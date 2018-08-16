# AWS Cost and Usage Report<a name="billing-reports-costusage"></a>

The AWS Cost and Usage report tracks your AWS usage and provides estimated charges associated with your AWS account\. The report contains line items for each unique combination of AWS product, usage type, and operation that your AWS account uses\. You can customize the AWS Cost and Usage report to aggregate the information either by the hour or by the day\. 

If you use the consolidated billing feature in AWS Organizations, this report is available only to the master account and includes activity for all the member accounts that are associated with the master account\. Member account owners can obtain the report only from the master account owner\. For more information, see [Consolidated Billing for Organizations](consolidated-billing.md)\.

AWS delivers the report files to an Amazon S3 bucket that you specify in your account and updates the report up to three times a day\. Each update is cumulative, so each version of the AWS Cost and Usage report includes all of the line items and information from the previous version\. The reports that AWS generates throughout the month are estimated and are subject to change during the rest of the month, as you incur more usage\. AWS finalizes the report at the end of each month\. Finalized reports have the calculations for your blended and unblended costs, and cover all of your usage for the month\. AWS might update reports after they have been finalized if AWS applies refunds, credits, or support fees to your usage for the month after finalizing your bill\. You can set this as a preference when creating or editing your report\. The report is available starting within 24 hours of the date that you created a report on the **Reports** page of the Billing and Cost Management console\. 

You can either download the report from the Amazon S3 console or upload the report into Amazon Redshift or Amazon QuickSight\. For more information about uploading to Amazon Redshift, see [Uploading an AWS Cost and Usage Report to Amazon Redshift](billing-reports-costusage-upload.md)\. For more information about uploading to Amazon QuickSight, see [Create a Data Set Using Amazon S3 Files](http://docs.aws.amazon.com/quicksight/latest/user/create-a-data-set-s3.html) in the *Amazon QuickSight User Guide*\. If you chose to create Amazon Redshift and Amazon QuickSight manifests when you created your report, Billing and Cost Management provides the Amazon S3 data and Amazon QuickSight manifests for you\.

**Note**  
AWS supports five AWS Cost and Usage reports per account\. The reports are free of charge, but standard Amazon S3 storage rates apply\. 

**Topics**
+ [Managing AWS Cost and Usage Reports](billing-reports-costusage-managing.md)
+ [Cost and Usage Report Details](billing-reports-costusage-details.md)
+ [Reserved Instances](billing-reports-costusage-ri.md)