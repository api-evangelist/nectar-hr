# Nectar (nectar-hr)

Nectar is an employee recognition and rewards platform that helps organizations build culture through peer-to-peer and manager recognition, a points-based global rewards catalog (200+ gift cards, direct Amazon integration, branded swag, and custom company rewards), automated milestone celebrations for birthdays and work anniversaries, and internal communications.

Nectar exposes a documented **Open API** — the "Nectar Public API" (OpenAPI 3.0.0, version 0.1.0) — with a base URL of `https://api.nectarhr.com`, Swagger UI at [`/docs`](https://api.nectarhr.com/docs), and the raw definition at `/swagger.yaml`. Every endpoint is authenticated with a Bearer (JWT) API key.

**Access is a plan-gated add-on.** The docs and OpenAPI definition are publicly viewable, but live access must be enabled on your Nectar plan by support / your account manager. Once enabled, an admin generates a single scoped API key (with an optional expiration) under **Settings > Integrations**. If the Integrations API section is not visible, API access is not included in the current plan.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/nectar-hr/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/nectar-hr/refs/heads/main/apis.yml)

## Tags

- Employee Recognition
- Rewards
- Points
- HR
- Employee Engagement
- Culture
- People Operations

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Nectar Users API

Read and manage the people in a Nectar company. List users with filters (active, invited, email, employee_id) via cursor pagination, get a single user by ID, and upsert up to 50 users at a time (matched on `nectar_id`, `email`, or `employee_id`) with optional invite sending. Backs HRIS sync and user provisioning.

- **Human URL:** [https://api.nectarhr.com/docs](https://api.nectarhr.com/docs)
- **Base URL:** `https://api.nectarhr.com`
- Endpoints: `GET /v1/users`, `GET /v1/users/{userId}`, `PUT /v1/users`

### Nectar Recognition API

Read the company recognition feed — the stream of peer-to-peer and manager recognitions posted in Nectar — with filtering by type, privacy, leaderboard visibility, and deleted state, plus date-range and cursor-based pagination.

- **Human URL:** [https://api.nectarhr.com/docs](https://api.nectarhr.com/docs)
- **Base URL:** `https://api.nectarhr.com`
- Endpoints: `GET /v1/recognition/feed`

### Nectar Custom Awards API

List a company's configured custom awards and programmatically send a custom award to one or more recipients (valid user UUIDs), with an optional message and point value.

- **Human URL:** [https://api.nectarhr.com/docs](https://api.nectarhr.com/docs)
- **Base URL:** `https://api.nectarhr.com`
- Endpoints: `GET /v1/custom-awards`, `POST /v1/custom-awards/send`

### Nectar Financial Analytics API

Generate a summary of reward redemptions made by all users over a date range (defaulting to the current month to date, capped at a one-year span). Powers financial reporting and reconciliation of points-to-rewards spend.

- **Human URL:** [https://api.nectarhr.com/docs](https://api.nectarhr.com/docs)
- **Base URL:** `https://api.nectarhr.com`
- Endpoints: `GET /v1/analytics/financial/redemptions`

### Nectar Flows API

Enroll users in a Nectar Flow via an API trigger. Users are identified by email or userId and must be valid company members; if any user is not found the request fails without enrolling anyone (all-or-nothing).

- **Human URL:** [https://api.nectarhr.com/docs](https://api.nectarhr.com/docs)
- **Base URL:** `https://api.nectarhr.com`
- Endpoints: `POST /v1/flows/trigger/{triggerId}`

## Authentication

All endpoints require an API key sent as an `Authorization: Bearer <yourAPIKey>` header (JWT). One scoped key is generated per account in Settings > Integrations after access is enabled by Nectar.

## Rate Limits

Nectar documents a ceiling of **50 concurrent calls** per account rather than a published per-minute request quota, plus per-endpoint caps (user upsert of 50 per request, custom-awards page default of 25, and a one-year maximum span on the redemptions report). See [`rate-limits/nectar-hr-rate-limits.yml`](rate-limits/nectar-hr-rate-limits.yml).

## Pricing

Nectar's Recognize product is sold per employee per month (billed annually) with a published annual minimum. Third-party pricing pages report a Plus tier at roughly **$5/employee/month** and a Premium tier at roughly **$6/employee/month** (annual billing), plus custom Enterprise; Nectar's own pricing page is quote-based. The Open API is an add-on enabled on your plan, not a separately metered product. See [`plans/nectar-hr-plans-pricing.yml`](plans/nectar-hr-plans-pricing.yml).

## WebSocket / Realtime

No. Nectar does not publish a documented public WebSocket API. The Nectar Public API is request/response REST over HTTPS; there is no server-push (WebSocket or SSE) transport to model, so no AsyncAPI document was authored. See [`review.yml`](review.yml).

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/nectarhr)
- [Website](https://nectarhr.com)
- [Documentation](https://api.nectarhr.com/docs)
- [Plans](plans/nectar-hr-plans-pricing.yml)
- [Rate Limits](rate-limits/nectar-hr-rate-limits.yml)
- [Fin Ops](finops/nectar-hr-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
