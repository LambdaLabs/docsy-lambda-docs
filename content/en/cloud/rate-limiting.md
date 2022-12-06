---
title: "Are API requests rate-limited?"
type: docs
tags:
- API
---

Requests to the [Cloud API](https://cloud.lambdalabs.com/api/v1/docs) are
generally limited to 1 request per second.

Requests to the `/instance-operations/launch` endpoint are limited to 1
request every 10 seconds.

{{% alert title="Note" color="info" %}}
If you're being rate limited, you'll receive
[error code: 1015](https://support.cloudflare.com/hc/en-us/articles/360029779472-Troubleshooting-Cloudflare-1XXX-errors#error1015)
in response to your API request.

You'll also receive an
[HTTP 429 response status code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429).
{{% /alert %}}

{{% alert title="Note" color="info" %}}
The request rate limits may change at any time.
{{% /alert %}}
