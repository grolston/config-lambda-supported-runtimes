# Config Rule Lambda Supported Runtimes

Checks for unsupported runtime environments for Lambda.

## Suppurted Runtimes

The following runtime environments are supported in AWS Lambda

1. python3.8 
2. python3.7 
3. python3.6 
4. nodejs14.x 
5. nodejs12.x  
6. ruby2.7 
7. java11
8. java8.al2 
9. java8 
10. go1.x
11. dotnetcore3.1
12. dotnetcore2.1 
13. provided.al2
14. provided

If the runtime identifier is not listed above, the config rule will display as noncompliant.

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
