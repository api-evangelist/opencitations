# OpenCitations

OpenCitations is an open science research infrastructure established in 2010, operated by the Research Centre for Open Scholarly Metadata at the University of Bologna. It provides free access to scholarly bibliographic and citation data through REST APIs, SPARQL endpoints, and downloadable dataset dumps. All data is published under the CC0 Public Domain Waiver for unrestricted reuse.

## APIs

This repository contains an APIs.json 0.19 profile for the following OpenCitations APIs:

### OpenCitations Index API
- **Base URL:** `https://api.opencitations.net/index/v2`
- **Version:** 2.2.0
- **Description:** Access citation entities including incoming/outgoing citation counts and full citation metadata. Supports DOI, PMID, and OMID identifiers. Aggregates data across all OpenCitations indexes.
- **Key endpoints:**
  - `GET /citation/{oci}` — citation metadata by Open Citation Identifier
  - `GET /citation-count/{id}` — incoming citation count for a work
  - `GET /reference-count/{id}` — outgoing reference count for a work
  - `GET /citations/{id}` — all incoming citations to a work
  - `GET /references/{id}` — all outgoing references from a work
  - `GET /venue-citation-count/{id}` — citation count for all works in a venue

### OpenCitations Meta API
- **Base URL:** `https://api.opencitations.net/meta/v1`
- **Version:** 1.1.1
- **Description:** Retrieve bibliographic metadata for scholarly works by DOI, ISSN, ISBN, OMID, OpenAlex ID, PMID, or PMCID. Also supports author and editor lookup by ORCID or OMID.
- **Key endpoints:**
  - `GET /metadata/{ids}` — bibliographic metadata for one or more works
  - `GET /author/{id}` — works authored by a specific person (ORCID/OMID)
  - `GET /editor/{id}` — works edited by a specific person (ORCID/OMID)

### OpenCitations SPARQL Endpoint
- **URL:** `https://sparql.opencitations.net`
- **Description:** Structured SPARQL queries against the full OpenCitations Meta and Index Linked Open Data graphs.

## Authentication

Authentication is optional. A free access token can be obtained at https://opencitations.net/accesstoken and included in the `authorization` HTTP header to help OpenCitations track anonymous usage metrics.

## Rate Limits

All REST APIs are rate-limited to **180 requests per minute per IP address**. For large-scale data needs, use the database dumps at https://download.opencitations.net.

## Pricing

All OpenCitations services are completely free. There are no paid tiers or commercial plans.

## Additional Resources

- Homepage: https://opencitations.net
- API Portal: https://api.opencitations.net
- SPARQL: https://sparql.opencitations.net
- Search: https://search.opencitations.net
- Downloads: https://download.opencitations.net
- OCI Resolver: https://oci.opencitations.net
- Statistics: https://statistics.opencitations.net
- Access Token: https://opencitations.net/accesstoken

## Contact

- General: contact@opencitations.net
- Technical: tech@opencelist.net
