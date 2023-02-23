---
title: "How do I terminate an instance using the Cloud API?"
type: docs
tags:
- API
---

You can terminate instances from the command line using the
[Cloud API](https://cloud.lambdalabs.com/api/v1/docs):

1. [Generate an API key](https://cloud.lambdalabs.com/api-keys) if you haven't
   already generated one.

2. Create a file that contains the
   [necessary payload](https://cloud.lambdalabs.com/api/v1/docs#operation/terminateInstance).
   For example:

   ```json
   {
     "instance_ids": [
       "0920582c7ff041399e34823a0be62549"
     ]
   }
   ```

   {{% alert title="Note" color="info" %}}
   [Use the API to obtain the IDs of your instances]({{< relref "list-running-instances" >}}).
   {{% /alert %}}

3. Run the following command:

   ```bash
   curl -u API-KEY: https://cloud.lambdalabs.com/api/v1/instance-operations/terminate -d @INSTANCE-IDS -H "Content-Type: application/json" | jq .
   ```

   Replace **API-KEY** with your actual API key. **Don't remove the trailing
   colon (:).**
   
   Replace **INSTANCE-IDS** with the name of the payload file you created in
   the previous step.
