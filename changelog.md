## [v2.0.0] - 2026-09-12
### Breaking Changes
- **`AddOnOrder`** — previously exported struct and its methods (`GetMarkerIds`, `GetProviderIds`, `SetMarkerIds`, `SetProviderIds`) have been removed as a standalone type; replace any direct references with the new `AddOnOrder` type reintroduced in the checkout/order-set workflow.
- **`AggregateExprArgVisitor`**, **`QueryGroupByItemVisitor`**, **`QuerySelectItemVisitor`**, and **`UnnestExprUnnestVisitor`** — each interface now requires a new method `VisitReliabilityColumnExpr(*ReliabilityColumnExpr) error`; all existing implementations must add this method to compile.

### Added
- **`checkout.Client`** — new client package for managing checkout sessions and quotes, with `CreateCheckoutSession`, `GetCheckoutSession`, `ConfirmCheckoutSession`, `CreateQuote`, `RefineQuote`, and `GetQuote` methods; accessible via `client.Client.Checkout`.
- **`labtests.Client.EstimateOrderSetPricing()`** — new method to estimate pricing for an order set, backed by a full pricing component hierarchy (`OrderSetPricing`, `LabChargePricingComponent`, `GenericPricingComponent`, etc.) and the `PricingComponentId` enum.
- **`ReliabilityColumnExpr`** — new column expression type for querying data-reliability metrics, with a `ReliabilityColumnExprReliability` enum covering 15 reliability dimensions.
- **`CheckoutQuote`**, **`CheckoutSession`**, and related request/response types — new types supporting the end-to-end checkout flow, including new enums `CheckoutSessionStatus`, `CheckoutQuoteLineItemCode`, and `WalkInCollectionNetworkSlug`.
- **`IdempotencyKey`** and **`IdempotencyError`** — new optional fields on `CreateRegistrableTestkitOrderRequest` and forwarded as headers on `testkit.RawClient.CreateOrder` for idempotent order creation.

### Changed
- **`MatchReviewStatus`** — new enum value `MatchReviewStatusPendingCustomerReviewInProgress` (`pending_customer_review:in_progress`) added.
- **`PricingModifierMarkerPricingConditions`** — new optional `Keys []string` field added, listing property names present in conditions.
- **`IndexColumnExprIndex`** — new `"reliability"` constant (`IndexColumnExprIndexReliability`) added.
- **`IsStale`** — new optional field on `UnmatchedResult` and `GetUnmatchedResultResponse` indicating whether an unmatched result is stale.
- **`BillingUpfrontPayment`** — new `"upfront_payment"` constant added to the `Billing` enum.

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
