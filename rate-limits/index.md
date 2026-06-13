# OpenCitations Rate Limits

## Standard Rate Limit

All OpenCitations REST APIs enforce a single rate limit for fair use:

| Limit | Value |
|-------|-------|
| Requests per minute (per IP) | 180 |
| Authentication required | No |
| Access token required | No (optional) |

This rate limit applies to:
- OpenCitations Index API (`https://api.opencitations.net/index/v2`)
- OpenCitations Meta API (`https://api.opencitations.net/meta/v1`)

## Access Token Behavior

An optional free access token can be provided via the `authorization` HTTP request header. The token does not increase the rate limit but helps OpenCitations monitor usage anonymously to demonstrate service value to funders. Obtain a token at https://opencitations.net/accesstoken.

## Exceeding Rate Limits

If you need to retrieve large volumes of data, OpenCitations strongly recommends using the database dump downloads instead of the REST API:

- Download portal: https://download.opencitations.net
- Full dataset snapshots are available for all indexes (COCI, Meta, etc.)
- No rate limit applies to downloads

## SPARQL Endpoint

The SPARQL endpoint at https://sparql.opencitations.net does not publish explicit rate limit values in its documentation. Contact tech@opencitations.net for guidance on high-volume SPARQL usage.

## HTTP Methods

All REST API endpoints use GET requests only. No POST, PUT, or DELETE operations are supported.

## Response Formats

APIs return JSON by default. CSV output is also available via:
- Accept header: `Accept: text/csv`
- Query parameter: `?format=csv`

## Technical Contact

For rate limit questions or high-volume access needs: tech@opencitations.net
