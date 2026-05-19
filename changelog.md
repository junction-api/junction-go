## v1.1.0 - 2026-05-19
### Added
* **`UpdateOrder`** — new method on `labtests.Client` (and `RawClient`) to update a modifiable order's scheduled activation date via `PATCH /v3/order/{orderId}`.
* **`UpdateOrderBody`** — new request type with `OrderId` and optional `ActivateBy` fields used by `UpdateOrder`.
* **`LabReportResultLoincMatchStatus`** — new enum type with values `auto_match`, `needs_review`, and `no_match`, along with a `LoincMatchStatus` field on `LabReportResult` and corresponding getter/setter methods.

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
