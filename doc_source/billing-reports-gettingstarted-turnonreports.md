# Creating an AWS Cost and Usage report<a name="billing-reports-gettingstarted-turnonreports"></a>

Use the **Reports** page of the Billing and Cost Management console to create an AWS Cost and Usage report\.

**To create an AWS Cost and Usage report**

1. Sign into the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)

1. On the navigation pane, choose **Reports**\.

1. Choose **Create report**\.

1. For **Report name**, type a name for your report\.

1. For **Time unit**, choose **Hourly** if you want the line items in the report to be aggregated by the hour\. Choose **Daily** if you want the line items in the report to be aggregated by the day\. 

1. For **Include**, to include the IDs of each individual resource in the report, select **Resource IDs**\.

1. For **Enable support for**, select whether you want to upload your AWS Cost and Usage report to Amazon Redshift or Amazon QuickSight\. If you select a manifest, your report is stored with \.gz compression\. 

1. For **Data refresh settings**, select whether you want the AWS Cost and Usage report to refresh if AWS applies refunds, credits, or support fees to your account after finalizing your bill\. When a report refreshes, a new report is upload to Amazon S3\.

1. Choose **Next**\.

1. For **Amazon S3 bucket**, type the name of the Amazon S3 bucket where you want the reports to be delivered and choose **Verify**\. The bucket must have appropriate permissions to be valid\. For more information on adding permissions to the bucket, see [ Setting Bucket and Object Access Permissions](http://docs.aws.amazon.com/AmazonS3/latest/user-guide/set-permissions.html) in the *[Amazon Simple Storage Service Console User Guide](http://docs.aws.amazon.com/AmazonS3/latest/user-guide/)*\. 

1. For **Report path prefix**, type the report path prefix that you want prepended to the name of your report\. 

1. Choose **Next**\.

1. After you have reviewed the settings for your report, choose **Review and Complete**\. 

**Note**  
It can take up to 24 hours for AWS to start delivering reports to your Amazon S3 bucket\. After delivery starts, AWS updates the AWS Cost and Usage report files at least once a day\. 