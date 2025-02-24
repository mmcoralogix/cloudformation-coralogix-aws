# AWS S3 integarion for Coralogix

This template were created automatically from coralogix/coralogix-aws-serverless.
To make a change in the template go to the link below.

https://github.com/coralogix/coralogix-aws-serverless/tree/master/src/s3

Coralogix provides a predefined Lambda function to easily forward your S3 logs straight to the Coralogix platform.

## Prerequisites

* AWS account (Your AWS user should have permissions to create lambdas and IAM roles).
* Coralogix account.
* AWS S3 bucket.

## Fields 

* **Application name** - The stack name of this application created via AWS CloudFormation.

* **NotificationEmail** - If the lambda's execute fails an auto email sends to this address to notify it via SNS (requires you have a working SNS, with a validated domain).

* **S3BucketName** - The name of your S3 bucket.

* **ApplicationName** - The name of the Coralogix application you wish to assign to this lambda.

* **BlockingPattern** - OPTIONAL, a regular expression for lines that should be excluded.

* **BufferSize** - The Coralogix logger buffer size, possible option is ``134217728``.

* **CoralogixRegion** - The Coralogix location region, possible options are ``Europe``, ``Europe2``, ``India``, ``Singapore``, ``US``. In case that you want to use Custom domain, leave this as default and write the Custom doamin in the ``CustomDomain`` filed.

* **CustomDomain** - The Coralogix custom domain, leave empty if you don't use Custom domain.

* **Debug** - The Coralogix logger debug mode, possible options are ``true``, ``false``.

* **FunctionArchitecture** - Lambda function architecture, possible options are ``x86_64``, ``arm64``.

* **FunctionMemorySize** - Do not change! This is the maximum allocated memory that this lambda can consume, the default is ``1024``.

* **FunctionTimeout** - Do not change! This is the maximum time in seconds the function may be allowed to run, the default is ``300``.

* **NewlinePattern** - Do not change! This is the pattern for lines splitting, the default is ``(?:\r\n|\r|\n)``.

* **PrivateKey** - Your Coralogix secret key. Can be found in your **Coralogix** account under `Settings` -> `Send your logs`. It is located in the upper left corner.

* **SsmEnabled** - Set this to True to use AWS Secrets  (When enable it creates the secret in with the following pattern "lambda/coralogix/<AWS_REGION>/<Cloudwatch_lambda_name>") - optional. The field receive 'True' or 'False'. 
**Note:** Both layers and lambda need to be in the same AWS Region.

* **LayerARN** - This is the ARN of the Coralogix SecurityLayer. Copy from the ``SSM`` serverless application the ARN that was installed on the AWS account. 

* **SamplingRate** - Send messages with specific rate, the default is ``1``.

* **SubsystemName** - The subsystem name you wish to allocate to this log shipper.

* **S3KeyPrefix** - OPTIONAL, The prefix of the path within the log, this way you can choose if only part of your bucket is shipped.

* **S3KeySuffix** - OPTIONAL, A filter for the suffix of the file path in your bucket.

**Note:** You can use log field as Application/Subsystem names. Just use following syntax: ``$.my_log.field``.

## License

This project is licensed under the Apache-2.0 License.
