# When deleting remote state in aws

Make sure to remove the key in S3 and the item in the DynomoDB. 

Otherwise you will get an error like: 

```
state data in S3 does not have the expected content.

This may be caused by unusually long delays in S3 processing a previous state
update.  Please wait for a minute or two and try again. If this problem
persists, and neither S3 nor DynamoDB are experiencing an outage, you may need
to manually verify the remote state and update the Digest value stored in the
DynamoDB table to the following value:
```
