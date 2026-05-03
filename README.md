# US Senate

The United States Senate is one of the two chambers of Congress, responsible for representing the interests of the individual states and ensuring that federal legislation is passed in a fair and representative manner. The Senate administers the Lobbying Disclosure Act (LDA) reporting system, which requires lobbyists and lobbying firms to register and report their activities for public transparency.

**LDA Developer Portal:** https://lda.senate.gov/api/  
**APIs.yml:** https://raw.githubusercontent.com/api-evangelist/us-senate/refs/heads/main/apis.yml

---

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

Federal Government, Lobbying, Government Transparency, Campaign Finance, Open Data

## Timestamps

- **Created:** 2024-12-03
- **Modified:** 2026-05-03

---

## APIs

### Senate Lobbying Disclosure Act (LDA) API
REST API providing public access to lobbying filings, registrations, quarterly activity reports (LD-2), and semi-annual contribution reports (LD-203).

- **Base URL:** `https://lda.senate.gov/api/v1`
- **Auth:** Optional API key (increases rate limit from 15 to 120 req/min)
- **OpenAPI:** [openapi/us-senate-lda-openapi.yml](openapi/us-senate-lda-openapi.yml)
- **Documentation:** https://lda.senate.gov/api/redoc/v1/

Key endpoints:
- `GET /filings/` — Search lobbying disclosure filings
- `GET /filings/{filing_uuid}/` — Get specific filing
- `GET /registrants/` — List lobbying registrants
- `GET /clients/` — List lobbying clients
- `GET /lobbyists/` — List individual lobbyists
- `GET /contributions/` — List LD-203 contribution reports
- `GET /constants/filing/lobbyingactivityissues/` — Get issue codes

---

## Artifacts

| Type | Files |
|------|-------|
| OpenAPI Specs | [openapi/](openapi/) — 1 spec |
| Examples | [examples/](examples/) — 2 examples |
| Spectral Rules | [rules/us-senate-rules.yml](rules/us-senate-rules.yml) |
| Naftiko Capabilities | [capabilities/](capabilities/) — 1 workflow + 1 shared |
| JSON Schema | [json-schema/](json-schema/) — 1 schema |
| JSON Structure | [json-structure/](json-structure/) — 1 structure |
| JSON-LD | [json-ld/](json-ld/) — 1 context |
| Vocabulary | [vocabulary/](vocabulary/) — 1 vocabulary |

---

## Capabilities

### Shared Definitions
- [capabilities/shared/lda.yaml](capabilities/shared/lda.yaml) — LDA API consumed definition (5 operations + reference data)

### Workflow Capabilities
- [capabilities/lobbying-transparency.yaml](capabilities/lobbying-transparency.yaml) — Lobbying disclosure research (7 MCP tools)
  - Lobbying filing search and retrieval
  - Registrant and client lookup
  - Lobbyist search
  - Reference data (issue codes, government entities)

---

## Use Cases

- **Government Transparency Research** — Track who is lobbying Congress and on what issues
- **Lobbying Activity Monitoring** — Monitor filings for specific clients, registrants, or issue areas
- **Campaign Finance Research** — Analyze LD-203 campaign contribution disclosures
- **Policy Influence Tracking** — Identify which organizations are lobbying on specific legislation
- **Compliance Verification** — Verify registrant and lobbyist registration status
- **Investigative Journalism** — Research lobbying relationships and expenditures

---

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
