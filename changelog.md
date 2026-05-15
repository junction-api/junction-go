## v1.1.0 - 2026-05-15
### Added
* **`LabReportResultLoincMatchStatus`** — new enum type with values `auto_match`, `needs_review`, and `no_match` representing the LOINC matching status of a lab result.
* **`LoincMatchStatus`** field on `LabReportResult` — exposes the LOINC match status directly on lab report results.
* **`GetLoincMatchStatus()`** and **`SetLoincMatchStatus()`** methods on `LabReportResult` — provide safe accessor and setter for the new field.
* **`NewLabReportResultLoincMatchStatusFromString()`** — constructor function to parse a `LabReportResultLoincMatchStatus` from a raw string value.

## v1.0.0 - 2026-05-06
* Initial SDK generation
* 🌿 Generated with Fern
