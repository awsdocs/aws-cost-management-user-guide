# Migrating Your Detailed Billing Report to AWS Cost and Usage Report<a name="migrate-dbr-cur"></a>

The Detailed Billing Report \(DBR\) and the AWS Cost and Usage Report \(CUR\) both provide information about your charges\. If you are using DBR, we strongly recommend you transfer your report to the AWS Cost and Usage Report\.

**Topics**
+ [Benefits of the AWS Cost and Usage Report](#migrate-benefit-cur)
+ [Key Differences Between the Detailed Billing Report and the AWS Cost and Usage Report](#migrate-key)
+ [Reporting on Advanced Charge Types](#reporting-advanced-chargetype)

## Benefits of the AWS Cost and Usage Report<a name="migrate-benefit-cur"></a>

 The Cost and Usage Report provides the most comprehensive source of information\. It allows you to understand individual costs in depth, and to analyze them in greater detail, which is especially useful at an enterprise scale\. CUR is best suited for customers with complex cost management needs, for example, those with dedicated query or analytic\-based systems\. CUR is also your best source for Reserved Instance \(RI\) information, especially if you want to view amortized costs\.

For more information on getting started with the AWS Cost and Usage Report, see [AWS Cost and Usage Report](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-costusage.html)\.

### Comprehensive Reservation Information<a name="migrate-reservation"></a>

Reserved Instances \(RI\), or Reservations, offer a discounted hourly rate compared to on\-demand usage, in exchange for committing to a one\- or three\-year term of service\. This can result in significant savings\. CUR helps you monitor and manage your reservation portfolio by providing comprehensive information like Reservation Amazon Resource Numbers \(ARN\), numbers of reservations, and total reserved units\. You can track your reservation\-related discounts to specific resources, which help you better understand your savings\. 

DBR provides a subset of this metadata, but work is required to transform the required columns\.

CUR provides additional columns not available in DBR, such as information regarding your amortized reservation costs\. For more information, see [Amortizing Reserved Instances](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/amortizing-ri.html)\.

### On\-Demand Pricing Availability<a name="migrate-ondemand"></a>

CUR provides information regarding the on\-demand rates for each individual line item of usage\. This information makes it easy to quantify your savings by subtracting the amount you paid from the on\-demand rate, allowing you to quickly and easily compute your savings as compared to on\-demand prices\. This also gives you the flexibility of choosing to allocate your costs using public on\-demand rates\.

DBR doesn’t contain information for on\-demand rates, but only the billed amount\. This makes it difficult to calculate your overall savings or to allocate costs using on\-demand rates\.

### Granular Breakdown of Discounts<a name="migrate-granular"></a>

CUR can access a granular view of the usage\-based discounts\. If discounts were applied, you can use CUR to view:
+ The cost prior to being discounted
+ The discounted amount
+ The total cost after the discount was applied at the line item level

DBR does not contain a granular breakdown of your discounts\.awsMasterSchedDocs

### Automated Data Ingestion at Scale<a name="migrate-autodata"></a>

When you use CUR, you can easily configure an event to trigger an automated data ingestion process, streamlining the process of refreshing the billing data in your in\-house systems\. CUR data can automatically be refreshed when charges related to previous months are detected\.

Additionally, CUR is generated as multiple files, providing the added benefit of segmenting the data into smaller pieces\. This makes it easier to ingest the data according to the processes used by multiple workers\. It also allows you to retry data downloads in smaller pieces\.

CUR is formatted in a way that allows for easy data location and extraction\. This report is modeled from a manifest file that contains information for the overall structure of the data, including a list of every column that is contained in the report\. This makes the report easily extensible in cases where new information regarding your usage becomes available\.

### Cross\-Product Integration<a name="migrate-crossproduct"></a>

CUR supports integration with Amazon Redshift, Amazon QuickSight, and Amazon Athena, making it easy to quickly build out an AWS based cost management solution\. CUR also provides data in Parquet format, broadening your options when it comes to building out your own cost and usage reporting system\. For more information, see [AWS Cost and Usage Report Manifest Files](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-costusage-files.html#manifests)\.

## Key Differences Between the Detailed Billing Report and the AWS Cost and Usage Report<a name="migrate-key"></a>

There are a few differences between DBR and CUR that you should be aware of after you migrate to using CUR\. You may need to adjust how you ingest the data into your systems accordingly\.

### File Structure<a name="key-file"></a>

DBR is delivered as a single file, while CUR is delivered as a consolidated set of files\. In the AWS Cost and Usage Report, you can view the following files in your Amazon S3 bucket:
+  A set of data files containing all of your usage line items
+  \(If applicable\) A separate data file containing all of your discounts
+ A manifest file that lists all of the data files that belong to a single report

### Column Structure<a name="key-column"></a>

DBR has a fixed list of columns, limiting its flexibility\. CUR does not have a fixed column structure, and instead allows you to freely add or remove columns as needed\. When you begin using a new AWS service, CUR can dynamically start to include new data in the report that may be useful in your case\. The manifest file provides a map of all columns present in the report for your ease of use\.


**Equivalent Column Names for DBR and CUR**  

| DBR Column Name | CUR Column Name | 
| --- | --- | 
| InvoiceId | bill/InvoiceId | 
| PayerAccountId | bill/PayerAccountId | 
| LinkedAccountId | lineItem/UsageAccountId | 
| ProductName | product/ProductName | 
| SubscriptionId | reservation/subscriptionid | 
| UsageType | lineItem/UsageType | 
| Operation | lineItem/Operation | 
| AvailabilityZone | lineItem/AvailabilityZone | 
| ReservedInstance | Not Supported | 
| ItemDescription | lineItem/LineItemDescription | 
| UsageStartDate | lineItem/UsageStartDate | 
| UsageEndDate | lineItem/UsageEndDate | 
| UsageQuantity | lineItem/UsageAmount | 
| BlendedRate | lineItem/BlendedRate | 
| BlendedCost | lineItem/BlendedCost | 
| UnBlendedRate | lineItem/UnblendedRate | 
| UnBlendedCost | lineItem/UnblendedCost | 
| ResourceId | lineItem/ResourceId | 
| RecordType | Not Supported | 
| Pricingplanid | Not Supported | 
| RateID | pricing/RateId | 

 


**Retrieving DBR RecordType Values Through CUR**  

| RecordType values in DBR | Syntax to Retrieve RecordType Through CUR | Use Case | 
| --- | --- | --- | 
| LineItem | SELECT SUM\(line\_item\_unblended\_cost\) FROM \[CUR\] WHERE line\_item\_line\_item\_type = 'Usage' | Usage line item partitions out usage costs from one\-time charges\. For example: upfront RI payment  | 
| InvoiceTotal | SELECT \(bill\_invoice\_id\), sum\(line\_item\_unblended\_cost\) FROM \[CUR\] GROUP BY bill\_invoice\_id | Invoice total helps you reconcile your costs between Invoices and the Cost and Usage Report\. | 
| AccountTotal | SELECT line\_item\_usage\_account\_id, sum\(line\_item\_unblended\_cost\) FROM \[CUR\] GROUP BY line\_item\_usage\_account\_id  | Account total helps you isolate costs related to your linked accounts for charge back purposes\. | 
| StatementTotal | SELECT SUM\(line\_item\_unblended\_cost\) FROM \[CUR\] | Statement total helps you understand your costs for the billing period\. | 
| Discount | SELECT SUM\(line\_item\_unblended\_cost\) FROM \[CUR\] WHERE line\_item\_line\_item\_type = 'Discount'  | Discount line items helps you identify all of your discount\-related line items\. | 
| Rounding | Not yet supported | Not yet supported | 

## Reporting on Advanced Charge Types<a name="reporting-advanced-chargetype"></a>

### Refunds<a name="reporting-advanced-refunds"></a>

CUR: Refunds are identified by filtering for the `lineitem/lineitemtype = ‘Refund’` string\.

DBR: Credits can be identified by parsing the ItemDescription column for the `‘Credit’` substring\. 

### Credits<a name="reporting-advanced-credits"></a>

CUR: Refunds are identified by filtering for the `lineitem/lineitemtype = ‘Credit’` string\.

DBR: Refunds are identified through parsing the ItemDescription column for the `‘Refund’` substring\. 

### Taxes<a name="reporting-advanced-taxes"></a>

CUR: Taxes are identified by filtering the `lineitem/lineitemtype = ‘Tax’` string\.

DBR: Taxes are identified by parsing the ItemDescription column for the `‘Tax’` substring\. 

### Identifying Reservation\-Related Upfront Costs<a name="reporting-advanced-upfront"></a>

CUR: Reservation\-related upfront fees can be identified by filtering `"lineitem/lineitemtype" = 'Fee'`\.

DBR: Reservation\-related upfront costs can be identified by examining the Usagetype column for the `'HeavyUsage'` substring, and whether the `'SubscriptionId'` is null\.

### Identifying Reservation\-Related Monthly Fee<a name="reporting-advanced-monthly"></a>

CUR: Reservation\-related monthly fees can be identified by filtering `"lineitem/lineitemtype" = 'RIfee'`\.

DBR: Reservation\-related monthly fees can be identified by examining the Usagetype column for the `'HeavyUsage'` substring\. 

### Identifying Instances That Received Reserved Instance Benefits<a name="identify-benefit-instance"></a>

CUR: Reservation\-related upfront fees can be identified by filtering `"lineitem/lineitemtype" = 'DiscountedUsage'`\.

DBR: Reservation\-related upfront fees can be identified by filtering`'ReservedInstance' = 'Y'`\. 