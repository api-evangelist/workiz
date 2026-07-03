# Workiz (workiz)

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
