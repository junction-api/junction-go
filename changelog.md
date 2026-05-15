## v1.1.0 - 2026-05-15
### Added
* **`LabReportResultLoincMatchStatus`** — new enum type with values `auto_match`, `needs_review`, and `no_match` representing the LOINC matching status of a lab report result.
* **`LabReportResult.LoincMatchStatus`** — new optional field on `LabReportResult` exposing the LOINC match status, accessible via `GetLoincMatchStatus()` and `SetLoincMatchStatus()`.
* **`NewLabReportResultLoincMatchStatusFromString()`** — constructor function to parse a `LabReportResultLoincMatchStatus` from a string value.

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
