## [v2.0.0] - 2026-06-12
### Breaking Changes
- **`LabReportResult.IsSensitive`** — field renamed to `Sensitivity` (type changed from `*LabReportResultIsSensitive` to `*LabReportResultSensitivity`); update all field accesses, and replace calls to `GetIsSensitive()`/`SetIsSensitive()` with `GetSensitivity()`/`SetSensitivity()`.
- **`LabReportResultIsSensitive`** and **`NewLabReportResultIsSensitiveFromString()`** — removed; use `LabReportResultSensitivity` and `NewLabReportResultSensitivityFromString()` instead.

### Added
- **`AlignExpr`**, **`AlignExprCarry`**, **`AlignExprCarryVisitor`**, **`CarryForwardExpr`**, **`CarryBackwardExpr`**, and **`CarryNearestExpr`** — new types supporting post-aggregation bucket alignment (carry-forward, carry-backward, carry-nearest) for CQ queries.
- **`Query.Align`** — new optional field (with `GetAlign()` / `SetAlign()`) to attach an alignment clause to a query.
- **`OAuthProvidersGoogleHealth`** and **`ProvidersGoogleHealth`** — new enum values for Google Health as an OAuth and data provider.
- **`ParsingJobFailureReasonTooManyPages`** — new enum value indicating a lab report was rejected due to page count.

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
