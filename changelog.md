## [v3.0.0] - 2026-10-10
### Breaking Changes
- **`GetUnmatchedResultResponse`** — removed and replaced by `GetUnmatchedResultTestResponse` with an entirely different field set (`RunId`, `Stage`, `Case`, `OrderSource`, etc.); update all references and type assertions to use `GetUnmatchedResultTestResponse`.
- **`UnmatchedResult.IsStale`** — field and its `SetIsStale()` setter removed with no replacement; remove all call sites.

### Added
- **`CheckoutSessionAppointment`** — new type representing a PSC appointment slot held during checkout; attach it to a session via the new `CreateCheckoutSessionBody.Appointment` field and `SetAppointment()` setter.
- **Lab-test promotion** — new types `LabTestPromotion`, `LabTestPromotionSource`, `GetPromotionSourceLabTestsRequest`, and `ListPromotionsLabTestsRequest` support promoting sandbox lab tests to production.
- **Unmatched-result update tracking** — new types `UnmatchedResultUpdate`, `CreateUnmatchedResultUpdateBody`, `ListUnmatchedResultUpdatesLabTestsRequest`, `ListUnmatchedResultUpdatesResponse`, and related enums (`UnmatchedResultUpdateActorType`, `UnmatchedResultUpdateStatus`, `MatchReviewTransitionStatus`) enable recording and listing status transitions on unmatched results.
- **Collection instructions** — new `GetLabTestCollectionInstructionsResponse` and `GetLabTestCollectionInstructionsLabTestsRequest` types expose tube count and lab details for a given lab test.
- **`UnmatchedResult` activity fields and new enum values** — `LatestActivityActorId`, `LatestActivityActorType`, and `LatestActivityAt` added to `UnmatchedResult`; `MatchReviewStatusFilterPendingCustomerReviewInProgress` added to `MatchReviewStatusFilter`.

## v2.0.0 - 2026-09-24

### Added

* **Order tracking** — added `labtests.Client.GetOrderTracking()`, tracking types, and an order-tracking webhook type.
* **Test-kit idempotency** — added optional idempotency controls when creating a test-kit order.
* **Result and status details** — added stale-result indicators and expanded order-status values.
* **Horizon AI device reliability** — added reliability columns for query selection, grouping, and aggregate expressions.

### Changed

* **Module path** — import v2 from `github.com/junction-api/junction-go/v2`; update all SDK imports to include `/v2`.
* **Order-set request types** — `OrderSetRequest` and `AddOnOrder` now live in the root package rather than `labtests`.

### Removed

* **Legacy timeseries methods** — removed the non-grouped `vitals` methods (including `Steps()` and `Heartrate()`) and their request types. Use the corresponding `*Grouped()` methods and handle their paginated grouped responses.
* **Hypnogram timeseries** — removed `Hypnogram()`, `HypnogramGrouped()`, their types, and the sleep-stream hypnogram field. Use sleep-cycle summaries and events.
* **Deprecated event fields** — removed `ClientFacingSource.Name`, `Logo`, and `Slug`; `ProviderConnectionCreated.Source`; and `HistoricalPullCompleted.IsFinal`. Use source context, `ProviderConnectionCreated.Provider`, and the completed event itself.

### Beta

* **Checkout** — added quote and checkout-session clients and request types, with checkout webhook types and the `upfront_payment` billing value.
* **Order-set pricing estimates** — added `labtests.Client.EstimateOrderSetPricing()` and pricing types.

## v1.3.0 - 2026-08-14

### Added

* **Orderable-test search** — added `compendium.Client.SearchOrderableTests()` and the related request and response types.
* **Unmatched lab-result management** — added methods for listing, testing, reviewing, accepting, and resolving unmatched results, together with match-review webhook types.
* **Lab-test pricing** — added pricing types and optional pricing fields on marker and paginated lab-test requests.
* **Provider and lab coverage** — added Google Health provider and OAuth values and the MTL lab value.
* **Lab metadata** — added optional source interpretation, lab logo URL, and lab-location website fields.
* **Request controls** — added `WithoutRetries()`, `WithMaxStreamReconnectAttempts()`, and `WithoutStreamReconnection()` options.

### Beta

* **Aggregate and lab-report states** — added the result-table resource and processing-error parsing state without affecting the stable-surface SemVer calculation.

## v1.2.0 - 2026-06-05
### Added
* **`AlignExpr`** — new public symbol
* **`AlignExprCarry`** — new public symbol
* **`AlignExprCarryVisitor`** — new public symbol
* **`CarryBackwardExpr`** — new public symbol
* **`CarryForwardExpr`** — new public symbol
* **`CarryNearestExpr`** — new public symbol
### Changed
* **`Query`** — new optional field(s): Align
### Beta
* **`LabReportResult`** — field(s) removed: IsSensitive
* **`LabReportResultIsSensitive`** — public symbol removed
* **`LabReportResultSensitivity`** — new public symbol
* **`NewLabReportResultIsSensitiveFromString()`** — public symbol removed
* **`NewLabReportResultSensitivityFromString()`** — new public symbol

## v1.1.0 - 2026-05-27
### Added
* **`UpdateOrder`** — new method on `labtests.Client` (and `RawClient`) to update a modifiable order's scheduled activation date via PATCH `/v3/order/{id}`; accepts the new `UpdateOrderBody` request type with `OrderId` and optional `ActivateBy` fields.
* **`GetOrderCommunicationSettingsResponse`**, **`PatchOrderCommunicationSettingsBody`**, and **`PatchOrderCommunicationSettingsResponse`** — new types for reading and updating per-order SMS communication settings.
* **`LabReportResult.IsSensitive`** and **`LabReportResult.LoincMatchStatus`** — new optional fields on `LabReportResult` with corresponding enum types `LabReportResultIsSensitive` (values: `sensitive`, `insensitive`, `unknown`) and `LabReportResultLoincMatchStatus` (values: `auto_match`, `needs_review`, `no_match`).

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
