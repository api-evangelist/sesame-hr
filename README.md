# Sesame HR (sesame-hr)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Sesame HR is an all-in-one HR and time-tracking platform used by small and mid-sized companies across Spain, Latin America, and beyond to manage employees, the digital time clock (check-in / check-out), work hours, shifts and scheduling, vacations, absences and leave, contracts, payroll data, and recruitment. The **Sesame Public API (v3)** exposes that same functionality over a documented REST interface, letting teams sync HRIS data with payroll and ERP systems, build custom dashboards, and automate onboarding, shift assignment, and absence-approval workflows.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sesame-hr/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sesame-hr/refs/heads/main/apis.yml)

## Access Model

The Sesame Public API is **public and self-serve for subscribers**. Any company on a paid Sesame HR subscription (or during the 14-day free trial) can generate a **Bearer API token** from the admin panel at `app.sesametime.com` under **Settings > Integrations > API** — there is no separate API application, approval step, or per-call fee.

- **Base host:** `https://api-{region}.sesametime.com` — the host is region-specific (default region `eu1`); your region is shown in the admin settings.
- **Path prefix:** every endpoint is prefixed with `/core/v3` (for example `https://api-eu1.sesametime.com/core/v3/employees`).
- **Authentication:** `Authorization: Bearer YOUR_API_TOKEN`. Verify a token with `GET /core/v3/info`.
- **Rate limit:** 1,000 requests per minute per company, shared across all of that company's tokens (HTTP 429 when exceeded).
- **Docs:** [https://apidocs.sesametime.com/introduction](https://apidocs.sesametime.com/introduction) · OpenAPI: [https://apidocs.sesametime.com/openapi.json](https://apidocs.sesametime.com/openapi.json)

The full API spans roughly 500 endpoints across 30+ resources. This catalog entry models the subset most relevant to HRIS, time-tracking, and workforce-management use cases across five logical APIs. Endpoint paths are taken from the official documentation; some request/response field shapes in the OpenAPI are modeled generically where the public docs do not publish a complete schema.

## Tags

- Human Resources
- HRIS
- Time Tracking
- Workforce Management
- Employee Management
- HR
- Attendance
- Absence Management
- Scheduling
- Payroll

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Sesame HR Employees API

Create, read, update, delete, and list employee records, plus manage the manager relationships, roles, and contribution data attached to each person. The core HRIS resource for syncing your workforce with payroll and ERP systems.

- **Human URL:** [https://apidocs.sesametime.com/introduction](https://apidocs.sesametime.com/introduction)
- **Base URL:** `https://api-eu1.sesametime.com/core/v3`
- **Tags:** Human Resources, HRIS, Employee Management

### Sesame HR Time Tracking API

Clock employees in and out, log and correct work entries and time entries, and read worked-hours analytics (by weekday, night hours, and hours-bag balances). Powers digital time-clock and attendance-reporting workflows.

- **Human URL:** [https://apidocs.sesametime.com/introduction](https://apidocs.sesametime.com/introduction)
- **Base URL:** `https://api-eu1.sesametime.com/core/v3`
- **Tags:** Time Tracking, Attendance, Work Hours

### Sesame HR Absences and Leave API

Manage vacation and absence calendars, create and approve or reject day-off requests, configure vacation policies, and administer holidays and employee leave types across the workforce.

- **Human URL:** [https://apidocs.sesametime.com/introduction](https://apidocs.sesametime.com/introduction)
- **Base URL:** `https://api-eu1.sesametime.com/core/v3`
- **Tags:** Absence Management, Vacations, Leave

### Sesame HR Departments and Org API

Create and manage departments and offices, assign employees to them, and read or update the organization chart (manager-by-employee) that structures the company.

- **Human URL:** [https://apidocs.sesametime.com/introduction](https://apidocs.sesametime.com/introduction)
- **Base URL:** `https://api-eu1.sesametime.com/core/v3`
- **Tags:** Departments, Organization, Workforce Management

### Sesame HR Scheduling and Shifts API

Build shift plans and schedule templates, assign shifts and free days to employees through planners, and manage the recurring schedules that drive workforce management and rota planning.

- **Human URL:** [https://apidocs.sesametime.com/introduction](https://apidocs.sesametime.com/introduction)
- **Base URL:** `https://api-eu1.sesametime.com/core/v3`
- **Tags:** Scheduling, Shifts, Workforce Management

## Artifacts

- [OpenAPI](openapi/sesame-hr-openapi.yml)
- [Postman Collection](collections/sesame-hr.postman_collection.json)
- [Open Collection](collections/sesame-hr.opencollection.json)
- [Authentication](authentication/sesame-hr-authentication.yml)
- [Plans / Pricing](plans/sesame-hr-plans-pricing.yml)
- [Rate Limits](rate-limits/sesame-hr-rate-limits.yml)
- [Fin Ops](finops/sesame-hr-finops.yml)

## Common Properties

- [Website](https://www.sesamehr.com)
- [Documentation](https://apidocs.sesametime.com/introduction)
- [LinkedIn](https://www.linkedin.com/company/sesamehr)
- [Plans](plans/sesame-hr-plans-pricing.yml)
- [Rate Limits](rate-limits/sesame-hr-rate-limits.yml)
- [Fin Ops](finops/sesame-hr-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
