---
title: 'Sync with AWS S3'
date: '16:22 15-11-2021'
taxonomy:
    category:
        - docs
---

In the **desktop application** or **mobile application**, select "AWS S3 (Beta)" as the synchronisation target in the [Configuration screen](https://github.com/laurent22/joplin/blob/dev/readme/config_screen.md).

- **AWS S3 Bucket:** The name of your Bucket, such as `joplin-bucket`
- **AWS S3 URL:** Fully qualified URL; By default this should be `https://s3.amazonaws.com/`
- **AWS key & AWS secret:**  IAM user's programmatic access key.  To create a new key & secret, visit [IAM Security Credentials](https://console.aws.amazon.com/iam/home#/security_credentials).


While creating a new Bucket for Joplin, disable **Bucket Versioning**, enable **Block all public access** and enable **Default encryption** with `Amazon S3 key (SSE-S3)`.

To add a **Bucket Policy** from the AWS S3 Web Console, navigate to the **Permissions** tab. Temporarily disable **Block all public access**  to edit the Bucket policy, something along the lines of:
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Principal": "*",
            "Action": [
                  "s3:ListBucket",
                  "s3:GetBucketLocation",
                  "s3:DeleteObject",
                  "s3:DeleteObjectVersion",
                  "s3:PutObject"
            ],
            "Resource": [
                "arn:aws:s3:::joplin-bucket",
                "arn:aws:s3:::joplin-bucket/*"
            ]
        }
    ]
}
```