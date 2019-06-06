# Creating an AWS Cost and Usage Report<a name="billing-reports-gettingstarted-turnonreports"></a>

Use the **Reports** page of the Billing and Cost Management console to create an AWS Cost and Usage report\.

**To create an AWS Cost and Usage report**

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

1. For **Report path prefix**, enter the report path prefix that you want prepended to the name of your report\. 

   This step is optional for Amazon Redshift or Amazon QuickSight, but required for Amazon Athena\.

   If you don't specify a prefix, the default prefix is the name that you specified for the report in step 4 and the date range for the report, in the following format:

   `/report-name/date-range/`

1. For **Time granularity**, choose **Hourly** if you want the line items in the report to be aggregated by the hour\. Choose **Daily** if you want the line items in the report to be aggregated by the day\.

1. For **Report versioning**, choose whether you want each version of the report to overwrite the previous version of the report or to be delivered in addition to the previous versions\.

1. For **Enable report data integration for**, select whether you want to upload your AWS Cost and Usage report to Amazon Redshift, Amazon QuickSight, or Amazon Athena\. The report is compressed in the following formats:
   + **Amazon Redshift or Amazon QuickSight**: \.gz compression
   + **Athena**: parquet compression

1. Choose **Next**\.

1. After you have reviewed the settings for your report, choose **Review and Complete**\. 

**Note**  
It can take up to 24 hours for AWS to start delivering reports to your Amazon S3 bucket\. After delivery starts, AWS updates the AWS Cost and Usage report files at least once a day\. 