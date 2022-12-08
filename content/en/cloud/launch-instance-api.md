---
title: "Can I launch an instance from the command line?"
type: docs
tags:
- API
---

You can launch an instance from the command line using the
[Cloud API](https://cloud.lambdalabs.com/api/v1/docs):

1. [Generate an API key](https://cloud.lambdalabs.com/api-keys).

2. Create a file named `request.json` that contains the
   [necessary payload](https://cloud.lambdalabs.com/api/v1/docs#operation/launchInstance).
   For example:

   ```json
   {
     "region_name": "us-east-1",
     "instance_type_name": "gpu_1x_a100_sxm4",
     "ssh_key_names": [
       "SSH-KEY"
     ],
     "file_system_names": [],
     "quantity": 1
   }
   ```

3. Run the following command:

   ```bash
   curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/instance-operations/launch -d @request.json -H "Content-Type: application/json" | jq .
   ```

Replace **API-KEY** with your actual API key. **Don't remove the trailing
colon (:).**
