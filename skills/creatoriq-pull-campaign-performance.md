---
name: Pull CreatorIQ campaign performance
description: >-
  Read campaign activity, daily stats, publisher-level results and the reporting views that back
  CreatorIQ's measurement surface.
api: openapi/creatoriq-campaigns-openapi.yml, openapi/creatoriq-reports-openapi.yml, openapi/creatoriq-conversion-metrics-openapi.yml
operations:
  - getCampaigns
  - getCampaignInformation
  - getCampaignActivity
  - getCampaignDailyStats
  - getCampaignPublishers
  - getCampaignScheduledPosts
  - getSocialPostInfo
---

# Pull CreatorIQ campaign performance

Base URL `https://apis.creatoriq.com`, auth `x-api-key`.

## 1. Resolve the campaign
- `getCampaigns` — `GET /crm/v1/api/campaigns`
- `getCampaignInformation` — `GET /crm/v1/api/campaign/{campaignId}`

## 2. Read performance
- `getCampaignActivity` — `GET /crm/v1/api/campaign/{campaignId}/activity` — totals plus per-item rows.
- `getCampaignDailyStats` — `GET /crm/v1/api/campaign/{campaignId}/dailyStats`
- `getCampaignPublishers` — `GET /crm/v1/api/campaign/{campaignId}/publishers`
- `getCampaignScheduledPosts` — `GET /crm/v1/api/campaign/{campaignId}/scheduledPosts`
- `getSocialPostInfo` — `GET /crm/v1/api/social/postInfo` for a single post's metrics.

## 3. The reporting views
The reporting API is not resource-shaped. Forty named views are addressed through one path with a
`view` query parameter, e.g. `GET /crm/v1/api/view?view=Reports/Campaigns/CampaignPosts`. See
`openapi/creatoriq-reports-openapi.yml` for the full list of view names and their operationIds.

Reporting endpoints paginate with **`Page` and `PageSize`** — capitalised, unlike the CRM surface's
`page` and `size`. Sorting is expressed as bracketed query keys such as
`requestData[sort][0][field]`.

## 4. Metric caveats that will change your numbers
- A parallel `*_next` metric family (`views_next`, `engagedViews_next`, `EstimatedViews_next`, …) was
  added on 2025-10-14 and now sits alongside the legacy fields. Decide which family you are reporting on
  and be consistent.
- YouTube Shorts engaged views exist only for authenticated accounts, and view counts and estimated
  reach only for posts published on or after 2026-01-01.
- `GET /crm/v1/api/account/youtube/{id}/timeline` caps `size` at 50 and **silently lowers** larger
  values — if you ask for 200 you get 50 and no warning. Its `dateFrom` and `dateTo` parameters are
  deprecated.
- Campaign post data refreshes roughly every 24 hours. Polling faster spends rate limit for nothing;
  subscribe to `Campaign` / `update.latestpost` instead.
