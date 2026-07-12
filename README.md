# Sesame HR (sesame-hr)

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
