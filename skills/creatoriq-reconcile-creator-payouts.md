---
name: Reconcile CreatorIQ creator payouts
description: >-
  Read what is owed to creators, what has been paid, and whether each creator has supplied the payment
  information needed to pay them.
api: openapi/creatoriq-payments-openapi.yml
operations:
  - listPayables
  - listPayouts
  - getPaymentInfoCollectionStatus
---

# Reconcile CreatorIQ creator payouts

Base URL `https://apis.creatoriq.com`, auth header `X-API-KEY` (this spec declares it uppercase; HTTP
header names are case-insensitive, so the same key works).

The Payments API is **read-only**. Nothing here moves money — you cannot initiate, approve or cancel a
payout over the API. It is a reconciliation surface.

## 1. What is owed
- `listPayables` — `GET /payments/v1/payables`

## 2. What has been paid
- `listPayouts` — `GET /payments/v1/payouts`

## 3. Who is blocked
- `getPaymentInfoCollectionStatus` — `GET /payments/v1/publishers/payment-info-collection-status`

Creators who have not completed payment-information collection cannot be paid; this endpoint is the
list to chase.

## 4. Close the loop on the event
Payment completion is only observable as an event: subscribe to `Campaign` / `payout.paid`, which fires
when a creator's payment status is set to paid. There is no polling endpoint that tells you a specific
payout just settled.

## Rules
- This surface is **cursor-paginated** (`cursor`), unlike the page/size CRM endpoints. Follow the cursor;
  do not compute offsets.
- These endpoints are new — payables and payouts landed 2026-07-13, collection status 2026-07-08. Expect
  the shape to keep moving and parse tolerantly.
- There is no sandbox with test payout data and no PCI DSS claim on this surface. Reconcile against
  production carefully.
