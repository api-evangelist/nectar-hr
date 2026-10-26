# Nectar (nectar-hr)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
