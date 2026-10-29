# CreatorIQ

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

CreatorIQ is an enterprise creator- and influencer-marketing platform used by brands and agencies to discover creators, build and manage a private creator network, run and measure campaigns, handle creator payouts, and report on performance across Instagram, TikTok, YouTube and other social networks. Its public REST API — documented on a Stoplight portal at apidocs.creatoriq.com and served from https://apis.creatoriq.com — exposes the customer's own CRM: publishers (creators), campaigns, lists, one-sheets, notes, divisions, social accounts and post/account metrics, an asynchronous reporting surface of forty report views, ecommerce promo codes and transactions, affiliate link tracking, conversion metrics, SafeIQ brand-safety scoring, and a Payments API for payouts and payables. A pub/sub webhook API lets integrators subscribe to campaign, creator, one-sheet and list events with MD5 and SHA-256 signed callbacks. Authentication is a single `x-api-key` header issued per partner or per division by a CreatorIQ account manager; there is no self-serve signup.

**Areas:** Influencer Marketing · Creator Economy · Social Media · Marketing · Campaign Management · creator-crm · Social Analytics · Brand Safety · Affiliate Marketing · creator-payments · E-Commerce · Reporting

## CreatorIQ on APIs.io

Everything profiled for CreatorIQ is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/creatoriq/](https://apis.io/providers/creatoriq/)** — or go straight to one of the APIs or properties below.

### APIs (19)

- [CreatorIQ Brand Safety API](https://apis.io/apis/creatoriq/creatoriq-brand-safety-api/) — SafeIQ brand safety timeline API
- [CreatorIQ Campaign API](https://apis.io/apis/creatoriq/creatoriq-campaign-api/) — Campaign information
- [CreatorIQ Campaign Conversion Metrics API](https://apis.io/apis/creatoriq/creatoriq-campaign-conversion-metrics-api/) — Campaign Conversion Metrics
- [CreatorIQ CJ API](https://apis.io/apis/creatoriq/creatoriq-cj-api/) — CJ reports
- [CreatorIQ Creator Payment Info API](https://apis.io/apis/creatoriq/creatoriq-creator-payment-info-api/) — Creator payment-info collection status
- [CreatorIQ Divisions API](https://apis.io/apis/creatoriq/creatoriq-divisions-api/) — Divisions public API
- [CreatorIQ Ecommerce API](https://apis.io/apis/creatoriq/creatoriq-ecommerce-api/) — Ecommerce public API
- [CreatorIQ General API](https://apis.io/apis/creatoriq/creatoriq-general-api/) — General section of reporting
- [CreatorIQ Global Conversion Metrics Configuration API](https://apis.io/apis/creatoriq/creatoriq-global-conversion-metrics-configuration-api/) — Global Conversion Metrics Configuration
- [CreatorIQ Link Tracking API](https://apis.io/apis/creatoriq/creatoriq-linktracking-api/) — LinkTracking public API
- [CreatorIQ Lists API](https://apis.io/apis/creatoriq/creatoriq-lists-api/) — Lists public API
- [CreatorIQ Notes API](https://apis.io/apis/creatoriq/creatoriq-notes-api/) — Notes public API
- [CreatorIQ Onesheet API](https://apis.io/apis/creatoriq/creatoriq-onesheet-api/) — Onesheets public API
- [CreatorIQ Payables API](https://apis.io/apis/creatoriq/creatoriq-payables-api/) — Creator payables
- [CreatorIQ Payouts API](https://apis.io/apis/creatoriq/creatoriq-payouts-api/) — Creator payouts
- [CreatorIQ Publisher API](https://apis.io/apis/creatoriq/creatoriq-publisher-api/) — Publisher public API
- [CreatorIQ Reporting API](https://apis.io/apis/creatoriq/creatoriq-reporting-api/) — Reporting
- [CreatorIQ Social API](https://apis.io/apis/creatoriq/creatoriq-social-api/) — Public social API
- [CreatorIQ Subscription API](https://apis.io/apis/creatoriq/creatoriq-subscription-api/) — Subscription API part

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Creatoriq Webhooks](https://apis.io/asyncapis/creatoriq/creatoriq-webhooks/)

#### Collections (17)

Postman and Open Collection request collections.

- [CreatorIQ SafeIQ Brand Safety API](https://apis.io/collections/creatoriq/open-creatoriq-brand-safety/)
- [CreatorIQ Brand Safety (draft)](https://apis.io/collections/creatoriq/open-creatoriq-brand-safety-draft/)
- [CreatorIQ Campaign APIs](https://apis.io/collections/creatoriq/open-creatoriq-campaigns/)
- [Conversion Metrics API](https://apis.io/collections/creatoriq/open-creatoriq-conversion-metrics/)
- [CreatorIQ Ecommerce APIs](https://apis.io/collections/creatoriq/open-creatoriq-ecommerce/)
- [CreatorIQ CRM LinkTracking API](https://apis.io/collections/creatoriq/open-creatoriq-link-tracking/)
- [CreatorIQ CRM Lists API](https://apis.io/collections/creatoriq/open-creatoriq-lists/)
- [CreatorIQ CRM Publishers API](https://apis.io/collections/creatoriq/open-creatoriq-notes/)
- [CreatorIQ CRM Onesheets API](https://apis.io/collections/creatoriq/open-creatoriq-onesheets/)
- [CreatorIQ Payments API](https://apis.io/collections/creatoriq/open-creatoriq-payments/)
- [CreatorIQ CRM Publishers API](https://apis.io/collections/creatoriq/open-creatoriq-publishers/)
- [CreatorIQ Reporting APIs](https://apis.io/collections/creatoriq/open-creatoriq-reports/)
- [CreatorIQ Social Account APIs](https://apis.io/collections/creatoriq/open-creatoriq-socials/)
- [CreatorIQ Divisions APIs](https://apis.io/collections/creatoriq/open-creatoriq-v1-divisions/)
- [CreatorIQ CRM Campaigns API V2](https://apis.io/collections/creatoriq/open-creatoriq-v2-campaigns/)
- [CreatorIQ CRM Publishers API V2](https://apis.io/collections/creatoriq/open-creatoriq-v2-publishers/)
- [CreatorIQ Public APIs](https://apis.io/collections/creatoriq/open-creatoriq-webhooks/)

#### Overlays (18)

OpenAPI overlays, including conversational phrasing for each operation.

- [_Index](https://apis.io/overlays/creatoriq/_index/)
- [Creatoriq Brand Safety Draft Overlay](https://apis.io/overlays/creatoriq/creatoriq-brand-safety-draft-overlay/)
- [Creatoriq Brand Safety Overlay](https://apis.io/overlays/creatoriq/creatoriq-brand-safety-overlay/)
- [Creatoriq Campaigns Overlay](https://apis.io/overlays/creatoriq/creatoriq-campaigns-overlay/)
- [Creatoriq Conversion Metrics Overlay](https://apis.io/overlays/creatoriq/creatoriq-conversion-metrics-overlay/)
- [Creatoriq Ecommerce Overlay](https://apis.io/overlays/creatoriq/creatoriq-ecommerce-overlay/)
- [Creatoriq Link Tracking Overlay](https://apis.io/overlays/creatoriq/creatoriq-link-tracking-overlay/)
- [Creatoriq Lists Overlay](https://apis.io/overlays/creatoriq/creatoriq-lists-overlay/)
- [Creatoriq Notes Overlay](https://apis.io/overlays/creatoriq/creatoriq-notes-overlay/)
- [Creatoriq Onesheets Overlay](https://apis.io/overlays/creatoriq/creatoriq-onesheets-overlay/)
- [Creatoriq Payments Overlay](https://apis.io/overlays/creatoriq/creatoriq-payments-overlay/)
- [Creatoriq Publishers Overlay](https://apis.io/overlays/creatoriq/creatoriq-publishers-overlay/)
- [Creatoriq Reports Overlay](https://apis.io/overlays/creatoriq/creatoriq-reports-overlay/)
- [Creatoriq Socials Overlay](https://apis.io/overlays/creatoriq/creatoriq-socials-overlay/)
- [Creatoriq V1 Divisions Overlay](https://apis.io/overlays/creatoriq/creatoriq-v1-divisions-overlay/)
- [Creatoriq V2 Campaigns Overlay](https://apis.io/overlays/creatoriq/creatoriq-v2-campaigns-overlay/)
- [Creatoriq V2 Publishers Overlay](https://apis.io/overlays/creatoriq/creatoriq-v2-publishers-overlay/)
- [Creatoriq Webhooks Overlay](https://apis.io/overlays/creatoriq/creatoriq-webhooks-overlay/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Creatoriq Authentication](https://apis.io/security/creatoriq/creatoriq-authentication/)
- [Creatoriq Domain Security](https://apis.io/security/creatoriq/creatoriq-domain-security/)
- [Creatoriq Trust Center](https://apis.io/security/creatoriq/creatoriq-trust-center/)
- [Creatoriq Vulnerability Disclosure](https://apis.io/security/creatoriq/creatoriq-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Creatoriq Plans Pricing](https://apis.io/plans/creatoriq/creatoriq-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Creatoriq Rate Limits](https://apis.io/rate-limits/creatoriq/creatoriq-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.creatoriq.com/)
- [Documentation](https://apidocs.creatoriq.com/docs/ciq-api-documentation/o5yqwvpp1lbnb-overview)
- [Getting started](https://apidocs.creatoriq.com/docs/ciq-api-documentation/05lf89tv60rvy-introduction-to-api-keys)
- [API reference](https://apidocs.creatoriq.com/docs/ciq-api-documentation/6e239b2598043-creator-iq-crm-publishers-api)
- [Pricing](https://www.creatoriq.com/pricing)
- [Sign up](https://app.creatoriq.com/)
- [Support](https://www.creatoriq.com/contact)
- [Changelog](https://apidocs.creatoriq.com/docs/ciq-api-documentation/6b7999d265a29-changelog)
- [Blog](https://www.creatoriq.com/blog)
- [Security](https://www.creatoriq.com/legal/security)
- [Compliance](https://www.creatoriq.com/trust)
- [Terms of service](https://www.creatoriq.com/legal/terms-of-use)
- [Privacy policy](https://www.creatoriq.com/legal/privacy-policy)
- [Status](https://status.creatoriq.com/)

## API Evangelist rating

**Kin Score 62.4** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 63.0 |
| Contract governance | 4.5 |
| Operational transparency | 78.9 |
| Developer ergonomics | 66.1 |
| Access clarity | 60.5 |

**Agent readiness 35.9** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | distinct |

**Regulatory alignment 32.1** — Payments

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/creatoriq/](https://apis.io/providers/creatoriq/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for CreatorIQ: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/creatoriq/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
