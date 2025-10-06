<div align="center">

<h2>Okta Endpoints</h2>

</div>

### 🔑 Core Authorization & Token Endpoints

#### Authorization Endpoint

```
/oauth2/default/v1/authorize
```

#### Token Endpoint

```
/oauth2/default/v1/token
```

#### Revoke Token

```
/oauth2/default/v1/revoke
```

#### Introspection Endpoint

```
/oauth2/default/v1/introspect
```

### 👤 User Info & Session Management

#### UserInfo Endpoint

```
/oauth2/default/v1/userinfo
```

#### Logout Endpoint (end-session)

```
/oauth2/default/v1/logout
```

#### Session API

```
/api/v1/sessions
```

### 📖 Discovery (Well-Known Endpoints)

#### OIDC Discovery

```swift
/.well-known/openid-configuration
/oauth2/default/.well-known/openid-configuration
```

#### OAuth 2.0 Authorization Server Metadata

```pgsql
/.well-known/oauth-authorization-server
```

### 👥 Okta REST API Endpoints (common ones)

#### These exist at:

```
https://<yourOktaDomain>/api/v1/
```

#### Some useful paths:

##### Users:

```
/api/v1/users
/api/v1/users/{id}
```

##### Groups:

```
/api/v1/groups
/api/v1/groups/{id}
```

##### Apps:

```
/api/v1/apps
```

##### Factors (MFA):

```
/api/v1/users/{id}/factors
```

##### Sessions:

```
/api/v1/sessions
```

## All Endpoints

```bash
/.well-known/openid-configuration
/oauth2/default/.well-known/openid-configuration
/.well-known/oauth-authorization-server
/oauth2/default/v1/authorize
/oauth2/default/v1/token
/oauth2/default/v1/revoke
/oauth2/default/v1/introspect
/oauth2/default/v1/userinfo
/oauth2/default/v1/logout
/api/v1/sessions
/api/v1/users
/api/v1/users/{id}
/api/v1/groups
/api/v1/groups/{id}
/api/v1/apps
/api/v1/users/{id}/factors
/oauth2/<authServerId>/v1/authorize
/oauth2/<authServerId>/v1/token
/oauth2/<authServerId>/v1/userinfo
/oauth2/<authServerId>/.well-known/openid-configuration

# Optional for recon/fuzzing (common host variants):

https://<yourOktaDomain>
https://<yourOktaDomain>/oauth2
https://<yourOktaDomain>/api/v1
```

## ✅ Tip for Recon:

If you know a site is using Okta, check:

- HTML/JS references → look for `okta.com`, `oktapreview.com`, or `okta-emea.com`.
- Try hitting `/.well-known/openid-configuration` → it usually reveals all active endpoints.
- Enumerate `/api/v1/...` if API access is exposed (auth required).
