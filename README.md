# Workiz (workiz)

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

Workiz is field service management (FSM) software for home-service businesses - HVAC, plumbing, electrical, appliance repair, garage doors, locksmiths, carpet cleaning, and similar trades. It combines scheduling and dispatch, a CRM, jobs and leads, estimates and invoicing, payments, and communications (calls, SMS, email) in one platform. Workiz exposes a documented REST API (the Developer API add-on) for reading and writing jobs, leads, team members, time off, and payments, plus outbound webhooks for new-job and new-lead events. All calls are made to `https://api.workiz.com/api/v1/` with the account API token embedded in the request path.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/workiz/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/workiz/refs/heads/main/apis.yml)

## Authentication

Enable the **Developer API** add-on from the Workiz Feature Center / Marketplace, then copy the API token and secret from **Settings > Integrations**. The API token is placed directly in the request path (`https://api.workiz.com/api/v1/{api_token}/...`) - there is no `Authorization` header. Responses are JSON and HTTP status codes signal errors.

## Tags

- Field Service Management
- FSM
- Home Services
- Scheduling
- Dispatch
- CRM
- Jobs
- Invoicing

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Workiz Jobs API

List and retrieve jobs, create and update jobs, and assign or unassign team members to a job. Jobs are the core work order in Workiz and carry the client details, location, scheduled time, line items, status, and assigned crew. List queries support filters such as `records`, `offset`, `only_open`, and `status`.

- **Human URL:** [https://developer.workiz.com/](https://developer.workiz.com/)
- **Base URL:** `https://api.workiz.com/api/v1`

#### Tags

- Jobs
- Scheduling
- Dispatch

#### Properties

- [Documentation](https://developer.workiz.com/)
- [API Reference](https://developer.workiz.com/)
- [OpenAPI](openapi/workiz-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/workiz.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/workiz.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Workiz Leads API

List and retrieve leads and manage their lifecycle - create and update leads and mark a lead as active or lost. Leads are prospective work that can be converted into jobs. List and single-record reads are confirmed in the public API; write and status-change operations are exposed through Workiz integration partners and modeled here.

- **Human URL:** [https://developer.workiz.com/](https://developer.workiz.com/)
- **Base URL:** `https://api.workiz.com/api/v1`

#### Tags

- Leads
- CRM
- Sales

#### Properties

- [Documentation](https://developer.workiz.com/)
- [OpenAPI](openapi/workiz-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/workiz.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/workiz.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Workiz Team API

List team members (technicians, dispatchers, and office users) and retrieve a single team member by user ID. Team members are the users you assign to jobs and whose availability and time off drive scheduling.

- **Human URL:** [https://developer.workiz.com/](https://developer.workiz.com/)
- **Base URL:** `https://api.workiz.com/api/v1`

#### Tags

- Team
- Technicians
- Users

#### Properties

- [Documentation](https://developer.workiz.com/)
- [OpenAPI](openapi/workiz-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/workiz.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/workiz.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Workiz Time Off API

Retrieve time-off records for the account or for a specific user by name. Time off blocks a technician's availability and is a scheduling input for dispatch and job assignment.

- **Human URL:** [https://developer.workiz.com/](https://developer.workiz.com/)
- **Base URL:** `https://api.workiz.com/api/v1`

#### Tags

- Time Off
- Availability
- Scheduling

#### Properties

- [Documentation](https://developer.workiz.com/)
- [OpenAPI](openapi/workiz-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/workiz.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/workiz.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Workiz Payments API

Record a payment against a job by its UUID. Workiz tracks invoices, estimates, and payments against jobs; the public API surfaces adding a payment to a job, which advances the job toward a paid state.

- **Human URL:** [https://developer.workiz.com/](https://developer.workiz.com/)
- **Base URL:** `https://api.workiz.com/api/v1`

#### Tags

- Payments
- Invoicing
- Billing

#### Properties

- [Documentation](https://developer.workiz.com/)
- [OpenAPI](openapi/workiz-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/workiz.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/workiz.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Workiz Webhooks

Outbound webhooks that push events to a configured HTTPS endpoint when a new job is created or a new lead arrives, enabling near-real-time integrations without polling. Workiz posts the event payload to your URL. This is server-to-endpoint HTTP delivery, not a WebSocket. Webhook subscription is offered through the Developer API add-on and Workiz integration partners; the endpoint payloads are modeled here.

- **Human URL:** [https://developer.workiz.com/](https://developer.workiz.com/)
- **Base URL:** `https://api.workiz.com/api/v1`

#### Tags

- Webhooks
- Events
- Notifications

#### Properties

- [Documentation](https://developer.workiz.com/)
- [OpenAPI](openapi/workiz-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/workiz)
- [Website](https://www.workiz.com)
- [Documentation](https://developer.workiz.com/)
- [Plans](plans/workiz-plans-pricing.yml)
- [Rate Limits](rate-limits/workiz-rate-limits.yml)
- [Fin Ops](finops/workiz-finops.yml)

## Review

A WebSocket review ([review.yml](review.yml)) found that Workiz does **not** expose a documented public WebSocket API. Its public surface is token-in-path REST plus outbound HTTPS webhooks for new-job and new-lead events. No AsyncAPI document was authored because there is no server-push WebSocket or SSE transport on Workiz's own API to model.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
