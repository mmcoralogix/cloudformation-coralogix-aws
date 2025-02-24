# AWS CloudTrail-SNS integration for Coralogix

This template were created automatically from coralogix/coralogix-aws-serverless.
To make a change in the template go to the link below.

https://github.com/coralogix/coralogix-aws-serverless/tree/master/src/cloudtrail-sns

Coralogix provides a predefined Lambda function to easily forward your CloudTrail logs through SNS to the Coralogix platform.

## Prerequisites
* Active CloudTrail 
* Permissions to create lambda functions.
* SNS topic with permission `SNS:Publish` on the S3 bucket.
* An AWS account.
* A coralogix account.

## Fields 

**Application name** - The stack name of this application created via AWS CloudFormation.

**SubsystemName** - Sybsystem Name as it will be seen in Coralogix UI.

**NotificationEmail** (optinal) - If the lambda fails a notification email will be sent to this address via SNS (requires you have a working SNS, with a validated domain).

**S3BucketName** - The name of the S3 bucket with CloudTrail logs to watch (must be in the same region as stack that you will create).

**SNSTopicARN** - The arn of the SNS topic (must be in the same region as the S3 bucket).

**ApplicationName** - Application Name as it will be seen in Coralogix UI.

**CoralogixRegion** - The Coralogix location region, possible options are [Europe, Europe2, India, Singapore, US].In case that you want to use Custom domain, leave this as default and write the Custom doamin in the ``CustomDomain`` filed.

**CustomDomain** - The Coralogix custom domain,leave empty if you don't use Custom domain.

**FunctionArchitecture** - Lambda function architecture, possible options are [x86_64, arm64]. 

**FunctionMemorySize** - The maximum allocated memory this lambda may consume, the default is 1024. Don't change

**FunctionTimeout** - The maximum time in seconds the function may be allowed to run, the default is 300. Don't change

**PrivateKey** - Your Coralogix secret key.

Do not change the `FunctionMemorySize`, `FunctionTimeout` parameters.


## License

This project is licensed under the Apache-2.0 License.
