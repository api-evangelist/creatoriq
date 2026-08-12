---
name: Build and publish a CreatorIQ One-Sheet
description: >-
  Assemble a shareable creator pitch sheet from a list of creators, publish it, and collect the
  approvals, rejections and comments that come back.
api: openapi/creatoriq-onesheets-openapi.yml, openapi/creatoriq-lists-openapi.yml
operations:
  - getListsCollection
  - createList
  - postPublisherToList
  - createOnesheet
  - addCreatorToOnesheet
  - PublishOneSheet
  - getCreatorsOfOnesheet
  - approveCreatorToOnesheet
  - RemoveCreator
  - AddPublisherComment
---

# Build and publish a CreatorIQ One-Sheet

Base URL `https://apis.creatoriq.com`, auth `x-api-key`.

A One-Sheet is CreatorIQ's pitch artefact: a set of creators plus their metrics, published at a
shareable link so a brand can approve or reject each one.

## 1. Curate the shortlist
- `getListsCollection` — `GET /crm/v1/api/lists`
- `createList` — `POST /crm/v1/api/lists`
- `postPublisherToList` — `POST /crm/v1/api/list/{listId}/publishers`
- `deletePublisherFromList` — `DELETE /crm/v1/api/list/{listId}/publishers`

## 2. Build the One-Sheet
- `createOnesheet` — `POST /crm/v1/api/onesheets`
- `addCreatorToOnesheet` — `POST /crm/v1/api/onesheet/{oneSheetId}/publishers`
- `getCreatorsOfOnesheet` — `GET /crm/v1/api/onesheet/{oneSheetId}/publishers`

## 3. Publish it
- `PublishOneSheet` — `POST /crm/v1/api/onesheet/{oneSheetId}/publish`

Publishing emits the `Onesheet` / `publish` webhook event. Subscribe before publishing if a downstream
system needs to react.

## 4. Handle the feedback loop
- `approveCreatorToOnesheet` — `PATCH /crm/v1/api/onesheet/{oneSheetId}/publisher/{publisherId}/approve`
- `RemoveCreator` — `DELETE /crm/v1/api/onesheet/{oneSheetId}/publisher/{publisherId}`
- `UpdateOneSheetCreator` — `PATCH /crm/v1/api/onesheet/{oneSheetId}/publisher/{publisherId}`
- `AddPublisherComment` — `POST /crm/v1/api/onesheet/{oneSheetId}/publisher/{publisherId}/comments`

## Rules
- Note the casing: several One-Sheet operationIds are PascalCase (`RemoveCreator`,
  `UpdateOneSheetCreator`, `AddPublisherComment`, `PublishOneSheet`) while their siblings are camelCase.
  Use them verbatim.
- No idempotency key. `PublishOneSheet` is not safe to blind-retry; re-read the One-Sheet first.
- 100,000 requests/day, 5 requests/second, `429` on exhaustion with no `Retry-After`.
