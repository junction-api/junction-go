# Reference
## Link
<details><summary><code>client.Link.ListBulkOps() -> *junctiongo.BulkOpsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ListBulkOpsLinkRequest{
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        PageSize: junctiongo.Int(
            1,
        ),
    }
client.Link.ListBulkOps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**nextCursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**pageSize:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.BulkImport(request) -> *junctiongo.BulkImportConnectionsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BulkImportConnectionsBody{
        Provider: junctiongo.OAuthProvidersOura,
        Connections: []*junctiongo.ConnectionRecipe{
            &junctiongo.ConnectionRecipe{
                UserId: "user_id",
                AccessToken: "access_token",
                RefreshToken: "refresh_token",
                ProviderId: "provider_id",
                ExpiresAt: 1,
            },
        },
    }
client.Link.BulkImport(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider:** `*junctiongo.OAuthProviders` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**connections:** `[]*junctiongo.ConnectionRecipe` 
    
</dd>
</dl>

<dl>
<dd>

**waitForCompletion:** `*bool` 


Whether or not the endpoint should wait for the Bulk Op to complete before responding.

When `wait_for_completion` is enabled, the endpoint may respond 200 OK if the Bulk Op takes less than 20 seconds to complete.

Otherwise, the endpoint always responds with 202 Created once the submitted data have been enqueued successfully. You can use
the [List Bulk Ops](https://docs.tryvital.io/api-reference/link/list-bulk-ops) endpoint to inspect the progress of the Bulk Op.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.BulkTriggerHistoricalPull(request) -> any</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BulkTriggerHistoricalPullBody{
        UserIds: []string{
            "user_ids",
        },
        Provider: junctiongo.OAuthProvidersOura,
    }
client.Link.BulkTriggerHistoricalPull(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userIds:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.OAuthProviders` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**waitForCompletion:** `*bool` 


Whether or not the endpoint should wait for the Bulk Op to complete before responding.

When `wait_for_completion` is enabled, the endpoint may respond 200 OK if the Bulk Op takes less than 20 seconds to complete.

Otherwise, the endpoint always responds with 202 Created once the submitted data have been enqueued successfully. You can use
the [List Bulk Ops](https://docs.tryvital.io/api-reference/link/list-bulk-ops) endpoint to inspect the progress of the Bulk Op.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.BulkExport(request) -> *junctiongo.BulkExportConnectionsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BulkExportConnectionsBody{
        Provider: junctiongo.OAuthProvidersOura,
    }
client.Link.BulkExport(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userIds:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.OAuthProviders` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**nextToken:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.BulkPause(request) -> any</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BulkPauseConnectionsBody{
        UserIds: []string{
            "user_ids",
        },
        Provider: junctiongo.OAuthProvidersOura,
    }
client.Link.BulkPause(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userIds:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.OAuthProviders` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.Token(request) -> *junctiongo.LinkTokenExchangeResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Endpoint to generate a user link token, to be used throughout the vital
link process. The vital link token is a one time use token, that
expires after 10 minutes. If you would like vital-link widget to launch
with a specific provider, pass in a provider in the body. If you would
like to redirect to a custom url after successful or error connection,
pass in your own custom redirect_url parameter.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.LinkTokenExchange{
        UserId: "user_id",
    }
client.Link.Token(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` — User id returned by vital create user request. This id should be stored in your database against the user and used for all interactions with the vital api.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.Providers` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**redirectUrl:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**filterOnProviders:** `[]*junctiongo.Providers` 

An allowlist of providers dictating what Vital Link Widget should show to the end user.
If unspecified, all linkable providers are shown.

This has no effect on programmatic Vital Link API usage.
    
</dd>
</dl>

<dl>
<dd>

**onError:** `*string` 

By default, Vital Link Widget input forms for password and email providers have in-built error handling.

Specifying `on_error=redirect` disables this Vital Link Widget UI behaviour — it would
instead redirect to your `redirect_url`, with Link Error parameters injected.

This has no effect on OAuth providers — they always redirect to your `redirect_url`. This also has
no effect on programmatic Vital Link API usage.
    
</dd>
</dl>

<dl>
<dd>

**onClose:** `*string` 

By default, Vital Link Widget closes the window or tab when the user taps the Close button.

Specifying `on_close=redirect` would change the Close button behaviour to redirect to your `redirect_url`
with the `user_cancelled` error specified.

This has no effect on programmatic Vital Link API usage.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.CodeCreate() -> *junctiongo.VitalTokenCreatedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Generate a token to invite a user of Vital mobile app to your team
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CodeCreateLinkRequest{
        UserId: "user_id",
        ExpiresAt: junctiongo.Time(
            junctiongo.MustParseDateTime(
                "2024-01-15T09:30:00Z",
            ),
        ),
    }
client.Link.CodeCreate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**expiresAt:** `*time.Time` — When the link code should expire. Defaults to server time plus 1 hour.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.GenerateOauthLink(OauthProvider) -> *junctiongo.Source</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint generates an OAuth link for oauth provider
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GenerateOauthLinkLinkRequest{
        OauthProvider: junctiongo.OAuthProvidersOura.Ptr(),
    }
client.Link.GenerateOauthLink(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**oauthProvider:** `*junctiongo.OAuthProviders` 
    
</dd>
</dl>

<dl>
<dd>

**vitalLinkToken:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.ConnectPasswordProvider(Provider, request) -> *junctiongo.ProviderLinkResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This connects auth providers that are password based.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.IndividualProviderData{
        Provider: junctiongo.PasswordProvidersWhoop.Ptr(),
        Username: "username",
        Password: "password",
    }
client.Link.ConnectPasswordProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider:** `*junctiongo.PasswordProviders` 
    
</dd>
</dl>

<dl>
<dd>

**vitalLinkToken:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**username:** `string` — Username for provider
    
</dd>
</dl>

<dl>
<dd>

**password:** `string` — Password for provider
    
</dd>
</dl>

<dl>
<dd>

**region:** `*junctiongo.Region` — Provider region to authenticate against. Only applicable to specific providers. ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.CompletePasswordProviderMfa(Provider, request) -> *junctiongo.ProviderLinkResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This connects auth providers that are password based.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CompletePasswordProviderMfaBody{
        Provider: junctiongo.PasswordProvidersWhoop.Ptr(),
        MfaCode: "mfa_code",
    }
client.Link.CompletePasswordProviderMfa(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider:** `*junctiongo.PasswordProviders` 
    
</dd>
</dl>

<dl>
<dd>

**vitalLinkToken:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**mfaCode:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.ConnectEmailAuthProvider(Provider, request) -> any</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This connects auth providers that are email based.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.EmailProviderAuthLink{
        Provider: junctiongo.EmailProviders(
            "freestyle_libre",
        ),
        Email: "email",
    }
client.Link.ConnectEmailAuthProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**provider:** `junctiongo.EmailProviders` 
    
</dd>
</dl>

<dl>
<dd>

**vitalLinkToken:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**email:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**emailProviderAuthLinkProvider:** `*junctiongo.Providers` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**region:** `*junctiongo.Region` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.GetAllProviders() -> []*junctiongo.SourceLink</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET List of all available providers given the generated link token.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetAllProvidersLinkRequest{}
client.Link.GetAllProviders(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**vitalLinkToken:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Link.ConnectDemoProvider(request) -> *junctiongo.DemoConnectionStatus</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST Connect the given Vital user to a demo provider.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.DemoConnectionCreationPayload{
        UserId: "user_id",
        Provider: junctiongo.DemoProvidersAppleHealthKit,
    }
client.Link.ConnectDemoProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` — Vital user ID
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.DemoProviders` — Demo provider. For more information, please check out our docs (https://docs.tryvital.io/wearables/providers/test_data) ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Electrocardiogram
<details><summary><code>client.Electrocardiogram.Get(UserId) -> *junctiongo.ClientFacingElectrocardiogramResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get electrocardiogram summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetElectrocardiogramRequest{
        UserId: "user_id",
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
    }
client.Electrocardiogram.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## SleepCycle
<details><summary><code>client.SleepCycle.Get(UserId) -> *junctiongo.ClientSleepCycleResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get sleep cycle for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetSleepCycleRequest{
        UserId: "user_id",
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
    }
client.SleepCycle.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Profile
<details><summary><code>client.Profile.Get(UserId) -> *junctiongo.ClientFacingProfile</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get profile for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetProfileRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
    }
client.Profile.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Profile.GetRaw(UserId) -> *junctiongo.RawProfile</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get raw profile for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetRawProfileRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
    }
client.Profile.GetRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Devices
<details><summary><code>client.Devices.GetRaw(UserId) -> *junctiongo.RawDevicesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get Devices for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetRawDevicesRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
    }
client.Devices.GetRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Activity
<details><summary><code>client.Activity.Get(UserId) -> *junctiongo.ClientActivityResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get activity summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetActivityRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Activity.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Activity.GetRaw(UserId) -> *junctiongo.RawActivityResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get raw activity summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetRawActivityRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Activity.GetRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Workouts
<details><summary><code>client.Workouts.Get(UserId) -> *junctiongo.ClientWorkoutResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get workout summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetWorkoutsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Workouts.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Workouts.GetRaw(UserId) -> *junctiongo.RawWorkoutResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get raw workout summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetRawWorkoutsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Workouts.GetRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Workouts.GetByWorkoutId(WorkoutId) -> *junctiongo.ClientFacingStream</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetByWorkoutIdWorkoutsRequest{
        WorkoutId: "workout_id",
    }
client.Workouts.GetByWorkoutId(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**workoutId:** `string` — The Vital ID for the workout
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Sleep
<details><summary><code>client.Sleep.Get(UserId) -> *junctiongo.ClientSleepResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get sleep summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetSleepRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Sleep.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sleep.GetRaw(UserId) -> *junctiongo.RawSleepResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get raw sleep summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetRawSleepRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Sleep.GetRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Sleep.GetStreamBySleepId(SleepId) -> *junctiongo.ClientFacingSleepStream</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get Sleep stream for a user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetStreamBySleepIdSleepRequest{
        SleepId: "sleep_id",
    }
client.Sleep.GetStreamBySleepId(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**sleepId:** `string` — The Vital Sleep ID
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Body
<details><summary><code>client.Body.Get(UserId) -> *junctiongo.ClientBodyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get Body summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetBodyRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Body.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Body.GetRaw(UserId) -> *junctiongo.RawBodyResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get raw Body summary for user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetRawBodyRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Body.GetRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Meal
<details><summary><code>client.Meal.Get(UserId) -> *junctiongo.ClientFacingMealResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get user's meals
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetMealRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Meal.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## MenstrualCycle
<details><summary><code>client.MenstrualCycle.Get(UserId) -> *junctiongo.MenstrualCycleResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetMenstrualCycleRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.MenstrualCycle.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Vitals
<details><summary><code>client.Vitals.WorkoutSwimmingStrokeGrouped(UserId) -> *junctiongo.GroupedWorkoutSwimmingStrokeResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WorkoutSwimmingStrokeGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.WorkoutSwimmingStrokeGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.WorkoutDistanceGrouped(UserId) -> *junctiongo.GroupedWorkoutDistanceResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WorkoutDistanceGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.WorkoutDistanceGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.HeartRateRecoveryOneMinuteGrouped(UserId) -> *junctiongo.GroupedHeartRateRecoveryOneMinuteResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HeartRateRecoveryOneMinuteGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.HeartRateRecoveryOneMinuteGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.WaistCircumferenceGrouped(UserId) -> *junctiongo.GroupedWaistCircumferenceResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WaistCircumferenceGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.WaistCircumferenceGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.LeanBodyMassGrouped(UserId) -> *junctiongo.GroupedLeanBodyMassResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.LeanBodyMassGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.LeanBodyMassGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyMassIndexGrouped(UserId) -> *junctiongo.GroupedBodyMassIndexResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyMassIndexGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyMassIndexGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BasalBodyTemperatureGrouped(UserId) -> *junctiongo.GroupedBasalBodyTemperatureResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BasalBodyTemperatureGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BasalBodyTemperatureGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.HandwashingGrouped(UserId) -> *junctiongo.GroupedHandwashingResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HandwashingGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.HandwashingGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.DaylightExposureGrouped(UserId) -> *junctiongo.GroupedDaylightExposureResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.DaylightExposureGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.DaylightExposureGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.UvExposureGrouped(UserId) -> *junctiongo.GroupedUvExposureResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UvExposureGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.UvExposureGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.FallGrouped(UserId) -> *junctiongo.GroupedFallResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.FallGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.FallGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.InhalerUsageGrouped(UserId) -> *junctiongo.GroupedInhalerUsageResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.InhalerUsageGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.InhalerUsageGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.PeakExpiratoryFlowRateGrouped(UserId) -> *junctiongo.GroupedPeakExpiratoryFlowRateResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.PeakExpiratoryFlowRateGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.PeakExpiratoryFlowRateGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.ForcedVitalCapacityGrouped(UserId) -> *junctiongo.GroupedForcedVitalCapacityResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ForcedVitalCapacityGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.ForcedVitalCapacityGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.ForcedExpiratoryVolume1Grouped(UserId) -> *junctiongo.GroupedForcedExpiratoryVolume1Response</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ForcedExpiratoryVolume1GroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.ForcedExpiratoryVolume1Grouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.WheelchairPushGrouped(UserId) -> *junctiongo.GroupedWheelchairPushResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WheelchairPushGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.WheelchairPushGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.SleepBreathingDisturbanceGrouped(UserId) -> *junctiongo.GroupedSleepBreathingDisturbanceResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.SleepBreathingDisturbanceGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.SleepBreathingDisturbanceGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.SleepApneaAlertGrouped(UserId) -> *junctiongo.GroupedSleepApneaAlertResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.SleepApneaAlertGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.SleepApneaAlertGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.StandDurationGrouped(UserId) -> *junctiongo.GroupedStandDurationResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.StandDurationGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.StandDurationGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.StandHourGrouped(UserId) -> *junctiongo.GroupedStandHourResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.StandHourGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.StandHourGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.HeartRateAlertGrouped(UserId) -> *junctiongo.GroupedHeartRateAlertResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HeartRateAlertGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.HeartRateAlertGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.AfibBurdenGrouped(UserId) -> *junctiongo.GroupedAFibBurdenResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.AfibBurdenGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.AfibBurdenGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.WorkoutDurationGrouped(UserId) -> *junctiongo.GroupedWorkoutDurationResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WorkoutDurationGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.WorkoutDurationGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Vo2MaxGrouped(UserId) -> *junctiongo.GroupedVo2MaxResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.Vo2MaxGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Vo2MaxGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.StressLevelGrouped(UserId) -> *junctiongo.GroupedStressLevelResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.StressLevelGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.StressLevelGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.MindfulnessMinutesGrouped(UserId) -> *junctiongo.GroupedMindfulnessMinutesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.MindfulnessMinutesGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.MindfulnessMinutesGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CaffeineGrouped(UserId) -> *junctiongo.GroupedCaffeineResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CaffeineGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CaffeineGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.WaterGrouped(UserId) -> *junctiongo.GroupedWaterResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WaterGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.WaterGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.StepsGrouped(UserId) -> *junctiongo.GroupedStepsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.StepsGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.StepsGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.FloorsClimbedGrouped(UserId) -> *junctiongo.GroupedFloorsClimbedResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.FloorsClimbedGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.FloorsClimbedGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.DistanceGrouped(UserId) -> *junctiongo.GroupedDistanceResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.DistanceGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.DistanceGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CaloriesBasalGrouped(UserId) -> *junctiongo.GroupedCaloriesBasalResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CaloriesBasalGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CaloriesBasalGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CaloriesActiveGrouped(UserId) -> *junctiongo.GroupedCaloriesActiveResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CaloriesActiveGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CaloriesActiveGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.RespiratoryRateGrouped(UserId) -> *junctiongo.GroupedRespiratoryRateResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.RespiratoryRateGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.RespiratoryRateGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.NoteGrouped(UserId) -> *junctiongo.GroupedNoteResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.NoteGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.NoteGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.InsulinInjectionGrouped(UserId) -> *junctiongo.GroupedInsulinInjectionResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.InsulinInjectionGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.InsulinInjectionGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.IgeGrouped(UserId) -> *junctiongo.GroupedIgeResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.IgeGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.IgeGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.IggGrouped(UserId) -> *junctiongo.GroupedIggResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.IggGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.IggGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.HypnogramGrouped(UserId) -> *junctiongo.GroupedHypnogramResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HypnogramGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.HypnogramGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.HrvGrouped(UserId) -> *junctiongo.GroupedHrvResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HrvGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.HrvGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.HeartrateGrouped(UserId) -> *junctiongo.GroupedHeartRateResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HeartrateGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.HeartrateGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.GlucoseGrouped(UserId) -> *junctiongo.GroupedGlucoseResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GlucoseGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.GlucoseGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CholesterolGrouped(UserId) -> *junctiongo.GroupedCholesterolResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CholesterolGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CholesterolGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CarbohydratesGrouped(UserId) -> *junctiongo.GroupedCarbohydratesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CarbohydratesGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CarbohydratesGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyTemperatureDeltaGrouped(UserId) -> *junctiongo.GroupedBodyTemperatureDeltaResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyTemperatureDeltaGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyTemperatureDeltaGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyTemperatureGrouped(UserId) -> *junctiongo.GroupedBodyTemperatureResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyTemperatureGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyTemperatureGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyWeightGrouped(UserId) -> *junctiongo.GroupedBodyWeightResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyWeightGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyWeightGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyFatGrouped(UserId) -> *junctiongo.GroupedBodyFatResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyFatGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyFatGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BloodOxygenGrouped(UserId) -> *junctiongo.GroupedBloodOxygenResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BloodOxygenGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BloodOxygenGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.ElectrocardiogramVoltageGrouped(UserId) -> *junctiongo.GroupedElectrocardiogramVoltageResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ElectrocardiogramVoltageGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.ElectrocardiogramVoltageGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BloodPressureGrouped(UserId) -> *junctiongo.GroupedBloodPressureResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BloodPressureGroupedVitalsRequest{
        UserId: "user_id",
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BloodPressureGrouped(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Vo2Max(UserId) -> []*junctiongo.ClientFacingVo2MaxTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.Vo2MaxVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Vo2Max(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.StressLevel(UserId) -> []*junctiongo.ClientFacingStressLevelTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.StressLevelVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.StressLevel(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.MindfulnessMinutes(UserId) -> []*junctiongo.ClientFacingMindfulnessMinutesTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.MindfulnessMinutesVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.MindfulnessMinutes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Caffeine(UserId) -> []*junctiongo.ClientFacingCaffeineTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CaffeineVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Caffeine(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Water(UserId) -> []*junctiongo.ClientFacingWaterTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.WaterVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Water(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Steps(UserId) -> []*junctiongo.ClientFacingStepsTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.StepsVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Steps(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.FloorsClimbed(UserId) -> []*junctiongo.ClientFacingFloorsClimbedTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.FloorsClimbedVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.FloorsClimbed(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Distance(UserId) -> []*junctiongo.ClientFacingDistanceTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.DistanceVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Distance(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CaloriesBasal(UserId) -> []*junctiongo.ClientFacingCaloriesBasalTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CaloriesBasalVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CaloriesBasal(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CaloriesActive(UserId) -> []*junctiongo.ClientFacingCaloriesActiveTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CaloriesActiveVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CaloriesActive(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.RespiratoryRate(UserId) -> []*junctiongo.ClientFacingRespiratoryRateTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.RespiratoryRateVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.RespiratoryRate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Ige(UserId) -> []*junctiongo.ClientFacingIgeTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.IgeVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Ige(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Igg(UserId) -> []*junctiongo.ClientFacingIggTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.IggVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Igg(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Hypnogram(UserId) -> []*junctiongo.ClientFacingHypnogramTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HypnogramVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Hypnogram(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Hrv(UserId) -> []*junctiongo.ClientFacingHrvTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HrvVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Hrv(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Heartrate(UserId) -> []*junctiongo.ClientFacingHeartRateTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.HeartrateVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Heartrate(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Glucose(UserId) -> []*junctiongo.ClientFacingGlucoseTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GlucoseVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Glucose(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CholesterolTriglycerides(UserId) -> []*junctiongo.ClientFacingCholesterolTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CholesterolTriglyceridesVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CholesterolTriglycerides(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CholesterolTotal(UserId) -> []*junctiongo.ClientFacingCholesterolTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CholesterolTotalVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CholesterolTotal(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CholesterolLdl(UserId) -> []*junctiongo.ClientFacingCholesterolTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CholesterolLdlVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CholesterolLdl(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.CholesterolHdl(UserId) -> []*junctiongo.ClientFacingCholesterolTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CholesterolHdlVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.CholesterolHdl(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.Cholesterol(UserId) -> []*junctiongo.ClientFacingCholesterolTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CholesterolVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.Cholesterol(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyWeight(UserId) -> []*junctiongo.ClientFacingBodyWeightTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyWeightVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyWeight(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BodyFat(UserId) -> []*junctiongo.ClientFacingBodyFatTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BodyFatVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BodyFat(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BloodOxygen(UserId) -> []*junctiongo.ClientFacingBloodOxygenTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BloodOxygenVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BloodOxygen(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.ElectrocardiogramVoltage(UserId) -> []*junctiongo.ClientFacingElectrocardiogramVoltageTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ElectrocardiogramVoltageVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.ElectrocardiogramVoltage(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Vitals.BloodPressure(UserId) -> []*junctiongo.ClientFacingBloodPressureTimeseries</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BloodPressureVitalsRequest{
        UserId: "user_id",
        Provider: junctiongo.String(
            "provider",
        ),
        StartDate: "start_date",
        EndDate: junctiongo.String(
            "end_date",
        ),
    }
client.Vitals.BloodPressure(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*string` — Provider oura/strava etc
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `string` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*string` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## User
<details><summary><code>client.User.GetAll() -> *junctiongo.PaginatedUsersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET All users for team.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetAllUserRequest{
        Offset: junctiongo.Int(
            1,
        ),
        Limit: junctiongo.Int(
            1,
        ),
    }
client.User.GetAll(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**offset:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.Create(request) -> *junctiongo.ClientFacingUser</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST Create a Vital user given a client_user_id and returns the user_id.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UserCreateBody{
        ClientUserId: "client_user_id",
    }
client.User.Create(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clientUserId:** `string` — A unique ID representing the end user. Typically this will be a user ID from your application. Personally identifiable information, such as an email address or phone number, should not be used in the client_user_id.
    
</dd>
</dl>

<dl>
<dd>

**fallbackTimeZone:** `*string` 


    Fallback time zone of the user, in the form of a valid IANA tzdatabase identifier (e.g., `Europe/London` or `America/Los_Angeles`).
    Used when pulling data from sources that are completely time zone agnostic (e.g., all time is relative to UTC clock, without any time zone attributions on data points).
    
    
</dd>
</dl>

<dl>
<dd>

**fallbackBirthDate:** `*string` — Fallback date of birth of the user, in YYYY-mm-dd format. Used for calculating max heartrate for providers that don not provide users' age.
    
</dd>
</dl>

<dl>
<dd>

**ingestionStart:** `*string` — Starting bound for user [data ingestion bounds](https://docs.tryvital.io/wearables/providers/data-ingestion-bounds).
    
</dd>
</dl>

<dl>
<dd>

**ingestionEnd:** `*string` — Ending bound for user [data ingestion bounds](https://docs.tryvital.io/wearables/providers/data-ingestion-bounds).
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetTeamMetrics() -> *junctiongo.MetricsResult</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET metrics for team.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.User.GetTeamMetrics(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetConnectedProviders(UserId) -> map[string][]*junctiongo.ClientFacingProviderWithStatus</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET Users connected providers
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetConnectedProvidersUserRequest{
        UserId: "user_id",
    }
client.User.GetConnectedProviders(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetLatestUserInfo(UserId) -> *junctiongo.UserInfo</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetLatestUserInfoUserRequest{
        UserId: "user_id",
    }
client.User.GetLatestUserInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.CreateInsurance(UserId, request) -> *junctiongo.ClientFacingInsurance</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreateInsuranceRequest{
        UserId: "user_id",
        PayorCode: "payor_code",
        MemberId: "member_id",
        Relationship: junctiongo.ResponsibleRelationshipSelf,
        Insured: &junctiongo.VitalCoreSchemasDbSchemasLabTestInsurancePersonDetails{
            FirstName: "first_name",
            LastName: "last_name",
            Gender: junctiongo.GenderFemale,
            Address: &junctiongo.Address{
                FirstLine: "first_line",
                Country: "country",
                Zip: "zip",
                City: "city",
                State: "state",
            },
            Dob: "dob",
            Email: "email",
            PhoneNumber: "phone_number",
        },
    }
client.User.CreateInsurance(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**payorCode:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**memberId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**groupId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**relationship:** `*junctiongo.ResponsibleRelationship` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**insured:** `*junctiongo.VitalCoreSchemasDbSchemasLabTestInsurancePersonDetails` 
    
</dd>
</dl>

<dl>
<dd>

**guarantor:** `*junctiongo.GuarantorDetails` 
    
</dd>
</dl>

<dl>
<dd>

**isPrimary:** `*bool` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetLatestInsurance(UserId) -> *junctiongo.ClientFacingInsurance</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetLatestInsuranceUserRequest{
        UserId: "user_id",
        IsPrimary: junctiongo.Bool(
            true,
        ),
    }
client.User.GetLatestInsurance(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**isPrimary:** `*bool` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.UpsertUserInfo(UserId, request) -> *junctiongo.UserInfo</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UserInfoCreateRequest{
        UserId: "user_id",
        FirstName: "first_name",
        LastName: "last_name",
        Email: "email",
        PhoneNumber: "phone_number",
        Gender: "gender",
        Dob: "dob",
        Address: &junctiongo.UserAddress{
            FirstLine: "first_line",
            Country: "country",
            Zip: "zip",
            City: "city",
            State: "state",
        },
    }
client.User.UpsertUserInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**firstName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**lastName:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**email:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**phoneNumber:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**gender:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**dob:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**address:** `*junctiongo.UserAddress` 
    
</dd>
</dl>

<dl>
<dd>

**medicalProxy:** `*junctiongo.GuarantorDetails` 
    
</dd>
</dl>

<dl>
<dd>

**race:** `*junctiongo.Race` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**ethnicity:** `*junctiongo.Ethnicity` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**sexualOrientation:** `*junctiongo.SexualOrientation` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**genderIdentity:** `*junctiongo.GenderIdentity` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetByClientUserId(ClientUserId) -> *junctiongo.ClientFacingUser</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET user_id from client_user_id.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetByClientUserIdUserRequest{
        ClientUserId: "client_user_id",
    }
client.User.GetByClientUserId(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**clientUserId:** `string` — A unique ID representing the end user. Typically this will be a user ID number from your application. Personally identifiable information, such as an email address or phone number, should not be used in the client_user_id.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.DeregisterProvider(UserId, Provider) -> *junctiongo.UserSuccessResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.DeregisterProviderUserRequest{
        UserId: "user_id",
        Provider: junctiongo.ProvidersOura.Ptr(),
    }
client.User.DeregisterProvider(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.Providers` — Provider slug. e.g., `oura`, `fitbit`, `garmin`.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.Get(UserId) -> *junctiongo.ClientFacingUser</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetUserRequest{
        UserId: "user_id",
    }
client.User.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.Delete(UserId) -> *junctiongo.UserSuccessResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.DeleteUserRequest{
        UserId: "user_id",
    }
client.User.Delete(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.Patch(UserId, request) -> error</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UserPatchBody{
        UserId: "user_id",
    }
client.User.Patch(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**fallbackTimeZone:** `*string` 


    Fallback time zone of the user, in the form of a valid IANA tzdatabase identifier (e.g., `Europe/London` or `America/Los_Angeles`).
    Used when pulling data from sources that are completely time zone agnostic (e.g., all time is relative to UTC clock, without any time zone attributions on data points).
    
    
</dd>
</dl>

<dl>
<dd>

**fallbackBirthDate:** `*string` — Fallback date of birth of the user, in YYYY-mm-dd format. Used for calculating max heartrate for providers that don not provide users' age.
    
</dd>
</dl>

<dl>
<dd>

**ingestionStart:** `*string` — Starting bound for user [data ingestion bounds](https://docs.tryvital.io/wearables/providers/data-ingestion-bounds).
    
</dd>
</dl>

<dl>
<dd>

**ingestionEnd:** `*string` — Ending bound for user [data ingestion bounds](https://docs.tryvital.io/wearables/providers/data-ingestion-bounds).
    
</dd>
</dl>

<dl>
<dd>

**clientUserId:** `*string` — A unique ID representing the end user. Typically this will be a user ID from your application. Personally identifiable information, such as an email address or phone number, should not be used in the client_user_id.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.UndoDelete() -> *junctiongo.UserSuccessResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UndoDeleteUserRequest{
        UserId: junctiongo.String(
            "user_id",
        ),
        ClientUserId: junctiongo.String(
            "client_user_id",
        ),
    }
client.User.UndoDelete(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `*string` — User ID to undo deletion. Mutually exclusive with `client_user_id`.
    
</dd>
</dl>

<dl>
<dd>

**clientUserId:** `*string` — Client User ID to undo deletion. Mutually exclusive with `user_id`.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.Refresh(UserId) -> *junctiongo.UserRefreshSuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Trigger a manual refresh for a specific user
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.RefreshUserRequest{
        UserId: "user_id",
        Timeout: junctiongo.Float64(
            1.1,
        ),
    }
client.User.Refresh(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**timeout:** `*float64` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetDevices(UserId) -> []*junctiongo.ClientFacingDevice</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetDevicesUserRequest{
        UserId: "user_id",
    }
client.User.GetDevices(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetDevice(UserId, DeviceId) -> *junctiongo.ClientFacingDevice</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetDeviceUserRequest{
        UserId: "user_id",
        DeviceId: "device_id",
    }
client.User.GetDevice(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**deviceId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.GetUserSignInToken(UserId) -> *junctiongo.UserSignInTokenResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetUserSignInTokenUserRequest{
        UserId: "user_id",
    }
client.User.GetUserSignInToken(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.User.CreatePortalUrl(UserId, request) -> *junctiongo.CreateUserPortalUrlResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreateUserPortalUrlBody{
        UserId: "user_id",
        Context: junctiongo.CreateUserPortalUrlBodyContextLaunch,
    }
client.User.CreatePortalUrl(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**context:** `*junctiongo.CreateUserPortalUrlBodyContext` 

`launch`: Generates a short-lived (minutes) portal URL that is intended for launching a user from your
authenticated web context directly into the Junction User Portal. This URL is not suitable for asynchronous
communications due to its verbosity as well as short-lived nature.

`communications`: Generates a long-lived (weeks) but shortened portal URL that is suitable for Emails, SMS
messages and other communication channels. Users may be asked to verify their identity with Email and SMS
authentication, e.g., when they open a short link on a new device. ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**orderId:** `*string` — If specified, the generated URL will deeplink to the specified Order.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Team
<details><summary><code>client.Team.Get(TeamId) -> *junctiongo.ClientFacingTeam</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get team.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetTeamRequest{
        TeamId: "team_id",
    }
client.Team.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**teamId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Team.GetUserById() -> []*junctiongo.ClientFacingUser</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Search team users by user_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetUserByIdTeamRequest{
        QueryId: junctiongo.String(
            "query_id",
        ),
    }
client.Team.GetUserById(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**queryId:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Team.GetSvixUrl() -> map[string]any</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Team.GetSvixUrl(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Team.GetSourcePriorities() -> []map[string]any</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET source priorities.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetSourcePrioritiesTeamRequest{
        DataType: junctiongo.PriorityResourceWorkouts.Ptr(),
    }
client.Team.GetSourcePriorities(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**dataType:** `*junctiongo.PriorityResource` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Team.UpdateSourcePriorities() -> []map[string]any</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Patch source priorities.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.Team.UpdateSourcePriorities(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Team.GetPhysicians(TeamId) -> []*junctiongo.ClientFacingPhysician</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPhysiciansTeamRequest{
        TeamId: "team_id",
    }
client.Team.GetPhysicians(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**teamId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Providers
<details><summary><code>client.Providers.GetAll() -> []*junctiongo.ClientFacingProviderDetailed</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get Provider list
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetAllProvidersRequest{
        SourceType: junctiongo.String(
            "source_type",
        ),
    }
client.Providers.GetAll(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**sourceType:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Introspect
<details><summary><code>client.Introspect.GetUserResources() -> *junctiongo.UserResourcesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetUserResourcesIntrospectRequest{
        UserId: junctiongo.String(
            "user_id",
        ),
        Provider: junctiongo.ProvidersOura.Ptr(),
        UserLimit: junctiongo.Int(
            1,
        ),
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
    }
client.Introspect.GetUserResources(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `*string` — Filter by user ID.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.Providers` 
    
</dd>
</dl>

<dl>
<dd>

**userLimit:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Introspect.GetUserHistoricalPulls() -> *junctiongo.UserHistoricalPullsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetUserHistoricalPullsIntrospectRequest{
        UserId: junctiongo.String(
            "user_id",
        ),
        Provider: junctiongo.ProvidersOura.Ptr(),
        UserLimit: junctiongo.Int(
            1,
        ),
        Cursor: junctiongo.String(
            "cursor",
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
    }
client.Introspect.GetUserHistoricalPulls(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `*string` — Filter by user ID.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.Providers` 
    
</dd>
</dl>

<dl>
<dd>

**userLimit:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**cursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` — The cursor for fetching the next page, or `null` to fetch the first page.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## LabTests
<details><summary><code>client.LabTests.Get() -> []*junctiongo.ClientFacingLabTest</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET all the lab tests the team has access to.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetLabTestsRequest{
        GenerationMethod: junctiongo.LabTestGenerationMethodFilterAuto.Ptr(),
        LabSlug: junctiongo.String(
            "lab_slug",
        ),
        CollectionMethod: junctiongo.LabTestCollectionMethodTestkit.Ptr(),
        Status: junctiongo.LabTestStatusActive.Ptr(),
        MarkerIds: []*int{
            junctiongo.Int(
                1,
            ),
        },
        ProviderIds: []*string{
            junctiongo.String(
                "provider_ids",
            ),
        },
        Name: junctiongo.String(
            "name",
        ),
        OrderKey: junctiongo.GetLabTestsRequestOrderKeyPrice.Ptr(),
        OrderDirection: junctiongo.GetLabTestsRequestOrderDirectionAsc.Ptr(),
    }
client.LabTests.Get(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**generationMethod:** `*junctiongo.LabTestGenerationMethodFilter` — Filter on whether auto-generated lab tests created by Vital, manually created lab tests, or all lab tests should be returned.
    
</dd>
</dl>

<dl>
<dd>

**labSlug:** `*string` — Filter by the slug of the lab for these lab tests.
    
</dd>
</dl>

<dl>
<dd>

**collectionMethod:** `*junctiongo.LabTestCollectionMethod` — Filter by the collection method for these lab tests.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*junctiongo.LabTestStatus` — Filter by the status of these lab tests.
    
</dd>
</dl>

<dl>
<dd>

**markerIds:** `*int` — Filter to only include lab tests containing these marker IDs.
    
</dd>
</dl>

<dl>
<dd>

**providerIds:** `*string` — Filter to only include lab tests containing these provider IDs.
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — Filter by the name of the lab test (a case-insensitive substring search).
    
</dd>
</dl>

<dl>
<dd>

**orderKey:** `*junctiongo.GetLabTestsRequestOrderKey` 
    
</dd>
</dl>

<dl>
<dd>

**orderDirection:** `*junctiongo.GetLabTestsRequestOrderDirection` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.Create(request) -> *junctiongo.ClientFacingLabTest</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreateLabTestRequest{
        Name: "name",
        Method: junctiongo.LabTestCollectionMethodTestkit,
        Description: "description",
    }
client.LabTests.Create(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**markerIds:** `[]int` 
    
</dd>
</dl>

<dl>
<dd>

**providerIds:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**method:** `*junctiongo.LabTestCollectionMethod` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**description:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**fasting:** `*bool` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**labSlug:** `*junctiongo.Labs` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetById(LabTestId) -> *junctiongo.ClientFacingLabTest</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET all the lab tests the team has access to.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetByIdLabTestsRequest{
        LabTestId: "lab_test_id",
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
    }
client.LabTests.GetById(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labTestId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` — The lab account ID. This lab account is used to determine the availability of markers and lab tests.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.UpdateLabTest(LabTestId, request) -> *junctiongo.ClientFacingLabTest</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UpdateLabTestRequest{
        LabTestId: "lab_test_id",
    }
client.LabTests.UpdateLabTest(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labTestId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**active:** `*bool` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetMarkers() -> *junctiongo.GetMarkersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List active and orderable markers for a given Lab. Note that reflex markers are not included.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetMarkersLabTestsRequest{
        LabId: []*int{
            junctiongo.Int(
                1,
            ),
        },
        LabSlug: junctiongo.String(
            "lab_slug",
        ),
        Name: junctiongo.String(
            "name",
        ),
        ALaCarteEnabled: junctiongo.Bool(
            true,
        ),
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
        Page: junctiongo.Int(
            1,
        ),
        Size: junctiongo.Int(
            1,
        ),
    }
client.LabTests.GetMarkers(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labId:** `*int` — The identifier Vital assigned to a lab partner.
    
</dd>
</dl>

<dl>
<dd>

**labSlug:** `*string` — The slug of the lab for these markers. If both lab_id and lab_slug are provided, lab_slug will be used.
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — The name or test code of an individual biomarker or a panel.
    
</dd>
</dl>

<dl>
<dd>

**aLaCarteEnabled:** `*bool` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` — The lab account ID. This lab account is used to determine the availability of markers and lab tests.
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**size:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetMarkersForOrderSet(request) -> *junctiongo.GetMarkersResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetMarkersForOrderSetLabTestsRequest{
        Page: junctiongo.Int(
            1,
        ),
        Size: junctiongo.Int(
            1,
        ),
        Body: &junctiongo.OrderSetRequest{},
    }
client.LabTests.GetMarkersForOrderSet(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**page:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**size:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.OrderSetRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetMarkersForLabTest(LabTestId) -> *junctiongo.GetMarkersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

List all markers for a given Lab Test, as well as any associated reflex markers.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetMarkersForLabTestLabTestsRequest{
        LabTestId: "lab_test_id",
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
        Page: junctiongo.Int(
            1,
        ),
        Size: junctiongo.Int(
            1,
        ),
    }
client.LabTests.GetMarkersForLabTest(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labTestId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` — The lab account ID. This lab account is used to determine the availability of markers and lab tests.
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**size:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetMarkersByLabAndProviderId(ProviderId, LabId) -> *junctiongo.ClientFacingMarker</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET a specific marker for the given lab and provider_id
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetMarkersByLabAndProviderIdLabTestsRequest{
        ProviderId: "provider_id",
        LabId: 1,
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
    }
client.LabTests.GetMarkersByLabAndProviderId(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**providerId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**labId:** `int` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` — The lab account ID. This lab account is used to determine the availability of markers and lab tests.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetLabs() -> []*junctiongo.ClientFacingLab</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET all the labs.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.LabTests.GetLabs(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPaginated() -> *junctiongo.LabTestResourcesResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET lab tests the team has access to as a paginated list.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPaginatedLabTestsRequest{
        LabTestLimit: junctiongo.Int(
            1,
        ),
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        GenerationMethod: junctiongo.LabTestGenerationMethodFilterAuto.Ptr(),
        LabSlug: junctiongo.String(
            "lab_slug",
        ),
        CollectionMethod: junctiongo.LabTestCollectionMethodTestkit.Ptr(),
        Status: junctiongo.LabTestStatusActive.Ptr(),
        MarkerIds: []*int{
            junctiongo.Int(
                1,
            ),
        },
        ProviderIds: []*string{
            junctiongo.String(
                "provider_ids",
            ),
        },
        Name: junctiongo.String(
            "name",
        ),
        OrderKey: junctiongo.GetPaginatedLabTestsRequestOrderKeyPrice.Ptr(),
        OrderDirection: junctiongo.GetPaginatedLabTestsRequestOrderDirectionAsc.Ptr(),
    }
client.LabTests.GetPaginated(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labTestLimit:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**generationMethod:** `*junctiongo.LabTestGenerationMethodFilter` — Filter on whether auto-generated lab tests created by Vital, manually created lab tests, or all lab tests should be returned.
    
</dd>
</dl>

<dl>
<dd>

**labSlug:** `*string` — Filter by the slug of the lab for these lab tests.
    
</dd>
</dl>

<dl>
<dd>

**collectionMethod:** `*junctiongo.LabTestCollectionMethod` — Filter by the collection method for these lab tests.
    
</dd>
</dl>

<dl>
<dd>

**status:** `*junctiongo.LabTestStatus` — Filter by the status of these lab tests.
    
</dd>
</dl>

<dl>
<dd>

**markerIds:** `*int` — Filter to only include lab tests containing these marker IDs.
    
</dd>
</dl>

<dl>
<dd>

**providerIds:** `*string` — Filter to only include lab tests containing these provider IDs.
    
</dd>
</dl>

<dl>
<dd>

**name:** `*string` — Filter by the name of the lab test (a case-insensitive substring search).
    
</dd>
</dl>

<dl>
<dd>

**orderKey:** `*junctiongo.GetPaginatedLabTestsRequestOrderKey` 
    
</dd>
</dl>

<dl>
<dd>

**orderDirection:** `*junctiongo.GetPaginatedLabTestsRequestOrderDirection` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetLabTestCollectionInstructionPdf(LabTestId) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetLabTestCollectionInstructionPdfLabTestsRequest{
        LabTestId: "lab_test_id",
    }
client.LabTests.GetLabTestCollectionInstructionPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labTestId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetOrders() -> *junctiongo.GetOrdersResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET many orders with filters.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetOrdersLabTestsRequest{
        SearchInput: junctiongo.String(
            "search_input",
        ),
        StartDate: junctiongo.Time(
            junctiongo.MustParseDateTime(
                "2024-01-15T09:30:00Z",
            ),
        ),
        EndDate: junctiongo.Time(
            junctiongo.MustParseDateTime(
                "2024-01-15T09:30:00Z",
            ),
        ),
        UpdatedStartDate: junctiongo.Time(
            junctiongo.MustParseDateTime(
                "2024-01-15T09:30:00Z",
            ),
        ),
        UpdatedEndDate: junctiongo.Time(
            junctiongo.MustParseDateTime(
                "2024-01-15T09:30:00Z",
            ),
        ),
        Status: []*junctiongo.OrderLowLevelStatus{
            junctiongo.OrderLowLevelStatusOrdered.Ptr(),
        },
        OrderKey: junctiongo.GetOrdersLabTestsRequestOrderKeyCreatedAt.Ptr(),
        OrderDirection: junctiongo.GetOrdersLabTestsRequestOrderDirectionAsc.Ptr(),
        OrderType: []*junctiongo.LabTestCollectionMethod{
            junctiongo.LabTestCollectionMethodTestkit.Ptr(),
        },
        IsCritical: junctiongo.Bool(
            true,
        ),
        Interpretation: junctiongo.InterpretationNormal.Ptr(),
        OrderActivationTypes: []*junctiongo.OrderActivationType{
            junctiongo.OrderActivationTypeCurrent.Ptr(),
        },
        UserId: junctiongo.String(
            "user_id",
        ),
        PatientName: junctiongo.String(
            "patient_name",
        ),
        ShippingRecipientName: junctiongo.String(
            "shipping_recipient_name",
        ),
        OrderIds: []*string{
            junctiongo.String(
                "order_ids",
            ),
        },
        OrderTransactionId: junctiongo.String(
            "order_transaction_id",
        ),
        Page: junctiongo.Int(
            1,
        ),
        Size: junctiongo.Int(
            1,
        ),
    }
client.LabTests.GetOrders(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**searchInput:** `*string` — Search by order id, user id, patient name, shipping dob, or shipping recipient name.
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `*time.Time` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**endDate:** `*time.Time` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 23:59:59
    
</dd>
</dl>

<dl>
<dd>

**updatedStartDate:** `*time.Time` — Date from in YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**updatedEndDate:** `*time.Time` — Date to YYYY-MM-DD or ISO formatted date time. If a date is provided without a time, the time will be set to 00:00:00
    
</dd>
</dl>

<dl>
<dd>

**status:** `*junctiongo.OrderLowLevelStatus` — Filter by low level status.
    
</dd>
</dl>

<dl>
<dd>

**orderKey:** `*junctiongo.GetOrdersLabTestsRequestOrderKey` — Order key to sort by.
    
</dd>
</dl>

<dl>
<dd>

**orderDirection:** `*junctiongo.GetOrdersLabTestsRequestOrderDirection` — Order direction to sort by.
    
</dd>
</dl>

<dl>
<dd>

**orderType:** `*junctiongo.LabTestCollectionMethod` — Filter by method used to perform the lab test.
    
</dd>
</dl>

<dl>
<dd>

**isCritical:** `*bool` — Filter by critical order status.
    
</dd>
</dl>

<dl>
<dd>

**interpretation:** `*junctiongo.Interpretation` — Filter by result interpretation of the lab test.
    
</dd>
</dl>

<dl>
<dd>

**orderActivationTypes:** `*junctiongo.OrderActivationType` — Filter by activation type.
    
</dd>
</dl>

<dl>
<dd>

**userId:** `*string` — Filter by user ID.
    
</dd>
</dl>

<dl>
<dd>

**patientName:** `*string` — Filter by patient name.
    
</dd>
</dl>

<dl>
<dd>

**shippingRecipientName:** `*string` — Filter by shipping recipient name.
    
</dd>
</dl>

<dl>
<dd>

**orderIds:** `*string` — Filter by order ids.
    
</dd>
</dl>

<dl>
<dd>

**orderTransactionId:** `*string` — Filter by order transaction ID
    
</dd>
</dl>

<dl>
<dd>

**page:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**size:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPhlebotomyAppointmentAvailability(request) -> *junctiongo.AppointmentAvailabilitySlots</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return the available time slots to book an appointment with a phlebotomist
for the given address and order.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPhlebotomyAppointmentAvailabilityLabTestsRequest{
        StartDate: junctiongo.String(
            "start_date",
        ),
        Body: &junctiongo.UsAddress{
            FirstLine: "first_line",
            City: "city",
            State: "state",
            ZipCode: "zip_code",
        },
    }
client.LabTests.GetPhlebotomyAppointmentAvailability(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**startDate:** `*string` — Start date for appointment availability
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.UsAddress` — At-home phlebotomy appointment address.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.BookPhlebotomyAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Book an at-home phlebotomy appointment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BookPhlebotomyAppointmentLabTestsRequest{
        OrderId: "order_id",
        Body: &junctiongo.AppointmentBookingRequest{
            BookingKey: "booking_key",
        },
    }
client.LabTests.BookPhlebotomyAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.AppointmentBookingRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.RequestPhlebotomyAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Request an at-home phlebotomy appointment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.RequestAppointmentRequest{
        OrderId: "order_id",
        Address: &junctiongo.UsAddress{
            FirstLine: "first_line",
            City: "city",
            State: "state",
            ZipCode: "zip_code",
        },
        Provider: junctiongo.AppointmentProviderGetlabs,
    }
client.LabTests.RequestPhlebotomyAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**address:** `*junctiongo.UsAddress` — At-home phlebotomy appointment address.
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.AppointmentProvider` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**appointmentNotes:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.ReschedulePhlebotomyAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Reschedule a previously booked at-home phlebotomy appointment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ReschedulePhlebotomyAppointmentLabTestsRequest{
        OrderId: "order_id",
        Body: &junctiongo.AppointmentRescheduleRequest{
            BookingKey: "booking_key",
        },
    }
client.LabTests.ReschedulePhlebotomyAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.AppointmentRescheduleRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.CancelPhlebotomyAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Cancel a previously booked at-home phlebotomy appointment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ApiApiV1EndpointsVitalApiLabTestingOrdersHelpersAppointmentCancelRequest{
        OrderId: "order_id",
        CancellationReasonId: "cancellation_reason_id",
    }
client.LabTests.CancelPhlebotomyAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**cancellationReasonId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**notes:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPhlebotomyAppointmentCancellationReason() -> []*junctiongo.ClientFacingAppointmentCancellationReason</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the list of reasons for cancelling an at-home phlebotomy appointment.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.LabTests.GetPhlebotomyAppointmentCancellationReason(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPhlebotomyAppointment(OrderId) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the appointment associated with an order.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPhlebotomyAppointmentLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetPhlebotomyAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetAreaInfo() -> *junctiongo.AreaInfo</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET information about an area with respect to lab-testing.

Information returned:
* Whether a given zip code is served by our Phlebotomy network.
* List of Lab locations in the area.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetAreaInfoLabTestsRequest{
        ZipCode: "zip_code",
        Radius: junctiongo.AllowedRadiusTen.Ptr(),
        Lab: junctiongo.ClientFacingLabsQuest.Ptr(),
        Labs: []*junctiongo.ClientFacingLabs{
            junctiongo.ClientFacingLabsQuest.Ptr(),
        },
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
    }
client.LabTests.GetAreaInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zipCode:** `string` — Zip code of the area to check
    
</dd>
</dl>

<dl>
<dd>

**radius:** `*junctiongo.AllowedRadius` — Radius in which to search in miles
    
</dd>
</dl>

<dl>
<dd>

**lab:** `*junctiongo.ClientFacingLabs` — Lab to check for PSCs
    
</dd>
</dl>

<dl>
<dd>

**labs:** `*junctiongo.ClientFacingLabs` — List of labs to check for PSCs
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` — Lab Account ID to use for availability checks
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPscInfo() -> *junctiongo.PscInfo</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPscInfoLabTestsRequest{
        ZipCode: "zip_code",
        LabId: 1,
        Radius: junctiongo.AllowedRadiusTen.Ptr(),
        Capabilities: []*junctiongo.LabLocationCapability{
            junctiongo.LabLocationCapabilityStat.Ptr(),
        },
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
    }
client.LabTests.GetPscInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**zipCode:** `string` — Zip code of the area to check
    
</dd>
</dl>

<dl>
<dd>

**labId:** `int` — Lab ID to check for PSCs
    
</dd>
</dl>

<dl>
<dd>

**radius:** `*junctiongo.AllowedRadius` — Radius in which to search in miles. Note that we limit to 30 PSCs.
    
</dd>
</dl>

<dl>
<dd>

**capabilities:** `*junctiongo.LabLocationCapability` — Filter for only locations with certain capabilities
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` — Lab Account ID to use for availability checks
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetOrderPscInfo(OrderId) -> *junctiongo.PscInfo</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetOrderPscInfoLabTestsRequest{
        OrderId: "order_id",
        Radius: junctiongo.AllowedRadiusTen.Ptr(),
        Capabilities: []*junctiongo.LabLocationCapability{
            junctiongo.LabLocationCapabilityStat.Ptr(),
        },
    }
client.LabTests.GetOrderPscInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**radius:** `*junctiongo.AllowedRadius` — Radius in which to search in miles
    
</dd>
</dl>

<dl>
<dd>

**capabilities:** `*junctiongo.LabLocationCapability` — Filter for only locations with certain capabilities
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetResultPdf(OrderId) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint returns the lab results for the order.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetResultPdfLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetResultPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetResultMetadata(OrderId) -> *junctiongo.LabResultsMetadata</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return metadata related to order results, such as lab metadata,
provider and sample dates.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetResultMetadataLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetResultMetadata(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetResultRaw(OrderId) -> *junctiongo.LabResultsRaw</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Return both metadata and raw json test data
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetResultRawLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetResultRaw(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetLabelsPdf(OrderId) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

This endpoint returns the printed labels for the order.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetLabelsPdfLabTestsRequest{
        OrderId: "order_id",
        CollectionDate: junctiongo.MustParseDateTime(
            "2024-01-15T09:30:00Z",
        ),
    }
client.LabTests.GetLabelsPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**numberOfLabels:** `*int` — Number of labels to generate
    
</dd>
</dl>

<dl>
<dd>

**collectionDate:** `time.Time` — Collection date
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPscAppointmentAvailability() -> *junctiongo.AppointmentAvailabilitySlots</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPscAppointmentAvailabilityLabTestsRequest{
        Lab: junctiongo.AppointmentPscLabsQuest,
        StartDate: junctiongo.String(
            "start_date",
        ),
        SiteCodes: []*string{
            junctiongo.String(
                "site_codes",
            ),
        },
        ZipCode: junctiongo.String(
            "zip_code",
        ),
        Radius: junctiongo.AllowedRadiusTen.Ptr(),
        AllowStale: junctiongo.Bool(
            true,
        ),
    }
client.LabTests.GetPscAppointmentAvailability(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**lab:** `*junctiongo.AppointmentPscLabs` — Lab to check for availability
    
</dd>
</dl>

<dl>
<dd>

**startDate:** `*string` — Start date for appointment availability
    
</dd>
</dl>

<dl>
<dd>

**siteCodes:** `*string` — List of site codes to fetch availability for
    
</dd>
</dl>

<dl>
<dd>

**zipCode:** `*string` — Zip code of the area to check
    
</dd>
</dl>

<dl>
<dd>

**radius:** `*junctiongo.AllowedRadius` — Radius in which to search in miles
    
</dd>
</dl>

<dl>
<dd>

**allowStale:** `*bool` — If true, allows cached availability data to be returned.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.BookPscAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.BookPscAppointmentLabTestsRequest{
        OrderId: "order_id",
        Body: &junctiongo.AppointmentBookingRequest{
            BookingKey: "booking_key",
        },
    }
client.LabTests.BookPscAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**idempotencyKey:** `*string` — [!] This feature (Idempotency Key) is under closed beta. Idempotency Key support for booking PSC appointment.
    
</dd>
</dl>

<dl>
<dd>

**idempotencyError:** `*string` — If `no-cache`, applies idempotency only to successful outcomes.
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.AppointmentBookingRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.ReschedulePscAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ReschedulePscAppointmentLabTestsRequest{
        OrderId: "order_id",
        Body: &junctiongo.AppointmentRescheduleRequest{
            BookingKey: "booking_key",
        },
    }
client.LabTests.ReschedulePscAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.AppointmentRescheduleRequest` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.CancelPscAppointment(OrderId, request) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.VitalCoreClientsLabTestGetlabsSchemaAppointmentCancelRequest{
        OrderId: "order_id",
        CancellationReasonId: "cancellationReasonId",
    }
client.LabTests.CancelPscAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**cancellationReasonId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**note:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPscAppointmentCancellationReason() -> []*junctiongo.ClientFacingAppointmentCancellationReason</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
client.LabTests.GetPscAppointmentCancellationReason(
        context.TODO(),
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetPscAppointment(OrderId) -> *junctiongo.ClientFacingAppointment</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get the appointment associated with an order.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetPscAppointmentLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetPscAppointment(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetOrderCollectionInstructionPdf(OrderId) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET collection instructions for an order
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetOrderCollectionInstructionPdfLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetOrderCollectionInstructionPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetOrderRequistionPdf(OrderId) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET requisition pdf for an order
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetOrderRequistionPdfLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetOrderRequistionPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetOrderAbnPdf(OrderId) -> string</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET ABN pdf for an order
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetOrderAbnPdfLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetOrderAbnPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.GetOrder(OrderId) -> *junctiongo.ClientFacingOrder</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

GET individual order by ID.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetOrderLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.GetOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.UpdateOrder(OrderId, request) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update a modifiable order's scheduled activation date.

The order must be in `ordered` or `awaiting_registration` status. Setting
`activate_by` to a future date reschedules dispatch; setting it to `null`
clears the schedule and enqueues immediate dispatch for `ordered` orders.

Returns 400 when:
- the order is not in a modifiable status,
- the order was created for immediate processing (cannot be scheduled
  after the fact),
- `activate_by` is in the past.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UpdateOrderBody{
        OrderId: "order_id",
    }
client.LabTests.UpdateOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>

<dl>
<dd>

**activateBy:** `*string` — The date on which the order should be activated (dispatched to the lab). Must be today or a future date. Set to `null` to clear an existing scheduled date and dispatch the order immediately. Note: an order originally created for immediate processing (no `activate_by` at creation time) cannot be rescheduled — only orders that were created with an `activate_by` can have it changed or cleared.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.CreateOrder(request) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreateOrderRequestCompatible{
        UserId: "user_id",
        PatientDetails: &junctiongo.PatientDetailsWithValidation{
            FirstName: "first_name",
            LastName: "last_name",
            Dob: "dob",
            Gender: junctiongo.GenderFemale,
            PhoneNumber: "phone_number",
            Email: "email",
        },
        PatientAddress: &junctiongo.PatientAddressWithValidation{
            FirstLine: "first_line",
            City: "city",
            State: "state",
            Zip: "zip",
            Country: "country",
        },
    }
client.LabTests.CreateOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**idempotencyKey:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**idempotencyError:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**labTestId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**orderSet:** `*junctiongo.OrderSetRequest` 
    
</dd>
</dl>

<dl>
<dd>

**collectionMethod:** `*junctiongo.LabTestCollectionMethod` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**physician:** `*junctiongo.PhysicianCreateRequest` 
    
</dd>
</dl>

<dl>
<dd>

**healthInsurance:** `*junctiongo.HealthInsuranceCreateRequest` 
    
</dd>
</dl>

<dl>
<dd>

**priority:** `*bool` — Defines whether order is priority or not. For some labs, this refers to a STAT order.
    
</dd>
</dl>

<dl>
<dd>

**billingType:** `*junctiongo.Billing` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**icdCodes:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**consents:** `[]*junctiongo.Consent` 
    
</dd>
</dl>

<dl>
<dd>

**activateBy:** `*string` — Schedule an Order to be processed in a future date.
    
</dd>
</dl>

<dl>
<dd>

**aoeAnswers:** `[]*junctiongo.AoEAnswer` 
    
</dd>
</dl>

<dl>
<dd>

**passthrough:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**clinicalNotes:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**creatorMemberId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**patientDetails:** `*junctiongo.PatientDetailsWithValidation` 
    
</dd>
</dl>

<dl>
<dd>

**patientAddress:** `*junctiongo.PatientAddressWithValidation` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.ImportOrder(request) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ImportOrderBody{
        UserId: "user_id",
        BillingType: junctiongo.BillingClientBill,
        OrderSet: &junctiongo.OrderSetRequest{},
        CollectionMethod: junctiongo.LabTestCollectionMethodTestkit,
        PatientDetails: &junctiongo.PatientDetailsWithValidation{
            FirstName: "first_name",
            LastName: "last_name",
            Dob: "dob",
            Gender: junctiongo.GenderFemale,
            PhoneNumber: "phone_number",
            Email: "email",
        },
        PatientAddress: &junctiongo.PatientAddress{
            ReceiverName: "receiver_name",
            FirstLine: "first_line",
            City: "city",
            State: "state",
            Zip: "zip",
            Country: "country",
        },
        SampleId: "sample_id",
    }
client.LabTests.ImportOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**billingType:** `*junctiongo.Billing` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**orderSet:** `*junctiongo.OrderSetRequest` 
    
</dd>
</dl>

<dl>
<dd>

**collectionMethod:** `*junctiongo.LabTestCollectionMethod` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**physician:** `*junctiongo.PhysicianCreateRequest` 
    
</dd>
</dl>

<dl>
<dd>

**patientDetails:** `*junctiongo.PatientDetailsWithValidation` 
    
</dd>
</dl>

<dl>
<dd>

**patientAddress:** `*junctiongo.PatientAddress` 
    
</dd>
</dl>

<dl>
<dd>

**sampleId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.CancelOrder(OrderId) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

POST cancel order
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CancelOrderLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.CancelOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.SimulateOrderProcess(OrderId, request) -> any</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Get available test kits.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.SimulateOrderProcessLabTestsRequest{
        OrderId: "order_id",
        FinalStatus: junctiongo.OrderStatusReceivedWalkInTestOrdered.Ptr(),
        Delay: junctiongo.Int(
            1,
        ),
        Body: &junctiongo.SimulationFlags{},
    }
client.LabTests.SimulateOrderProcess(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**finalStatus:** `*junctiongo.OrderStatus` 
    
</dd>
</dl>

<dl>
<dd>

**delay:** `*int` 
    
</dd>
</dl>

<dl>
<dd>

**request:** `*junctiongo.SimulationFlags` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.UpdateOnSiteCollectionOrderDrawCompleted(OrderId) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

PATCH update on site collection order when draw is completed
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.UpdateOnSiteCollectionOrderDrawCompletedLabTestsRequest{
        OrderId: "order_id",
    }
client.LabTests.UpdateOnSiteCollectionOrderDrawCompleted(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderId:** `string` — Your Order ID.
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabTests.ValidateIcdCodes(request) -> *junctiongo.ValidateIcdCodesResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ValidateIcdCodesBody{
        Codes: []string{
            "codes",
        },
    }
client.LabTests.ValidateIcdCodes(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**codes:** `[]string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Compendium
<details><summary><code>client.Compendium.Search(request) -> *junctiongo.SearchCompendiumResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.SearchCompendiumBody{
        Mode: junctiongo.SearchModeCanonical,
    }
client.Compendium.Search(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**mode:** `*junctiongo.SearchMode` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**query:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**cptCodes:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**loincSetHash:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**labs:** `[]*junctiongo.CompendiumSearchLabs` 
    
</dd>
</dl>

<dl>
<dd>

**includeRelated:** `*bool` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Compendium.Convert(request) -> *junctiongo.ConvertCompendiumResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ConvertCompendiumBody{
        TargetLab: junctiongo.CompendiumSearchLabsLabcorp,
    }
client.Compendium.Convert(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labTestId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**providerIds:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**targetLab:** `*junctiongo.CompendiumSearchLabs` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## LabAccount
<details><summary><code>client.LabAccount.GetTeamLabAccounts() -> *junctiongo.GetTeamLabAccountsResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetTeamLabAccountsLabAccountRequest{
        LabAccountId: junctiongo.String(
            "lab_account_id",
        ),
        Status: junctiongo.LabAccountStatusActive.Ptr(),
    }
client.LabAccount.GetTeamLabAccounts(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**labAccountId:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**status:** `*junctiongo.LabAccountStatus` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## OrderTransaction
<details><summary><code>client.OrderTransaction.GetTransaction(TransactionId) -> *junctiongo.GetOrderTransactionResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetTransactionOrderTransactionRequest{
        TransactionId: "transaction_id",
    }
client.OrderTransaction.GetTransaction(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**transactionId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.OrderTransaction.GetTransactionResult(TransactionId) -> *junctiongo.LabResultsRaw</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetTransactionResultOrderTransactionRequest{
        TransactionId: "transaction_id",
    }
client.OrderTransaction.GetTransactionResult(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**transactionId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.OrderTransaction.GetTransactionResultPdf(TransactionId) -> string</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetTransactionResultPdfOrderTransactionRequest{
        TransactionId: "transaction_id",
    }
client.OrderTransaction.GetTransactionResultPdf(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**transactionId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Testkit
<details><summary><code>client.Testkit.Register(request) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.RegisterTestkitRequest{
        SampleId: "sample_id",
        PatientDetails: &junctiongo.PatientDetailsWithValidation{
            FirstName: "first_name",
            LastName: "last_name",
            Dob: "dob",
            Gender: junctiongo.GenderFemale,
            PhoneNumber: "phone_number",
            Email: "email",
        },
        PatientAddress: &junctiongo.PatientAddressWithValidation{
            FirstLine: "first_line",
            City: "city",
            State: "state",
            Zip: "zip",
            Country: "country",
        },
    }
client.Testkit.Register(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `*string` — The user ID of the patient.
    
</dd>
</dl>

<dl>
<dd>

**sampleId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**patientDetails:** `*junctiongo.PatientDetailsWithValidation` 
    
</dd>
</dl>

<dl>
<dd>

**patientAddress:** `*junctiongo.PatientAddressWithValidation` 
    
</dd>
</dl>

<dl>
<dd>

**physician:** `*junctiongo.PhysicianCreateRequestBase` 
    
</dd>
</dl>

<dl>
<dd>

**healthInsurance:** `*junctiongo.HealthInsuranceCreateRequest` 
    
</dd>
</dl>

<dl>
<dd>

**consents:** `[]*junctiongo.Consent` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Testkit.CreateOrder(request) -> *junctiongo.PostOrderResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates an order for an unregistered testkit
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreateRegistrableTestkitOrderRequest{
        UserId: "user_id",
        LabTestId: "lab_test_id",
        ShippingDetails: &junctiongo.ShippingAddressWithValidation{
            ReceiverName: "receiver_name",
            FirstLine: "first_line",
            City: "city",
            State: "state",
            Zip: "zip",
            Country: "country",
            PhoneNumber: "phone_number",
        },
    }
client.Testkit.CreateOrder(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**labTestId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**shippingDetails:** `*junctiongo.ShippingAddressWithValidation` 
    
</dd>
</dl>

<dl>
<dd>

**passthrough:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**labAccountId:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Order
<details><summary><code>client.Order.ResendEvents(request) -> *junctiongo.ResendWebhookResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Replay a webhook for a given set of orders
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ResendWebhookBody{}
client.Order.ResendEvents(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**orderIds:** `[]string` 
    
</dd>
</dl>

<dl>
<dd>

**startAt:** `*time.Time` 
    
</dd>
</dl>

<dl>
<dd>

**endAt:** `*time.Time` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Insurance
<details><summary><code>client.Insurance.SearchGetPayorInfo() -> []*junctiongo.ClientFacingPayorSearchResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.SearchGetPayorInfoInsuranceRequest{
        InsuranceName: junctiongo.String(
            "insurance_name",
        ),
        Provider: junctiongo.PayorCodeExternalProviderChangeHealthcare.Ptr(),
        ProviderPayorId: junctiongo.String(
            "provider_payor_id",
        ),
    }
client.Insurance.SearchGetPayorInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**insuranceName:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.PayorCodeExternalProvider` 
    
</dd>
</dl>

<dl>
<dd>

**providerPayorId:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Insurance.SearchPayorInfo(request) -> []*junctiongo.ClientFacingPayorSearchResponseDeprecated</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.PayorSearchRequest{}
client.Insurance.SearchPayorInfo(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**insuranceName:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.PayorCodeExternalProvider` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**providerId:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Insurance.SearchDiagnosis() -> []*junctiongo.ClientFacingDiagnosisInformation</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.SearchDiagnosisInsuranceRequest{
        DiagnosisQuery: "diagnosis_query",
    }
client.Insurance.SearchDiagnosis(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**diagnosisQuery:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Payor
<details><summary><code>client.Payor.CreatePayor(request) -> *junctiongo.ClientFacingPayor</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreatePayorBody{
        Name: "name",
        Address: &junctiongo.Address{
            FirstLine: "first_line",
            Country: "country",
            Zip: "zip",
            City: "city",
            State: "state",
        },
    }
client.Payor.CreatePayor(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**name:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**address:** `*junctiongo.Address` 
    
</dd>
</dl>

<dl>
<dd>

**provider:** `*junctiongo.PayorCodeExternalProvider` — ℹ️ This enum is non-exhaustive.
    
</dd>
</dl>

<dl>
<dd>

**providerPayorId:** `*string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## LabReport
<details><summary><code>client.LabReport.ParserCreateJob(request) -> *junctiongo.ParsingJob</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Creates a parse job, uploads the file(s) to provider, persists the job row,
and starts the ParseLabReport. Returns a generated job_id.
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.CreateLabReportParserJobBody{
        UserId: "user_id",
    }
client.LabReport.ParserCreateJob(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.LabReport.ParserGetJob(JobId) -> *junctiongo.ParsingJob</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieves the parse job status and stored result if completed.

Returns:
    ParseLabResultJobResponse with job status and parsed data (if complete)
</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.ParserGetJobLabReportRequest{
        JobId: "job_id",
    }
client.LabReport.ParserGetJob(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**jobId:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

## Aggregate
<details><summary><code>client.Aggregate.QueryOne(UserId, request) -> *junctiongo.AggregationResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.QueryBatch{
        UserId: "user_id",
        Timeframe: &junctiongo.QueryBatchTimeframe{
            RelativeTimeframe: &junctiongo.RelativeTimeframe{
                Anchor: "anchor",
                Past: &junctiongo.Period{
                    Unit: junctiongo.PeriodUnitMinute,
                },
            },
        },
        Queries: []*junctiongo.Query{
            &junctiongo.Query{
                Select: []*junctiongo.QuerySelectItem{
                    &junctiongo.QuerySelectItem{
                        AggregateExpr: &junctiongo.AggregateExpr{
                            Arg: &junctiongo.AggregateExprArg{
                                SleepColumnExpr: &junctiongo.SleepColumnExpr{
                                    Sleep: junctiongo.SleepColumnExprSleepId,
                                },
                            },
                            Func: junctiongo.AggregateExprFuncMean,
                        },
                    },
                },
            },
        },
    }
client.Aggregate.QueryOne(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**accept:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**timeframe:** `*junctiongo.QueryBatchTimeframe` 
    
</dd>
</dl>

<dl>
<dd>

**queries:** `[]*junctiongo.Query` 
    
</dd>
</dl>

<dl>
<dd>

**config:** `*junctiongo.QueryConfig` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Aggregate.GetResultTableForContinuousQuery(UserId, QueryIdOrSlug) -> *junctiongo.AggregationResult</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetResultTableForContinuousQueryAggregateRequest{
        UserId: "user_id",
        QueryIdOrSlug: "query_id_or_slug",
    }
client.Aggregate.GetResultTableForContinuousQuery(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**queryIdOrSlug:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**accept:** `string` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

<details><summary><code>client.Aggregate.GetTaskHistoryForContinuousQuery(UserId, QueryIdOrSlug) -> *junctiongo.ContinuousQueryTaskHistoryResponse</code></summary>
<dl>
<dd>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```go
request := &junctiongo.GetTaskHistoryForContinuousQueryAggregateRequest{
        UserId: "user_id",
        QueryIdOrSlug: "query_id_or_slug",
        NextCursor: junctiongo.String(
            "next_cursor",
        ),
        Limit: junctiongo.Int(
            1,
        ),
    }
client.Aggregate.GetTaskHistoryForContinuousQuery(
        context.TODO(),
        request,
    )
}
```
</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**userId:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**queryIdOrSlug:** `string` 
    
</dd>
</dl>

<dl>
<dd>

**nextCursor:** `*string` 
    
</dd>
</dl>

<dl>
<dd>

**limit:** `*int` 
    
</dd>
</dl>
</dd>
</dl>


</dd>
</dl>
</details>

