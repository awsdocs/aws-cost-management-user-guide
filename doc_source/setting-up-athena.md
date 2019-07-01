# Getting Started with Amazon Athena<a name="setting-up-athena"></a>

You can use an existing Amazon S3 bucket or AWS Cost and Usage report with Athena, but we strongly recommend that you create both a new Amazon S3 bucket and a new AWS Cost and Usage report for use with Athena\. The recommended setup process removes any Amazon S3 events that your bucket might already have, which can negatively affect any existing event\-based processes that you have for an existing AWS Cost and Usage report\. Setting up a new AWS Cost and Usage report can take up to 8 hours, so we recommend that you plan to do the last two setup steps the next day\.

AWS Cost and Usage Report supports only the parquet compression format for Athena and automatically overwrites previous AWS Cost and Usage reports stored in your Amazon S3 bucket\.

**Important**  
If you plan to use a AWS CloudFormation template, you must create all resources in the same Region\. AWS CloudFormation doesn't support cross\-Region resources\. The Region must support the following services:  
AWS Lambda
Amazon Simple Storage Service
AWS Glue
Amazon Athena

Setting up to use Athena includes the following steps:
+ [Create a new bucket](#create-athena-bucket)
+ [To create an AWS Cost and Usage report](#create-athena-cur)
+ [To use the Athena AWS CloudFormation template](#use-athena-cf)<a name="create-athena-bucket"></a>

**To create an Amazon S3 bucket for your reports**

Use this procedure to create a new Amazon S3 bucket for your report\.
**Note**  
If you are part of an AWS Organizations organization, only the master account can create this bucket\. AWS Cost and Usage reports can be delivered only to a bucket owned by the master account\.

1. Open the Amazon S3 console at [https://console\.aws\.amazon\.com/s3/](https://console.aws.amazon.com/s3/)\.

1. Choose **Create Bucket**\.

1. In the dialog box, for **Bucket Name**, enter the name for your bucket\.
**Note**  
Your bucket name must be all lowercase, from 3 to 63 characters long, and can't contain spaces\. You can use lowercase letters, numbers, hyphens \(\-\), and periods \(\.\) in your bucket name\.

1. Choose the Region that you want your Amazon S3 bucket to be in\.

1. Choose **Next**\.

1. Choose **Next**\.

1.  \(Optional\) If you choose **Grant Amazon Simple Storage Service Log Delivery group write access to this bucket**, you can enable access logs that track who accesses your Amazon S3 bucket\. Choose the bucket that you want the access logs to be delivered to and the name of a folder that you want the logs to be stored in\. 

1. Choose **Next**\.

1. Choose **Create bucket**\.

1. From the list of buckets, choose the bucket that you want to receive reports in\.

1. Choose **Permissions**\.

1. Choose **Bucket Policy**\.

1. Paste the following text into the bucket policy editor\.

   ```
   {
     "Version": "2012-10-17",
     "Statement": [
     {
       "Effect": "Allow",
       "Principal": {
         "Service": "billingreports.amazonaws.com"
       },
       "Action": [
         "s3:GetBucketAcl",
         "s3:GetBucketPolicy"
       ],
       "Resource": "arn:aws:s3:::bucketname"
     },
     {
       "Effect": "Allow",
       "Principal": {
         "Service": "billingreports.amazonaws.com"
       },
       "Action": "s3:PutObject",
       "Resource": "arn:aws:s3:::bucketname/*"
     }
     ]
   }
   ```

1. Replace *bucketname* with the name of your bucket\. 

1. Choose **Save**\.<a name="create-athena-cur"></a>

**To create an AWS Cost and Usage report**

Use this procedure to create a new AWS Cost and Usage report for use with Athena\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. On the navigation pane, choose **Cost and Usage Reports**\.

1. Choose **Create report**\.

1. For **Report name**, enter a name for your report\.

1. For **Additional report details**, to include the IDs of each individual resource in the report, select **Include resource IDs**\.

1. For **Data refresh settings**, select whether you want the AWS Cost and Usage report to refresh if AWS applies refunds, credits, or support fees to your account after finalizing your bill\. When a report refreshes, a new report is uploaded to Amazon S3\.
**Note**  
Detailed billing reports \(DBRs\) don't refresh automatically, whether you select **Data refresh settings** or not\. To refresh a DBR, open a support case\. For more information, see [Contacting Customer Support About Your Bill](billing-get-answers.md)\.

1. Choose **Next**\.

1. For **S3 bucket**, choose **Configure**\.

1. In the **Configure S3 Bucket** dialog box, do one of the following:
   + Select an existing bucket from the drop down list and choose **Next**\.
   + Enter a bucket name and the Region where you want to create a new bucket and choose **Next**\.

1. Select **I have confirmed that this policy is correct** and choose **Save**\.

1. For **Report path prefix**, enter the report path prefix that you want prepended to the name of your report\. You must provide a report path prefix to use Athena with AWS Cost and Usage report\. 

1. For **Time granularity**, choose **Hourly** if you want the line items in the report to be aggregated by the hour\. Choose **Daily** if you want the line items in the report to be aggregated by the day\.

1. For **Report versioning**, choose whether you want each version of the report to overwrite the previous version of the report or to be delivered in addition to the previous versions\.

1. For **Enable report data integration for**, select whether you want to upload your AWS Cost and Usage report to Amazon Redshift, Amazon QuickSight, or Amazon Athena\. The report is compressed in the following formats:
   + **Amazon Redshift or Amazon QuickSight**: \.gz compression
   + **Athena**: parquet compression

1. Choose **Next**\.

1. After you have reviewed the settings for your report, choose **Review and Complete**\. 

1. Before moving on to the next procedure, you must wait for the first AWS Cost and Usage report to be delivered to your Amazon S3 bucket\. It might take up to 8 hours for AWS to deliver your first AWS Cost and Usage report\.<a name="use-athena-cf"></a>

**To use the Athena AWS CloudFormation template**

To use Athena, you must set up an AWS Glue crawler, an AWS Glue database, and an AWS Lambda event\. Billing and Cost Management provides an AWS CloudFormation template that does this setup for you\. AWS CloudFormation doesn't support resources in multiple Regions for one stack, so the Region that you use must support the following services:
+ AWS Lambda
+ Amazon Simple Storage Service
+ AWS Glue
+ Amazon Athena
**Important**  
The AWS CloudFormation template removes all events associated with your Amazon S3 bucket, so we strongly recommend that you use a new Amazon S3 bucket\.

1. Open the Amazon S3 console at [https://console\.aws\.amazon\.com/s3/](https://console.aws.amazon.com/s3/)\.

1. From the list of buckets, choose the bucket name\.

1. Choose the prefix name\.

1. Choose the report name\.

1. Select the `.yml` template file\.

1. Select **download**\.

1. Open the AWS CloudFormation console at [https://console\.aws\.amazon\.com/cloudformation](https://console.aws.amazon.com/cloudformation/)\.

1. If you have never used AWS CloudFormation before, choose **Create New Stack**\. Otherwise, choose **Create Stack**\. 

1. Under **Choose a template**, choose **Upload a template to Amazon S3**\.

1. Choose **Browse\.\.\.**, choose the downloaded template, and then choose **Open**\.

1. Choose **Next**\.

1. For **Stack name**, enter a name for your template and choose **Next**\.

1. Choose **Next**\.

1. Select **I acknowledge that AWS CloudFormation might create IAM resources\.** This template creates the following resources:
   + Three IAM roles
   + An AWS Glue database
   + An AWS Glue crawler
   + Two Lambda functions
   + An Amazon S3 notification

1. Choose **Create**\.