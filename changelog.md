## v0.1.0 - 2026-05-05
### Added
* **`LabReportResultSampleType`** — new non-exhaustive enum representing the sample type of a lab result (e.g. `urine`, `serum_plasma_blood`, `capillary_blood`).
* **`LabReportResultMeasurementKind`** — new non-exhaustive enum representing how a lab result was measured (e.g. `direct`, `calculated`, `ratio`).
* **`LabReportResult.SampleType`** and **`LabReportResult.MeasurementKind`** — new optional fields on `LabReportResult` with corresponding getter and setter methods.
* **`MealInDbBaseClientFacingSource.CalendarDate`** — new required `string` field representing the meal date in `YYYY-mm-dd` format, with `GetCalendarDate` and `SetCalendarDate` methods.
### Changed
* **`Environments`** — all default base URLs updated from `tryvital.io` to `junction.com` domains (e.g. `Production` is now `https://api.us.junction.com`); consumers relying on the default URL without an explicit override will now target the new host.

## v0.0.1 - 2026-05-01
* Initial SDK generation
* 🌿 Generated with Fern

