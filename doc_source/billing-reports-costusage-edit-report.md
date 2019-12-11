# Editing an AWS Cost and Usage Report<a name="billing-reports-costusage-edit-report"></a>

Use the **** page of the Billing and Cost Management console to edit an AWS Cost and Usage report\.

**Note**  
You can't edit the report name\. If you chose **Overwrite** for **Report versioning**, you can't edit the report name, whether the report includes resource IDs, the time granularity, or the report versioning\. If you delete a report set to **Overwrite** and create a new report with the same name, Amazon S3 bucket, and path prefix, your data could become corrupted and inaccurate\.

**To edit an AWS Cost and Usage report**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)

1. On the navigation pane, choose ****\.

1. Select the report that you want to edit and choose **Edit report**\. 

1. \(Versioned reports only\) For **Additional report details**, to include the IDs of each individual resource in the report, select **Include resource IDs**\.

1. For **Data refresh settings**, select whether you want the AWS Cost and Usage report to refresh if AWS applies refunds, credits, or support fees to your account after finalizing your bill\. When a report refreshes, a new report is uploaded to Amazon S3\.

1. Choose **Next**\.

1. For **S3 bucket**, enter the name of the Amazon S3 bucket where you want the reports to be delivered and choose **Verify**\. The bucket must have appropriate permissions to be valid\. For more information on adding permissions to the bucket, see [ Setting Bucket and Object Access Permissions](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/set-permissions.html) in the *[Amazon Simple Storage Service Console User Guide](https://docs.aws.amazon.com/AmazonS3/latest/user-guide/)*\. 

1. For **Report path prefix**, enter the report path prefix that you want prepended to the name of your report\. 

1. \(Versioned reports only\) For **Time granularity**, choose **Hourly** if you want the line items in the report to be aggregated by the hour\. Choose **Daily** if you want the line items in the report to be aggregated by the day\.

1. \(Versioned reports only\) For **Report versioning**, choose whether you want each version of the report to overwrite the previous version of the report or to be delivered in addition to the previous versions\.

1. For **Enable report data integration for**, select whether you want to upload your AWS Cost and Usage report to Amazon Redshift, Amazon QuickSight, or Amazon Athena\. If you select an Amazon Redshift or Amazon QuickSight manifest, your report is stored with \.gz compression\. If you select an Athena manifest, your report is stored with parquet compression\.

1. Choose **Save**\.