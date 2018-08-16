# Detailed Billing Report with Resources and Tags<a name="reportstagsresources"></a>

**Important**  
The Detailed Billing Report with Resources and Tags will be unavailable at a later date\. We strongly recommend that you use the [AWS Cost and Usage Report](billing-reports-costusage.md) instead\.

The detailed billing report with resources and tags adds additional dimensions by which you can view your AWS charges\. This report includes resource identifiers for many of the AWS services\. Amazon EC2, for example, provides a ResourceID value for each Amazon EC2 instance that is run under your account\. You can use this field for viewing your charges for each AWS resource, as well as for data filtering and aggregation\. 

In addition, any cost allocation tags you have applied to your resources are appended to each line item in the report\. You can filter or aggregate on these tags\. For more information about creating these tags, see [Using Cost Allocation Tags](cost-alloc-tags.md)\. You are not required to create and use cost allocation tags to get the detailed billing report with resources and tags\.

**Note**  
This report contains line items for every hour of operation for every resource and can grow quite large\. The report is compressed into a ZIP file, but might exceed the maximum number of rows you can display in a desktop spreadsheet application\.