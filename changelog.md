## v1.1.0 - 2026-05-18
### Added
* **`UpdateOrder`** — new method on `labtests.Client` (and `labtests.RawClient`) to update a modifiable order's scheduled activation date via PATCH `/v3/order/{id}`; supports rescheduling to a future date or clearing the schedule for immediate dispatch.
* **`UpdateOrderBody`** — new request type carrying `OrderId` and optional `ActivateBy` fields used by `UpdateOrder`.
* **`LabReportResultLoincMatchStatus`** — new enum type with values `auto_match`, `needs_review`, and `no_match`, plus a `NewLabReportResultLoincMatchStatusFromString` constructor.
* **`LabReportResult.LoincMatchStatus`** — new optional field on `LabReportResult` with corresponding `GetLoincMatchStatus` and `SetLoincMatchStatus` methods.

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
