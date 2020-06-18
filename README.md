# aws-lambda-s3-file-upload
File upload to s3 bucket via rest call .


AWS Resources:
-   Aws api gateway with post method on resource
-   aws lambda in nodejs
-   s3 Bucket to save files

Make sure Aws lambda has access on S3. Add `S3FullAccess` policy on IAM role lambda has.
Required policy for s3 bucket.
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "GetPutProgramaticAccess",
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::<>:root"
            },
            "Action": [
                "s3:GetObject",
                "s3:PutObject"
            ],
            "Resource": "arn:aws:s3:::<bucket-name>/*"
        },
        {
            "Sid": "ReadAccess",
            "Effect": "Allow",
            "Principal": {
                "AWS": "*"
            },
            "Action": [
                "s3:GetObject"
            ],
            "Resource": "arn:aws:s3:::<bucket-name>/*"
        }
    ]
}
```
