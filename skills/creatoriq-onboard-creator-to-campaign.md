---
name: Onboard a creator into a CreatorIQ campaign
description: >-
  Find or create a creator (publisher) in the CreatorIQ CRM, attach their social accounts, assign them
  to a campaign, and set their payment terms for that campaign.
api: openapi/creatoriq-publishers-openapi.yml, openapi/creatoriq-campaigns-openapi.yml
operations:
  - getUserInSocialNetwork
  - getAllPublishers
  - createPublisher
  - addPublisherSocialAccount
  - getCampaigns
  - assignPublisherToCampaign
  - updateCampaignPublisherDetails
  - updateCampaignPublisherPaymentSettings
---

# Onboard a creator into a CreatorIQ campaign

Base URL `https://apis.creatoriq.com`. Every request carries `x-api-key: <key>`. Keys are issued by a
CreatorIQ account manager at partner or division level — there is no self-serve key creation, and no
scopes, so the key you hold can do everything this skill does.

## 1. Look before you create
Search the creator on the network or in the CRM first — duplicating a publisher is not reversible from
the API side without a delete.

- `getUserInSocialNetwork` — `GET /crm/v1/api/accounts/lookup`. Searches a social network *or* the
  CreatorIQ database.
- `getAllPublishers` — `GET /crm/v1/api/publishers`. Paginate with `page` and `size`. **`size` must not
  exceed 1000** (changelog 2026-06-24); a larger value is rejected.

## 2. Create the publisher if they are not there
- `createPublisher` — `POST /crm/v1/api/publishers`.

There is **no idempotency key** on this endpoint or any other. If the call times out you do not know
whether the publisher was created — re-run `getAllPublishers` and match before retrying, never blind-retry.

## 3. Attach social accounts
- `addPublisherSocialAccount` — `POST /crm/v1/api/publisher/{publisherId}/accounts`.
- `getPublisherAccounts` — `GET /crm/v1/api/publisher/{publisherId}/accounts` to confirm.

Account linking is also an event: subscribe to `Publisher` / `account.linked` and
`account.linked.failed` rather than polling (see `asyncapi/creatoriq-webhooks.yml`).

## 4. Assign to the campaign
- `getCampaigns` — `GET /crm/v1/api/campaigns` to resolve the campaign id.
- `assignPublisherToCampaign` — `POST /crm/v1/api/campaign/{campaignId}/publishers`.
- `updateCampaignPublisherDetails` — `PATCH /crm/v1/api/campaign/{campaignId}/publishers`.

## 5. Set payment terms
- `updateCampaignPublisherPaymentSettings` — `PATCH /crm/v1/api/campaign/{campaignId}/publisher/{publisherId}/payment/settings`.

## Error and rate-limit rules
- Budget: **100,000 requests/day and 5 requests/second** per key. A `429` means you exceeded it. No
  `Retry-After` and no `RateLimit-*` headers are returned — back off exponentially from a 1-second base.
- A `403` means either the key lacks permission **or the `x-api-key` header is missing entirely**. Check
  the header before assuming a permissions problem.
- A `400` — not a `404` — is what you get when a publisher id or campaign id does not exist.
- Responses gain fields without a version bump. Parse tolerantly and ignore unknown properties; this is
  CreatorIQ's own published instruction.
