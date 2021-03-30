# Config Rule Python Runtime

Checks for unsupported versions of Python 2.7.

## Deployment

Deploy from S3 Bucket at `https://rolston-cloud-library.s3-us-west-2.amazonaws.com/conformance-packs/lambda-supported-runtimes.yml`

```sh

aws configservice put-conformance-pack --conformance-pack-name="Lambda-Supported-Runtimes" --template-s3-uri="s3://rolston-cloud-library/conformance-packs/lambda-supported-runtimes.yml"

```
