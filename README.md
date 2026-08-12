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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

CreatorIQ is an enterprise creator- and influencer-marketing platform. Brands and agencies use it to
discover creators, run a private creator network, manage and measure campaigns, pay creators, and
report across Instagram, TikTok, YouTube and other networks.

- Website: https://www.creatoriq.com/
- Developer portal: https://apidocs.creatoriq.com/
- API host: https://apis.creatoriq.com
- Status: https://status.creatoriq.com/

## What is in this profile

Seventeen OpenAPI documents (8 x 3.0.1, 9 x 3.1.0) covering **159 operations**, harvested verbatim
from the Stoplight project behind `apidocs.creatoriq.com`. Every operation carries an `operationId`.
Alongside them: the authentication model, conventions, error catalogue, rate limits, lifecycle and
deprecation policy, changelog, webhook event catalogue, data model, sandbox and mock servers,
conformance, security and trust posture, five agent skills, and a generated `llms.txt`.

## Notable findings

- The developer portal is a client-rendered Stoplight site that looks spec-less. The specs are public
  and exportable through the Stoplight project API; `openapi/_original/` holds them verbatim.
- Rate limits are published — 100,000 requests/day and 5 requests/second per key — but **no
  rate-limit response headers and no `Retry-After` are documented**, so a client cannot see its
  remaining budget at runtime.
- **No idempotency contract anywhere.** Zero occurrences of "idempoten" across all eighteen specs,
  against a write surface that creates campaigns, publishers, lists, one-sheets and promo codes.
- A published one-year deprecation policy with `Deprecation` and `Sunset` headers (RFC 8594) — strong
  for this cohort — that appears in prose only and is declared in no spec.
- Webhook signatures are a plain MD5 or SHA-256 hash, not an HMAC, and CreatorIQ says so in its own
  docs. The signing secret is the API key itself.
- ISO/IEC 27001:2022 certified, GDPR and CCPA compliant. No SOC 2, and no PCI DSS claim on the
  Payments API.
- No SDKs, no public repositories, no CLI, no MCP server, no A2A agent card, no AsyncAPI, and no
  `/.well-known` document of any kind — including `security.txt`.
