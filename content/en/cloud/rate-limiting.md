---
title: "Are API requests rate-limited?"
type: docs
tags:
- API
---

Requests to the Cloud API are rate-limited as shown in the table, below.

{{% alert title="Warning" color="warning" %}}
All further API requests will be blocked for 1 minute if the rate limitation
is met.
{{% /alert %}}

| Endpoint | Rate limit (requests per minute) |
| --- | --- |
| /instances | 60 |
| /instances/{id} | 60 |
| /instance-operations/launch | 12 |
| /instance-operations/terminate | 60 |
| /instance-types | 60 |

{{% alert title="Note" color="info" %}}
For request rate limiting, the number of requests is cumulative.

This means, for example, if within 1 minute you make 30 requests to
`/instances` and 30 requests to `/instances-types`, you will be blocked from
making further requests for 1 minute.
{{% /alert %}}
