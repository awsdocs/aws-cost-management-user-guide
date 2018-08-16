# Line Item Details<a name="enhanced-lineitem-columns"></a>

Columns under the **lineItem** header are static fields that appear in every AWS Cost and Usage report\. They cover all of the cost and usage information for your usage\. This includes the following columns:

** lineItem/UsageAccountId**  
The ID of the account that used this line item\. For organizations, this can be either the master or a member account\. You can use this field to track costs or usage by account\. 

** lineItem/LineItemType**  
The type of charge covered by this line item\. There are seven possible types:  

+ **Credit** \- Any credits that AWS applied to your bill\. Check the **Description** column for details\.

+ **DiscountedUsage** \- The rate for any instances for which you had RI benefits\.

+ **Fee** \- Any upfront annual fee that you paid for subscriptions\. For example, the upfront fee that you paid for an **All Upfront RI** or a **Partial Upfront RI**\.

+ **Refund** \- Negative charges for which AWS refunded money to you\. Check the **Description** column for details\.

+ **RIFee** \- The monthly recurring fee for subscriptions\. For example, the recurring fee for **Partial Upfront RI**s and **No Upfront RI**s that you pay every month\.

+ **Tax** \- Any taxes that AWS applied to your bill\. For example, VAT, US Sales Tax, and so on\.

+ **Usage** \- Any usage that is charged at On\-Demand Instancerates\.

** lineItem/UsageStartDate**  
The start date and time for the line item in UTC, inclusive\. The format is YYYY\-MM\-DDTHH:mm:ssZ\. 

** lineItem/UsageEndDate**  
The end date and time for the corresponding line item in UTC, exclusive\. The format is YYYY\-MM\-DDTHH:mm:ssZ\.

** lineItem/ProductCode**  
The product code of the product measured by this line item\. For example, Amazon EC2 is the product code for Amazon Elastic Compute Cloud\.

** lineItem/UsageType**  
The usage details of this line item\. For example, `USW1-BoxUsage:m2.2xlarge` describes an M2 High Memory Double Extra Large instance in the US West \(Oregon\) Region\.

** lineItem/Operation**  
The specific AWS operation covered by this line item\. Describes the specific usage of the line item\. For example, a value of `RunInstances` indicates the operation of an Amazon EC2 instance\.

** lineItem/Region**  
The geographical area that hosts your AWS services, such as `us-east-1`\. You can use this field to analyze your spend across a specific region\.

** lineItem/AvailabilityZone**  
The Availability Zone that hosts this line item, such as `us-east-1a` or `us-east-1b` \.

** \(Optional\) lineItem/ResourceId**  
If you chose to include individual resources IDs in your report, this column contains the ID of the resource that you provisioned\. For example, an S3 storage bucket, EC2 compute instance, or RDS database can all have a resource ID\. This field is blank for usage types that are not associated with an instantiated host, such as data transfers and API requests, and line item types such as discounts, credits, and taxes\. The following table shows a list of resource identifiers for common AWS services\.    
**AWS Resource Identifiers**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/enhanced-lineitem-columns.html)

** lineItem/UsageAmount**  
The amount of usage that you incurred during the given time period\. For all reserved units, use the **reservation/TotalReservedUnits** column instead\.

** lineItem/NormalizationFactor**  
AWS can apply all regional Linux/UNIX Amazon EC2 and Amazon RDS RI discounts to all instance sizes in an instance family and AWS Region, as long as the instance has shared tenancy\. This also applies to RI discounts for member accounts in an organization\. All new and existing EC2 and RDS size\-flexible RIs are sized according to a normalization factor that is based on the instance size\. The following table shows the normalization factor that AWS applies to each instance size\.    
**Normalization Factors for EC2 size\-flexible RIs**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/enhanced-lineitem-columns.html)

** lineItem/NormalizedUsageAmount**  
The amount of usage that you incurred, in normalized units, for size\-flexible RIs\. The `NormalizedUsageAmount` is equal to `UsageAmount` multiplied by `NormalizationFactor`\.

** lineItem/CurrencyCode**  
The currency that this line item is shown in\.

** lineItem/UnblendedRate**  
The uncombined rate for specific usage\. For line items that have an RI discount applied to them, the `UnblendedRate` is zero\. Line items with an RI discount have a `UsageType` of `Discounted Usage`\.

** lineItem/UnblendedCost**  
The `UnblendedCost` comes from the `UnblendedRate` multiplied by the `UsageAmount`\.

** lineItem/BlendedRate**  
The `BlendedRate` represents the average cost incurred for each SKU across an organization\. For example, the Amazon S3 blended rates are the total cost of storage divided by the amount of data stored per month\. For accounts with RIs, the blended rates are calculated as the average costs of the Reserved Instances and the On\-Demand Instances\.  
Blended rates are calculated at the master account level and used to allocate costs to each member account\. For more information, see [Blended Rates](con-bill-blended-rates.md#Blended_CB)\.

** lineItem/BlendedCost**  
The `BlendedRate` multiplied by the `UsageAmount`\.

** lineItem/LineItemDescription**  
The description of the line item type\. For example, the description of a usage line item summarizes what type of usage you incurred during a specific time period\.   
For size\-flexible RIs, the description corresponds to the RI whose benefit was applied\. For example, if a line item corresponds to a `t2.micro` and a `t2.small` RI was applied to the usage, the line item/description displays `t2.small`\.   
The description for a usage line item with an RI discount contains the pricing plan covered by the line item\.

** lineItem/TaxType**  
The type of tax that AWS applied to this line item\. 
