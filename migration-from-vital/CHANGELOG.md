# Changelog

_Major release. Baseline: `tryVital/vital-go@v1.1.567`._

## Breaking changes

- **Go module path renamed** — [migration steps](MIGRATION.md#install)
  The Go module is published under a new path:

  - `github.com/tryVital/vital-go` → `github.com/junction-api/junction-go`

  Update `go get`, every `import` statement, and any tooling that pins the module by path. The new module is a replacement for the old one — there is no aliased re-export, so unmodified imports of the old path will not resolve.
- **Minimum Go toolchain is now 1.21** — [migration steps](MIGRATION.md#install)
  The `go.mod` file now declares `go 1.21`. Upgrade your toolchain (and any CI / Docker base images) to Go 1.21 or newer before installing the new module.
- **Server base URLs replaced** — [migration steps](MIGRATION.md#server-base-urls)
  Every server URL exposed by the SDK has been replaced as part of the rebrand. Code that pins or compares the server URL by string literal (for example, callers that pass a custom URL via `option.WithBaseURL(...)` or read `api.Environments.Production`) must be updated. The `Environments` struct shape is unchanged, only the URL values inside it.
  
  | Old | New |
  | --- | --- |
  | `https://api.tryvital.io` | `https://api.us.junction.com` |
  | `https://api.eu.tryvital.io` | `https://api.eu.junction.com` |
  | `https://api.sandbox.tryvital.io` | `https://api.sandbox.us.junction.com` |
  | `https://api.sandbox.eu.tryvital.io` | `https://api.sandbox.eu.junction.com` |
- **Path parameters now live on the request struct** — [migration steps](MIGRATION.md#inline-path-parameters)
  Methods that previously took path parameters such as `userId` and `orderId` as positional arguments now take a single request struct that carries those values as fields. The `ctx` and trailing `option.RequestOption` arguments are unchanged.
  
  This affects every resource client method whose path included a parameter — for example, `activity.Client.Get`, `vitals.Client.*`, `order.Client.*`, `user.Client.GetById`, and so on.
- **Request struct names are verb-leading** — [migration steps](MIGRATION.md#request-struct-rename)
  Generated request struct names now lead with the operation verb instead of the resource. For example:

  - `activity.ActivityGetRequest` → `activity.GetActivityRequest`
  - `link.LinkBulkExportConnectionsRequest` → `link.BulkExportConnectionsRequest`

  If you only construct request structs inline at the call site you do not need to do anything — the method signature accepts the new name. If you store a request value in a typed local variable, helper, or struct field, update the type reference to the new name.

## New & improved

- **New top-level resources**
  The SDK now exposes the `compendium`, `labaccount`, `ordertransaction` resource clients on the root client. See the API reference for the full endpoint list.
- **Configure streaming buffer size with `option.WithMaxStreamBufSize`**
  The SDK now exposes `option.WithMaxStreamBufSize` for callers that consume chunked / streaming endpoints and need to override the default scanner buffer ceiling.
  
  ```go
  client := client.NewClient(
      option.WithMaxStreamBufSize(1024 * 1024),
  )
  ```
- **Continuous Query DSL: subqueries, unnest, and menstrual-cycle expressions**
  The Continuous Query expression language adds scalar-output subqueries, list-column unnesting, a derived-readiness column expression, an awakenings macro, and a menstrual-cycle column with its own field-expression family — see the API reference for the full expression catalog.
- **Appointment booking gains notes and confirmation-timeout knobs**
  `AppointmentBookingRequest` (and `AppointmentRescheduleRequest`) now accept `AppointmentNotes`, plus `AsyncConfirmation`, `AsyncConfirmationTimeoutMillisecond`, and `SyncConfirmationTimeoutMillisecond` for callers that want to control how the SDK waits for the lab to confirm the booking.
  
  ```go
  _, err := client.LabTests.BookPscAppointment(
      ctx,
      &junctiongo.BookPscAppointmentLabTestsRequest{
          OrderId: orderID,
          Body: &junctiongo.AppointmentBookingRequest{
              AppointmentNotes:                  junctiongo.String("prefer morning"),
              AsyncConfirmation:                 junctiongo.Bool(true),
              AsyncConfirmationTimeoutMillisecond: junctiongo.Int(5000),
          },
      },
  )
  ```
- **Appointments link back to order transactions**
  `ClientFacingAppointment` exposes `OrderTransactionId` so callers can correlate a booked appointment with the new order-transaction resource.
- **Lab-test creation can target a specific lab account**
  `CreateLabTestRequest` accepts `LabAccountId` and `LabSlug`, allowing teams that operate multiple lab accounts (now exposed via the new `labaccount` resource) to route a lab-test definition to a specific account.
- **Sortable lab-test and order listings**
  `labtests.Client.Get` and `labtests.Client.GetOrders` accept `OrderDirection` and `OrderKey` on the request struct for stable sort control.
- **Order payloads carry transaction and origin context**
  `ClientFacingOrder` now exposes `OrderTransaction`, `Origin`, `LastEvent`, and `ClinicalNotes`. `ClientFacingOrderEvent` exposes `StatusDetail`. Address payloads (`Address`) gain `AccessNotes`. These are additive — existing field reads continue to work.
- **Raw response shapes formalized — `*V2InDB` types are now `*Raw`**
  Endpoints whose responses were previously typed as `*V2InDB` now use `*Raw` types. The values are unchanged; only the type names differ:
  
  - `ActivityV2InDB` → `*RawActivityResponse`
  - `BodyV2InDB` → `*RawBodyResponse`
  - `DeviceV2InDB` → `*RawDevicesResponse`
  - `SleepV2InDB` → `*RawSleepResponse`
  - `WorkoutV2InDB` → `*RawWorkoutsResponse`
  
  Replace any `*V2InDB`-typed variable declarations with the new `Raw*Response` shape. The on-the-wire JSON shape is unchanged.
- **User addresses with structured `UserAddress`**
  User-level address payloads now use the new `UserAddress` struct, exposing fields such as `Country`, `City`, `AccessNotes`, etc., for consistent address handling across user, insurance, and order flows.

## Removed

- **Legacy link methods removed** — [migration steps](MIGRATION.md#link-removed-legacy)
  These methods have been deprecated for over two years and were never part of the documented Junction Link integration path; they should not have been in the SDK in the first place. They are removed in this release:

  - `link.Client.EmailAuth`
  - `link.Client.PasswordAuth`
  - `link.Client.StartConnect`
  - `link.Client.ConnectManualProvider`
  - `link.Client.TokenState`
  - `link.Client.IsTokenValid`
  - `link.Client.GetLinkConfig`

  The supporting request/body types that backed these methods are removed alongside them:

  - `BeginLinkTokenRequest`
  - `EmailAuthLink`
  - `PasswordAuthLink`
  - `LinkTokenValidationRequest`
  - `ManualConnectionData`

  If you have call sites referencing these methods, see the Junction Link API reference for the documented integration path.
- **Public types removed** — [migration steps](MIGRATION.md#public-types-removed)
  Three top-level public types were removed from the SDK with no equivalent. If you imported any of these, drop the import:
  
  - `AuthType` — was used by the legacy `email_auth` flow only.
  - `ManualProviders` — was the parameter type for the now-removed `connectManualProvider` method (one of the legacy link methods, see above). With that method gone, this enum is removed too.
  - `ClientFacingUserKey` — the endpoint that used to return this model now returns `ClientFacingUser` instead. If you depended on the user-key shape, switch to reading the user fields off `ClientFacingUser` directly.
