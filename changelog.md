## [v2.0.0] - 2026-08-14
### Breaking Changes
- **`LabReportResult.IsSensitive`** — field removed and replaced by **`LabReportResult.Sensitivity`** (`*LabReportResultSensitivity`); replace all `GetIsSensitive()`/`SetIsSensitive()` calls with `GetSensitivity()`/`SetSensitivity()`.
- **`LabReportResultIsSensitive`** — type and **`NewLabReportResultIsSensitiveFromString()`** removed; use **`LabReportResultSensitivity`** and **`NewLabReportResultSensitivityFromString()`** instead.

### Added
- **`compendium.Client.SearchOrderableTests()`** — new POST `/v3/compendium/search_orderable_tests` method accepting `SearchOrderableTestsBody` and returning `SearchOrderableTestsResponse`.
- **`labtests.Client`** — new methods `ListUnmatchedResultTestCases()`, `CreateUnmatchedResultTest()`, `GetUnmatchedResultTest()`, `ListUnmatchedResults()`, `GetUnmatchedResult()`, `AcceptUnmatchedResult()`, and `ResolveUnmatchedResult()` for managing unmatched lab results and test cases.
- **`ClientFacingMatchReviewChanged`** / **`ClientFacingMatchReviewUpdated`** — new webhook event types for match review lifecycle events, each carrying a **`MatchReviewWebhookPayload`**.
- **`AlignExpr`** and related carry-fill types — new post-aggregation bucket alignment and carry-fill strategy types (`AlignExprCarry`, `CarryForwardExpr`, `CarryBackwardExpr`, `CarryNearestExpr`) plus a **`Query.Align`** field for CQ queries.
- **New enum values and request options** — `ParsingJobFailureReasonTooManyPages`, `ParsingJobFailureReasonProcessingError`, `ClientFacingResourceResultTable`, `LabsMtl`, `OAuthProvidersGoogleHealth`, and `ProvidersGoogleHealth` added; **`WithoutRetries()`**, **`WithMaxStreamReconnectAttempts()`**, and **`WithoutStreamReconnection()`** added as `RequestOption` helpers.

### Changed
- **`DisableRetries`** — the `RequestOptions.DisableRetries` flag is now respected across all client packages, enabling per-request retry suppression on every endpoint.
- **`BiomarkerResult.SourceInterpretation`** and **`ClientFacingLab.LogoUrl`** — new optional fields added to their respective types.
- **`Micros`** godoc — corrected units for minerals (mg) and vitamins (biotin/folic acid as μg, vitamin E as mg).

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
