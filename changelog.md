## v1.1.0 - 2026-05-27
### Added
* **`UpdateOrder`** — new method on `labtests.Client` (and `RawClient`) to update a modifiable order's scheduled activation date via PATCH `/v3/order/{id}`; accepts the new `UpdateOrderBody` request type with `OrderId` and optional `ActivateBy` fields.
* **`GetOrderCommunicationSettingsResponse`**, **`PatchOrderCommunicationSettingsBody`**, and **`PatchOrderCommunicationSettingsResponse`** — new types for reading and updating per-order SMS communication settings.
* **`LabReportResult.IsSensitive`** and **`LabReportResult.LoincMatchStatus`** — new optional fields on `LabReportResult` with corresponding enum types `LabReportResultIsSensitive` (values: `sensitive`, `insensitive`, `unknown`) and `LabReportResultLoincMatchStatus` (values: `auto_match`, `needs_review`, `no_match`).

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
