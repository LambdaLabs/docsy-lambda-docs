---
title: "Can I list my running instances from a command line?"
type: docs
---

You can list your running instances from a command line using the
[Cloud API](https://cloud.lambdalabs.com/api/v1/docs).

First, [generate an API key](https://cloud.lambdalabs.com/api-keys). Then, run
the following command:

```bash
curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/instances | jq .
```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**
