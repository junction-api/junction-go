# Migration guide

_From `tryVital/vital-go@v1.1.567` to the new release._

## Install the new Go module

<a id="install"></a>

This is a path replacement, not a version bump — the old module path is no longer published. Run `go get` against the new module and update every `import` statement that references the old path. The minimum Go toolchain is now 1.21.

Things to look out for:

- Sub-package imports (`.../client`, `.../option`, `.../activity`, `.../labtests`, etc.) — all move under the new module root with the same suffix.
- Aliased imports (`vitalclient "..."`, `vitalgo "..."`) — the alias is yours to keep or rename, but the import path on the right must change.
- `go.mod` `replace` directives, vendor directories, and lockfile / CI cache keys that pin the old module path.
- Bump the `go` directive in `go.mod` (and your CI Go version) to 1.21 or newer; the new module requires it.

**Before:**

```bash
go get github.com/tryVital/vital-go
```

```go
import (
    vitalclient "github.com/tryVital/vital-go/client"
    "github.com/tryVital/vital-go/option"
)
```

**After:**

```bash
go get github.com/junction-api/junction-go
```

```go
import (
    junctionclient "github.com/junction-api/junction-go/client"
    "github.com/junction-api/junction-go/option"
)
```

## Update server base URLs

<a id="server-base-urls"></a>

The four base URLs are replaced as follows:

| Old host                              | New host                                |
|---------------------------------------|-----------------------------------------|
| `https://api.tryvital.io`             | `https://api.us.junction.com`           |
| `https://api.eu.tryvital.io`          | `https://api.eu.junction.com`           |
| `https://api.sandbox.tryvital.io`     | `https://api.sandbox.us.junction.com`   |
| `https://api.sandbox.eu.tryvital.io`  | `https://api.sandbox.eu.junction.com`   |

If you read the URL through `api.Environments.Production` (or `ProductionEu` / `Sandbox` / `SandboxEu`), the field names still resolve correctly — only the URL string they return has changed. If you pass a literal URL via `option.WithBaseURL(...)`, replace the host directly.

Things to look out for:

- Hard-coded URL literals in fixtures, mocks, or test recordings.
- DNS allow-lists, proxy rules, and outbound-firewall configurations pinned to the old hostnames.
- Webhook receivers that filter on the source host.

**Before:**

```go
import (
    "github.com/tryVital/vital-go/client"
    "github.com/tryVital/vital-go/option"
)

c := client.NewClient(
    option.WithBaseURL("https://api.tryvital.io"),
)
```

**After:**

```go
import (
    "github.com/junction-api/junction-go/client"
    "github.com/junction-api/junction-go/option"
)

c := client.NewClient(
    option.WithBaseURL("https://api.us.junction.com"),
)
```

## Move path parameters into the request struct

<a id="inline-path-parameters"></a>

Methods that previously took path parameters (such as `userId` or `orderId`) as positional arguments now take a single request struct that carries those values as fields. The `ctx` and trailing `option.RequestOption` arguments are unchanged. This affects every resource client method whose path included a parameter — `activity.Client.Get`, `vitals.Client.*`, `order.Client.*`, `user.Client.GetById`, and so on.

**Before:**

```go
resp, err := client.Activity.Get(
    ctx,
    userID,
    &vitalgo.ActivityGetRequest{
        StartDate: "2024-01-01",
    },
)
```

**After:**

```go
resp, err := client.Activity.Get(
    ctx,
    &junctiongo.GetActivityRequest{
        UserId:    userID,
        StartDate: "2024-01-01",
    },
)
```

## Update typed references to renamed request structs

<a id="request-struct-rename"></a>

The struct-name change follows a fixed pattern: `<Resource><Verb>Request` becomes `<Verb><Resource>Request`. For example:

- `activity.ActivityGetRequest` → `activity.GetActivityRequest`
- `link.LinkBulkExportConnectionsRequest` → `link.BulkExportConnectionsRequest`

If you only construct request structs inline at the call site you do not need to do anything — the method signature accepts the new name. If you store a request value in a typed local variable, helper return type, or struct field, update the type reference.

**Before:**

```go
func buildActivityRequest() *vitalgo.ActivityGetRequest {
    return &vitalgo.ActivityGetRequest{StartDate: "2024-01-01"}
}
```

**After:**

```go
func buildActivityRequest() *junctiongo.GetActivityRequest {
    return &junctiongo.GetActivityRequest{StartDate: "2024-01-01"}
}
```

## Drop calls to the legacy link methods

<a id="link-removed-legacy"></a>

These methods were deprecated for years and were never part of the documented Junction Link integration. Customer code that didn't reference them needs no migration. If you do have call sites, replace them with the Junction Link integration described in the API reference — there isn't a one-to-one drop-in, the legacy methods wrapped retired endpoints with no published equivalents.

## Drop imports for removed public types

<a id="public-types-removed"></a>

Three names were exported from the package root in the old SDK but are not present in the new SDK:

- `AuthType` — was only used by the legacy `EmailAuth` flow.
- `ManualProviders` — was the parameter type for the now-removed `ConnectManualProvider` method.
- `ClientFacingUserKey` — callers should switch to `ClientFacingUser`. The endpoint that previously returned `ClientFacingUserKey` now returns `ClientFacingUser`.

**Before:**

```go
import vital "github.com/tryVital/vital-go"

var t vital.AuthType
var p vital.ManualProviders
var k vital.ClientFacingUserKey
```

**After:**

```go
// AuthType and ManualProviders have no replacement — drop the references.
// ClientFacingUserKey -> ClientFacingUser
import junction "github.com/junction-api/junction-go"

var u junction.ClientFacingUser
```
