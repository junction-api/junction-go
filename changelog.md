## v0.1.0 - 2026-05-04
### Added
* **`MealInDbBaseClientFacingSource.CalendarDate`** — new `string` field (with `GetCalendarDate()` and `SetCalendarDate()`) representing the meal date in `YYYY-mm-dd` format, populated for providers that only expose a calendar date.
### Changed
* **`Environments`** — all default API base URLs updated from `tryvital.io` to `junction.com` domains; consumers not supplying a custom `BaseURL` will automatically route to the new host after upgrading.

## v0.0.1 - 2026-05-01
* Initial SDK generation
* 🌿 Generated with Fern

