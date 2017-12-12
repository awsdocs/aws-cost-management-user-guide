# Setting Up an Amazon S3 Bucket for AWS Cost and Usage Reports<a name="billing-reports-gettingstarted-s3"></a>

To receive billing reports, you must have an Amazon S3 bucket in your AWS account to store the reports in\. You can specify an existing bucket or create a new one\. To create a bucket, see [Creating a Bucket](http://docs.aws.amazon.com/AmazonS3/latest/user-guide/CreatingaBucket.html) in the [Amazon Simple Storage Service Console User Guide](http://docs.aws.amazon.com/AmazonS3/latest/user-guide/)\.

You also must apply a resource\-based permissions policy to your Amazon S3 bucket to allow AWS to write files to the bucket\. For an example bucket policy and information about how to apply your policy to a bucket, see [Step 2: Turn on Reports](billing-getting-started.md#step-2)\.

**Note**  
Storing the billing reports data in your Amazon S3 bucket is billed at standard Amazon S3 rates\.