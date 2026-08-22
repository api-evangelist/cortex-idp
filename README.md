# Cortex (cortex-idp)

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
