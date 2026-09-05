## [v2.0.0] - 2026-09-05
### Breaking Changes
- **`AddOnOrder`** — type and all associated methods (`GetMarkerIds`, `GetProviderIds`, `SetMarkerIds`, `SetProviderIds`, etc.) have been removed; remove any references to `AddOnOrder` and update `OrderSetRequest` usage accordingly.

### Added
- **`checkout.Client`** — new sub-client exposed as `Client.Checkout` with `GetCheckoutSession`, `ConfirmCheckoutSession`, `CreateQuote`, `RefineQuote`, and `GetQuote` methods for managing checkout sessions and quotes.
- **`labtests.Client.EstimateOrderSetPricing()`** — new method (and corresponding `EstimateOrderSetPricingBody`/`EstimateOrderSetPricingResponse` types) for estimating order-set pricing before placing an order.
- **`OrderSetPricing`**, **`LabChargePricingComponent`**, **`GenericPricingComponent`**, and related pricing condition types — new types for granular per-component and aggregate pricing breakdowns.
- **`PricingComponentId`** — new non-exhaustive enum with constants for all charge types (`lab_charge`, `draw_charge`, `mobile_phlebotomy_charge`, `delivered_kit_charge`, etc.).
- **`CheckoutSession`**, **`CheckoutQuote`**, **`WalkInCollectionNetworkSlug`**, **`ClientFacingCheckoutQuoteCreated`**, and **`BillingUpfrontPayment`** — new types and enum values supporting checkout, walk-in collection networks, and upfront-payment billing.
- **`MatchReviewStatusPendingCustomerReviewInProgress`** — new `MatchReviewStatus` enum constant (`pending_customer_review:in_progress`).

### Changed
- **`PricingModifierMarkerPricingConditions`** — new optional `Keys []string` field added to expose condition property names including those unknown to the deserializer.

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
