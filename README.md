# Cortex (cortex-idp)

Cortex (cortex.io) is an internal developer portal (IDP) and software catalog platform. It gives an engineering organization a searchable catalog of services and entities, Scorecards that measure those entities against production-readiness and reliability standards, Initiatives for driving improvement campaigns, and roughly thirty integrations (GitHub, PagerDuty, Datadog, Kubernetes, and more) that hydrate the catalog. Cortex exposes a documented public REST API at `https://api.getcortexapp.com/api/v1` authenticated with a Bearer API key.

If you searched for a **software catalog**, **service catalog**, or **internal developer portal (IDP)**, this is that category of product.

> **Disambiguation.** This entry is **Cortex.io the internal developer portal / service catalog & scorecards company** (docs.cortex.io, api.getcortexapp.com). It is **NOT**:
> - **Cortex XSOAR / Cortex XDR** by Palo Alto Networks (security orchestration / detection),
> - the **Cortex (CTXC)** crypto token / blockchain, or
> - **Orange Logic's Cortex** digital asset management (DAM) product.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/cortex-idp/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/cortex-idp/refs/heads/main/apis.yml)

## Access model

Cortex is a commercial SaaS internal developer portal (also available via the AWS Marketplace and Microsoft/Azure Marketplace). The REST API is available to authenticated workspace customers using an **API key** created in the Settings page of your Cortex workspace and passed as `Authorization: Bearer <token>`. The API operates on **your own workspace's catalog** - there is no open, unauthenticated public data API. The API reference itself is public at [docs.cortex.io/api](https://docs.cortex.io/api).

The API is rate limited to **1000 requests per minute per client** with a **2MB** maximum request body; exceeding the rate returns **429** with a `Retry-After` header.

## Tags

- Software Catalog
- Internal Developer Portal
- Service Catalog
- Developer Experience
- IDP
- Scorecards
- Platform Engineering
- Developer Portal

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Cortex Catalog API

The software catalog core - list, retrieve, create/update (upsert via entity descriptor), archive, unarchive, and delete catalog entities (services, resources, domains, and custom entity types). Retrieve an entity's descriptor, GitOps logs, and its scorecard scores.

- **Human URL:** [https://docs.cortex.io/api/readme/catalog-entities](https://docs.cortex.io/api/readme/catalog-entities)
- **Base URL:** `https://api.getcortexapp.com/api/v1`

### Cortex Scorecards API

List and retrieve Scorecards, fetch scores and next steps, get a per-entity badge, submit scores, manage a scorecard via its descriptor, and run the exemption workflow (request, approve, deny, revoke).

- **Human URL:** [https://docs.cortex.io/api/readme/scorecards](https://docs.cortex.io/api/readme/scorecards)
- **Base URL:** `https://api.getcortexapp.com/api/v1`

### Cortex Custom Data API

Attach arbitrary key/value metadata to catalog entities - list, get by key, add, bulk upsert across many entities, and delete.

- **Human URL:** [https://docs.cortex.io/api/readme/custom-data](https://docs.cortex.io/api/readme/custom-data)
- **Base URL:** `https://api.getcortexapp.com/api/v1`

### Cortex Initiatives API

Create, list, get, update, and delete Initiatives - time-boxed improvement campaigns that drive entities toward a Scorecard target.

- **Human URL:** [https://docs.cortex.io/api/readme/initiatives](https://docs.cortex.io/api/readme/initiatives)
- **Base URL:** `https://api.getcortexapp.com/api/v1`

### Cortex Deploys API

Record and query deployment events per catalog entity - list, add, update, and delete deploys, search across deploys, and list deploy environments.

- **Human URL:** [https://docs.cortex.io/api/readme/deploys](https://docs.cortex.io/api/readme/deploys)
- **Base URL:** `https://api.getcortexapp.com/api/v1`

### Cortex Integrations API

Manage the third-party integration configurations that hydrate the catalog. GitHub is shown as the exemplar; roughly thirty integrations follow the same configuration pattern. List, validate, add, update, and delete personal and app configurations per integration.

- **Human URL:** [https://docs.cortex.io/api/readme/integrations/github](https://docs.cortex.io/api/readme/integrations/github)
- **Base URL:** `https://api.getcortexapp.com/api/v1`

## Provenance and honesty note

Endpoint **paths and HTTP methods** in this entry are grounded in the live Cortex API reference at [docs.cortex.io/api](https://docs.cortex.io/api) (Catalog Entities, Scorecards, Custom Data, Initiatives, Deploys, and the GitHub integration). Request/response **schemas** in the OpenAPI are honestly modeled and simplified - marked as modeled where not copied verbatim - so verify exact payloads against the current documentation.

**Pricing is modeled.** Cortex's own pricing page ([cortex.io/pricing](https://www.cortex.io/pricing)) is contact-sales / custom proposal and publishes no rate card. Per-developer figures and tier limits in `plans/` come from third-party listings and are unconfirmed (`reconciled: false`). Cortex licenses per developer seat, not per catalogued service.

**No public WebSocket API.** See `review.yml`: Cortex's documented public API is request/response REST over HTTPS. Data ingestion happens via polling and inbound webhooks, not a consumer-facing server-push stream, so no AsyncAPI document was authored.

## Common Properties

- [Authentication](authentication/cortex-idp-authentication.yml)
- [LinkedIn](https://www.linkedin.com/company/cortexapp)
- [Website](https://www.cortex.io)
- [Documentation](https://docs.cortex.io)
- [Plans](plans/cortex-idp-plans-pricing.yml)
- [Rate Limits](rate-limits/cortex-idp-rate-limits.yml)
- [Fin Ops](finops/cortex-idp-finops.yml)
- [Pricing](https://www.cortex.io/pricing)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
