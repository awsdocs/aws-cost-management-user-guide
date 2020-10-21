# Monthly cost allocation report<a name="configurecostallocreport"></a>

The monthly cost allocation report lists the AWS usage for your account by product category and linked account user\. The report contains the same line items as the detailed billing report \(see the [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\) and additional columns for your tag keys\. For more information, see the following topics\.

**Topics**
+ [Setting up a monthly cost allocation report](#allocation-report)
+ [Getting an hourly cost allocation report](#allocation-get)
+ [Viewing a cost allocation report](#allocation-viewing)

## Setting up a monthly cost allocation report<a name="allocation-report"></a>

By default, new tag keys that you add using the API or the AWS Management Console are automatically excluded from the cost allocation report\. You can add them using the procedures described in this topic\.

When you select tag keys to include in your cost allocation report, each key becomes an additional column that lists the value for each corresponding line item\. Because you might use tags for more than just your cost allocation report \(for example, tags for security or operational reasons\), you can include or exclude individual tag keys for the report\. This ensures that you're seeing meaningful billing information that helps organize your costs\. A small number of consistent tag keys makes it easier to track your costs\. For more information, see [Viewing a cost allocation report](#allocation-viewing)\.

**Note**  
AWS stores billing reports in an Amazon S3 bucket that you create and own\. You can retrieve these reports from the bucket using the Amazon S3 API, AWS Management Console for Amazon S3, or the Amazon S3 command line interface \(CLI\)\. You can't download the cost allocation report from the [Account Activity](https://console.aws.amazon.com/billing/home#/bill) page of the Billing and Cost Management console\. 

**To set up the cost allocation report and activate tags**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Under **Preferences** in the navigation pane, choose **Billing Preferences**

1. For **Detailed Billing Reports \[Legacy\]**, select the check box **Turn on the legacy Detailed Billing Reports feature to receive ongoing reports of your AWS charges**\.

1. For **Save to S3 Bucket**, enter a valid Amazon S3 bucket name and choose **Verify**\.

1. In the **Report** list, select the check box for **Cost allocation report**\.

1. Choose **Manage report tags**, as shown in the following screenshot\.

   The page displays a list of tags that you've created using either the API or the console for the applicable AWS service\. Tag keys that currently appear in the report are selected, and the check boxes for excluded tag keys are cleared\. 

1. For **Filter**, choose **Inactive tags** in the dropdown list and select the tags that you want to activate for your report\.  
![\[Cost Allocation Management page\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Cost Allocation Management page\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Cost Allocation Management page\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

1. Choose **Activate**\.

If you own the management account in an organization, your cost allocation report includes all the usage, costs, and tags for the member accounts\. By default, all keys registered by member accounts are available for you to include or exclude from your report\. The detailed billing report with resources and tags also includes any cost allocation tag keys that you select using the preceding steps\. 

## Getting an hourly cost allocation report<a name="allocation-get"></a>

The cost allocation report is one of several reports that AWS publishes to an Amazon S3 bucket several times a day\. 

**Note**  
During the current billing period \(monthly\), AWS generates an estimated cost allocation report\. The current month's file is overwritten throughout the billing period until a final report is generated at the end of the billing period\. Then a new file is created for the next billing period\. The reports for the previous months remain in the designated Amazon S3 bucket\.

## Viewing a cost allocation report<a name="allocation-viewing"></a>

The following example tracks the charges for several cost centers and applications\. Resources \(such as Amazon EC2 instances and Amazon S3 buckets\) are assigned tags like "Cost Center"="78925" and "Application"="Widget1"\. In the cost allocation report, the user\-defined tag keys have the prefix `user`, such as `user:Cost Center` and `user:Application`\. AWS generated tag keys have the prefix `aws`\. The keys are column headings identifying each tagged line item's value, such as "78925"\.

![\[Keys in the Downloadable Report\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/CostAllocationPartExampleReport.png)

You can use a desktop spreadsheet application to create pivot tables that group the keys and the values for each key so that you can see combined values for tagged resources\. The following example organizes information first by Cost Center and, within each cost center further organizes the information by the Application tag\.

![\[An Example of a Microsoft Excel Pivot Table using tagged resources\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/AllocatedBillingReport.png)

Pick your keys carefully so that you have a consistent hierarchy of values\. Otherwise, your report won't group costs effectively, and you will have many line items\.

**Note**  
If you add or change the tags on a resource partway through a billing period, costs are split into two separate lines in your cost allocation report\. The first line shows costs before the update, and the second line shows costs after the update\.

### Unallocated resources in your report<a name="allocation-untagged"></a>

Any charges that cannot be grouped by tags in your cost allocation report default to the standard billing aggregation \(organized by Account/Product/Line Item\) and are included in your report\. Situations where you can have unallocated costs include:
+ You signed up for a cost allocation report mid\-month\.
+ Some resources aren't tagged for part, or all, of the billing period\.
+ You are using services that currently don't support tagging\.
+ Subscription\-based charges, such as Premium Support and AWS Marketplace monthly fees, can't be allocated\.
+ One\-time fees, such as Amazon EC2 Reserved Instance upfront charges, can't be allocated\.

### Unexpected costs associated with tagged resources<a name="cost-alloc-tag-costs"></a>

You can use cost allocation tags to see what resources are contributing to your usage and costs, but deleting or deactivating the resources doesn't always reduce your costs\. For more information on reducing unexpected costs, see [Avoiding unexpected charges](checklistforunwantedcharges.md)\.