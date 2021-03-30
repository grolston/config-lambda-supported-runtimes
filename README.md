# Config Rule Python Runtime

Checks for unsupported versions of Python 2.7.

## Deployment

Deploy from S3 Bucket at `https://rolston-cloud-library.s3-us-west-2.amazonaws.com/conformance-packs/lambda-supported-runtimes.yml`

Use the AWS CloudShell to quickly deploy the conformance pack

```sh

aws configservice put-conformance-pack --conformance-pack-name="lambda-supported-runtimes" --template-s3-uri="s3://rolston-cloud-library/conformance-packs/lambda-supported-runtimes.yml" ## optional set your region

```

or run this at the AWS Org level:

```sh
aws configservice put-organization-conformance-pack --organization-conformance-pack-name="lambda-supported-runtimes" --template-s3-uri="s3://rolston-cloud-library/conformance-packs/lambda-supported-runtimes.yml" ##optional set your region
```
