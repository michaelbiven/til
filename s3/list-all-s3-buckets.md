# List all S3 buckets

For a given profile list all of the bucket names. 

`aws s3api --profile <PROFILENAME> list-buckets | jq -r '.Buckets | .[] | .Name'`
