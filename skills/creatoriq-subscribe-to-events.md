---
name: Subscribe to CreatorIQ webhook events and verify them
description: >-
  Register a callback for CreatorIQ campaign, creator, One-Sheet and List events, and verify the
  signature on every delivery.
api: openapi/creatoriq-webhooks-openapi.yml
operations:
  - SubscriptionsController_subscribe
  - SubscriptionsController_getSubscriptions
  - SubscriptionsController_unsubscribe
---

# Subscribe to CreatorIQ webhook events and verify them

Base URL `https://apis.creatoriq.com/pubsub`, auth `x-api-key`. This surface is documented as **beta**.

## 1. Subscribe
- `SubscriptionsController_subscribe` — `POST /subscribe` with
  `{"callback": "...", "entityType": "...", "actionType": "..."}`. Returns `201`.

Available events (entityType / actionType):

| entityType | actionType |
|---|---|
| Campaign | `create`, `delete`, `update.latestpost`, `payout.paid` |
| Publisher | `account.linked`, `account.linked.failed`, `account.unlinked`, `delete`, `update`, `campaign.added` |
| Onesheet | `publish` |
| List_2 | `publish` |

`*` is accepted as a wildcard actionType, but the docs advise against it — subscribe only to what you
consume.

Subscribing twice to the same event returns `400` with
`"Subscription on the current event already exists!"`. Treat that as success, not as an error.

## 2. Confirm and manage
- `SubscriptionsController_getSubscriptions` — `GET /subscriptions`
- `SubscriptionsController_unsubscribe` — `DELETE /unsubscribe?entityType=...&actionType=...`.
  Unsubscribing from something you are not subscribed to returns `404`.

## 3. Verify every delivery
Each callback carries `x-timestamp` and `x-signature`. Build the signing string as:

```
JSON.stringify(JSON.parse(rawBody)) + xTimestamp + apiKey
```

and compare `md5(signingString)` against `x-signature`. If your partner has ACL enabled you will also
receive `x-signature-sha256`; verify that one instead — same signing string, SHA-256 instead of MD5.

Two things to know before you rely on this:
- It is a plain hash, **not an HMAC**, and CreatorIQ says so in its own docs.
- The signing secret **is your API key**. Whatever verifies webhooks therefore holds a credential that
  can call the whole API. Keep verification server-side.

## 4. Delivery expectations
- Your endpoint must serve valid HTTPS; CreatorIQ validates the connection before sending.
- On failure CreatorIQ retries twice at 1-minute intervals, then stores the event for 4 days. Replay is
  a support request, not an API call.
- There is no event log endpoint and no dashboard. If you need delivery history, email support.
- There is no trigger/simulate endpoint. To test, register a `webhook.site` URL and cause the real state
  change through the API or the app.
