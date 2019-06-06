# Line Item Details<a name="enhanced-lineitem-columns"></a>

Columns under the **lineItem** header are static fields that appear in every AWS Cost and Usage report\. They cover all of the cost and usage information for your usage\. This includes the following columns:

** lineItem/AvailabilityZone**  
The Availability Zone that hosts this line item, such as `us-east-1a` or `us-east-1b` \.

** lineItem/BlendedCost**  
The `BlendedRate` multiplied by the `UsageAmount`\.  
For line items that have a **LineItemType** of **Discount**, **BlendedCost** is blank\. Discounts are calculated using only the unblended cost of a linked account, aggregated by linked account and SKU, so **BlendedCost** is not available for discounts\.

** lineItem/BlendedRate**  
The `BlendedRate` represents the average cost incurred for each SKU across an organization\. For example, the Amazon S3 blended rates are the total cost of storage divided by the amount of data stored per month\. For accounts with RIs, the blended rates are calculated as the average costs of the RIs and the On\-Demand Instances\.  
Blended rates are calculated at the master account level and used to allocate costs to each member account\. For more information, see [Blended Rates and Costs](con-bill-blended-rates.md#Blended_CB)\.

** lineItem/CurrencyCode**  
The currency that this line item is shown in\.

** lineItem/LegalEntity**  
The provider of your AWS services\. Possible values are the following:   
+ **Amazon Web Services, Inc\.** – The entity that sells AWS services\.
+ **Amazon Internet Services Pvt\. Ltd** – The local Indian entity that acts as a reseller for AWS services in India\.

** lineItem/LineItemType**  
The type of charge covered by this line item\. There are seven possible types:  
+ **Credit** – Any credits that AWS applied to your bill\. Check the **Description** column for details\. AWS might update reports after they have been finalized if AWS applies a credit to your account for the month after finalizing your bill\.
+ **DiscountedUsage** – The rate for any instances for which you had Reserved Instance \(RI\) benefits\.
+ **Fee** – Any upfront annual fee that you paid for subscriptions\. For example, the upfront fee that you paid for an **All Upfront RI** or a **Partial Upfront RI**\.
+ **Refund** – Negative charges that AWS refunded money to you for\. Check the **Description** column for details\. AWS might update reports after they have been finalized if AWS applies a refund to your account for the month after finalizing your bill\.
+ **RIFee** – The monthly recurring fee for subscriptions\. For example, the recurring fee for **Partial Upfront RI**s, **No Upfront RI**s, and **All Upfront**s that you pay every month\.
+ **Tax** – Any taxes that AWS applied to your bill: for example, VAT or US sales tax\.
+ **Usage** – Any usage that is charged at On\-Demand Instance rates\.

** lineItem/LineItemDescription**  
The description of the line item type\. For example, the description of a usage line item summarizes what type of usage you incurred during a specific time period\.   
For size\-flexible RIs, the description corresponds to the RI whose benefit was applied\. For example, if a line item corresponds to a `t2.micro` and a `t2.small` RI was applied to the usage, the line item/description displays `t2.small`\.   
The description for a usage line item with an RI discount contains the pricing plan covered by the line item\.

** lineItem/NormalizationFactor**  
AWS can apply all regional Linux or Unix Amazon EC2 and Amazon RDS RI discounts to all instance sizes in an instance family and AWS Region, as long as the instance has shared tenancy\. This also applies to RI discounts for member accounts in an organization\. All new and existing Amazon EC2 and Amazon RDS size\-flexible RIs are sized according to a normalization factor that is based on the instance size\. The following table shows the normalization factor that AWS applies to each instance size\.    
**Normalization Factors for Amazon EC2 Size\-Flexible RIs**    
<a name="aws-normalization-factors"></a>[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/enhanced-lineitem-columns.html)

** lineItem/NormalizedUsageAmount**  
The amount of usage that you incurred, in normalized units, for size\-flexible RIs\. The **NormalizedUsageAmount** is equal to **UsageAmount** multiplied by **NormalizationFactor**\.

** lineItem/Operation**  
The specific AWS operation covered by this line item\. Describes the specific usage of the line item\. For example, a value of `RunInstances` indicates the operation of an Amazon EC2 instance\.

** lineItem/ProductCode**  
The product code of the product measured by this line item\. For example, Amazon EC2 is the product code for Amazon Elastic Compute Cloud\.

** \(Optional\) lineItem/ResourceId**  
If you chose to include individual resources IDs in your report, this column contains the ID of the resource that you provisioned\. For example, an Amazon S3 storage bucket, an Amazon EC2 compute instance, or an Amazon RDS database can each have a resource ID\. This field is blank for usage types that aren't associated with an instantiated host, such as data transfers and API requests, and line item types such as discounts, credits, and taxes\. The following table shows a list of resource identifiers for common AWS services\.    
**AWS Resource Identifiers**    
<a name="aws-resource-identifiers"></a>[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/enhanced-lineitem-columns.html)

** lineItem/TaxType**  
The type of tax that AWS applied to this line item\. 

** lineItem/UnblendedCost**  
The `UnblendedCost` comes from the `UnblendedRate` multiplied by the `UsageAmount`\.

** lineItem/UnblendedRate**  
The uncombined rate for specific usage\. For line items that have an RI discount applied to them, the `UnblendedRate` is zero\. Line items with an RI discount have a `UsageType` of `Discounted Usage`\.

** lineItem/UsageAccountId**  
The ID of the account that used this line item\. For organizations, this can be either the master account or a member account\. You can use this field to track costs or usage by account\. 

** lineItem/UsageAmount**  
The amount of usage that you incurred during the specified time period\. For size\-flexible reserved instances, use the **reservation/TotalReservedUnits** column instead\.

** lineItem/UsageEndDate**  
The end date and time for the corresponding line item in UTC, exclusive\. The format is `YYYY-MM-DDTHH:mm:ssZ`\.

** lineItem/UsageStartDate**  
The start date and time for the line item in UTC, inclusive\. The format is `YYYY-MM-DDTHH:mm:ssZ`\. 

** lineItem/UsageType**  
The usage details of this line item\. For example, `USW2-BoxUsage:m2.2xlarge` describes an M2 High Memory Double Extra Large instance in the US West \(Oregon\) Region\.