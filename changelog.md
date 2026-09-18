## [v2.0.0] - 2026-09-18
### Breaking Changes
- **`AddOnOrder`** — struct removed; replace any references to `AddOnOrder`, `AddOnOrder.MarkerIds`, or `AddOnOrder.ProviderIds` with the new `OrderSetRequest` type.
- **`AggregateExprArgVisitor`**, **`QueryGroupByItemVisitor`**, **`QuerySelectItemVisitor`**, and **`UnnestExprUnnestVisitor`** — each interface gains a new required method `VisitReliabilityColumnExpr(*ReliabilityColumnExpr) error`; add this method to all existing implementations.

### Added
- **`checkout.Client`** — new sub-client (via `client.Client.Checkout`) for managing checkout sessions (`CreateCheckoutSession`, `GetCheckoutSession`, `ConfirmCheckoutSession`) and quotes (`CreateQuote`, `RefineQuote`, `GetQuote`).
- **`labtests.Client.EstimateOrderSetPricing()`** — new method for estimating order-set pricing via `POST /v3/lab_test/estimate_order_set_pricing`, backed by `EstimateOrderSetPricingBody` and `EstimateOrderSetPricingResponse`.
- **`ReliabilityColumnExpr`** and **`ReliabilityColumnExprReliability`** — new expression type and 15-value enum for querying data-reliability columns in aggregate, group-by, select, and unnest contexts.
- **`CheckoutQuote`**, **`CheckoutSession`**, and supporting types — new response, request, and enum types for the checkout quote and session workflows, including `CheckoutSessionStatus`, `CheckoutSessionPaymentMethod`, and `WalkInCollectionNetworkSlug`.
- **Idempotency support** — `IdempotencyKey` and `IdempotencyError` fields added to `CreateRegistrableTestkitOrderRequest`; `testkit.RawClient.CreateOrder` now forwards `X-Idempotency-Key` and `X-Idempotency-Error` headers.
- See full changelog for all changes

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
