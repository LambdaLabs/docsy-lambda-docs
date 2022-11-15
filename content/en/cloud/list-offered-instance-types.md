---
title: "Can I list the offered instance types from a command line?"
type: docs
---

You can list the instances types offered by Lambda GPU Cloud by first
[generating an API key](https://cloud.lambdalabs.com/api-keys), then running
the following command:

```bash
curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/instance-types | jq .
```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**
