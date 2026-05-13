## v1.1.0 - 2026-05-13
### Added
* **`LabReportResultLoincMatchStatus`** — new enum type with values `auto_match`, `needs_review`, and `no_match`, plus a `NewLabReportResultLoincMatchStatusFromString()` constructor.
* **`LabReportResult.LoincMatchStatus`** — new optional field on `LabReportResult` indicating the LOINC matching status of a lab result.
* **`GetLoincMatchStatus()`** and **`SetLoincMatchStatus()`** — new accessor methods on `LabReportResult` for reading and writing the `LoincMatchStatus` field.

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
