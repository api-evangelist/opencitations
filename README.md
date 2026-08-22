# OpenCitations

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
