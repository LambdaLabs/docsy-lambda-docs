---
title: "How do I list my file systems using the Cloud API?"
type: docs
tags:
- API
- storage
---

To list your
[persistent storage file systems](https://lambdalabs.com/blog/persistent-storage-beta/)
using the [Cloud API](https://cloud.lambdalabs.com/api/v1/docs):

1. [Generate an API key](https://cloud.lambdalabs.com/api-keys) if you don't
   already have an API key.

1. Run the following command:

   ```bash
   curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/file-systems | jq .
   ```

   Replace **API-KEY** with your actual API key. **Don't remove the trailing
   colon (:).**
