# Config Rule - Conformance Pack - Lambda Supported Runtimes

Checks for unsupported runtime environments for Lambda.

## Supported Runtimes

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

If the runtime identifier is not listed above, the config rule will display as noncompliant. Please reference the Lambda [AWS Runtime Support Policy](https://docs.aws.amazon.com/lambda/latest/dg/runtime-support-policy.html) for further details about deprecated runtime environments.

## Prerequisites

The following prerequisites need to be met prior to deploying:

1. AWS Config running in the target account or AWS Config Aggregator deployed at the Organization
2. Permissions to deploy AWS Config Conformance Packs

## Deployment

The conformance pack is stored in an S3 bucket which can be referenced in many ways to deploy. To download the template directly, access from S3 at Bucket at `https://rolston-cloud-library.s3-us-west-2.amazonaws.com/conformance-packs/lambda-supported-runtimes.yml`. The template is an exact copy of the `lambda-supported-runtimes.yml` file in the master branch which is copied over via a GitHub Action.

### Deploy from CloudShell

Use the AWS CloudShell to quickly deploy the conformance pack

```sh

aws configservice put-conformance-pack --conformance-pack-name="lambda-supported-runtimes" --template-s3-uri="s3://rolston-cloud-library/conformance-packs/lambda-supported-runtimes.yml" ## optional set your region

```

### Deploy as CloudFormation

The deployment process leverages AWS CloudFormation and is relatively simple once prerequisites are satisfied. Overall the process entails three steps

**Steps to Deploy:**

1. Open your web browser and login to your AWS Account.
2. Click the `Launch Stack` button below to launch stack.
3. Fill in the parameter values

> **Note:** If you want to open the link as a new tab use `ctrl+click` when clicking the *launch Stack* button below.

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=lambda-supported-runtimes&templateURL=https://rolston-cloud-library.s3-us-west-2.amazonaws.com/conformance-packs/lambda-supported-runtimes.yml)

### Organizations Deployment

The preferred method of deployment is via AWS Organizations integration with AWS Config Aggregator. To learn more about Organizational AWS Config Aggregator read [AWS Config and AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/services-that-can-integrate-config.html).

Setting up AWS Config at the AWS Organization level enables complete visibility into all your linked accounts. The deployment requires you have access to your `management` account (aka payer account) and you have enabled AWS Organizations Full Features and the AWS Organization service for AWS Config.

To deploy an Organizational conformance pack go into your management account open up the CloudShell and run the following command:

```sh
aws configservice put-organization-conformance-pack --organization-conformance-pack-name="lambda-supported-runtimes" --template-s3-uri="s3://rolston-cloud-library/conformance-packs/lambda-supported-runtimes.yml" ##optional set your region
```
