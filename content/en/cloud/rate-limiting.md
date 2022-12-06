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
