# OpenCitations FinOps

## Cost Summary

OpenCitations is a fully free and open science infrastructure. There are no costs, subscription fees, or usage-based charges for any of its APIs, SPARQL endpoints, or data downloads.

| Service | Cost |
|---------|------|
| Index API | Free |
| Meta API | Free |
| SPARQL Endpoint | Free |
| Database Dumps | Free |
| Access Token | Free |

## Budget Planning

Because OpenCitations has no pricing tiers or usage fees, there are no direct API costs to plan for. FinOps considerations for OpenCitations integrations are limited to:

- **Infrastructure costs** for your own systems consuming the API
- **Caching strategy** to stay within the 180 requests/minute rate limit and avoid re-fetching the same data
- **Dump ingestion costs** if processing full database snapshots locally (compute + storage)

## Cost Optimization

1. **Use database dumps for bulk data** — Downloading full dataset snapshots from https://download.opencitations.net eliminates API call overhead entirely for large-scale needs.
2. **Cache API responses** — Citation data changes infrequently; caching responses locally reduces redundant API calls.
3. **Use the access token** — While it does not change costs, the token helps OpenCitations justify continued free operation by demonstrating usage metrics.
4. **Batch by double-underscores** — The Meta API `/metadata/{ids}` endpoint accepts multiple IDs separated by `__`, reducing the number of requests needed.

## Sustainability

OpenCitations operates as a non-commercial, community-guided open infrastructure funded by research grants and institutional support from the University of Bologna. It is not a commercial entity and does not generate revenue from API access.

Supporting OpenCitations' sustainability through citations, acknowledgements, and community engagement benefits the broader open science ecosystem.

Contact: contact@opencitations.net
Website: https://opencitations.net
