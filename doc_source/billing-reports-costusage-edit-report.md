# Editing an AWS Cost and Usage Report<a name="billing-reports-costusage-edit-report"></a>

Use the **Reports** page of the Billing and Cost Management console to edit an AWS Cost and Usage report\.

**Note**  
You can't edit the report name\.

**To edit an AWS Cost and Usage report**

1. Sign into the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)

1. On the navigation pane, choose **Reports**\.

1. Select the report that you want to edit and choose **Edit report**\. 

1.  For **Time unit**, choose **Hourly** if you want the line items in the report to be aggregated by the hour\. Choose **Daily** if you want the line items in the report to be aggregated by the day\. 

1.  For **Include**, to include the IDs of each individual resource in the report, select **Resource IDs**\.

1.  For **Enable support for**, select whether you want to upload your AWS Cost and Usage report to Amazon Redshift or Amazon QuickSight\. If you select a manifest, your report is stored with \.gz compression\. 

1. For **Data refresh settings**, select whether you want the AWS Cost and Usage report to refresh if AWS applies refunds, credits, or support fees to your account after finalizing your bill\. When a report refreshes, a new report is uploaded to Amazon S3, and the report manifest file is updated to reflect the location of the refreshed report\.

1.  For **Amazon S3 bucket**, type the name of the Amazon S3 bucket where you want the reports to be delivered and choose **Verify**\. The bucket must have appropriate permissions to be valid\. For more information on adding permissions to the bucket, see [ Setting Bucket and Object Access Permissions](http://docs.aws.amazon.com/AmazonS3/latest/user-guide/set-permissions.html) in the *[Amazon Simple Storage Service Console User Guide](http://docs.aws.amazon.com/AmazonS3/latest/user-guide/)*\. 

1.  For **Report path prefix**, type the report path prefix that you want prepended to the name of your report\. 

1. For **Compression**, choose how you want Cost Explorer to compress your reports\.

1. Choose **Save**\.