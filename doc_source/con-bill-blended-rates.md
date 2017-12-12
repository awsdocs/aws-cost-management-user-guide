# Understanding Consolidated Bills<a name="con-bill-blended-rates"></a>

To ensure that you pay the lowest available prices for AWS products and services, AWS offers pricing tiers that reward higher usage with lower prices and discounted rates for purchasing in advance \(Reserved Instances\)\.


+ [Pricing Tiers](#Blended_Rate_Overview)
+ [Reserved Instances: Capacity Reservations](#Capacity_Reservations)
+ [Regional Reserved Instances](#Regional_RI)
+ [Blended Rates](#Blended_CB)

## Pricing Tiers<a name="Blended_Rate_Overview"></a>

Some AWS services are priced in *tiers*, which specify unit costs for defined amounts of AWS usage\. As your usage increases, you cross thresholds into new pricing tiers that specify lower unit costs for additional usage in a month\. Each AWS service publishes its pricing information independently\. You can access all individual pricing pages from the [AWS Pricing](http://aws.amazon.com/pricing/) page\. The AWS whitepaper [ How AWS Pricing Works](https://aws.amazon.com/whitepapers/how-aws-pricing-works/) also discusses usage scenarios and pricing options\.

Your AWS usage is measured every month\. To measure usage, AWS treats all accounts in an organization as a single account\. Member accounts do not reach tier thresholds individually\. Instead, all usage in the organization is aggregated for each service, which ensures faster access to lower\-priced tiers\. As each month begins, your service usage is reset to zero\. For an example, see [Calculating Blended Rates for Amazon S3 Standard Storage](#Blended_S3_Stand_Storage)\.

## Reserved Instances: Capacity Reservations<a name="Capacity_Reservations"></a>

AWS also offers discounted hourly rates in exchange for an upfront fee and term contract\. Services such as Amazon Elastic Compute Cloud \([Amazon EC2](http://aws.amazon.com/ec2/reserved-instances/)\) and Amazon Relational Database Service \([Amazon RDS](http://aws.amazon.com/rds/reserved-instances/)\) use this approach to sell reserved capacity for hourly use of *Reserved Instances*\. For more information, see [Reserved Instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide//concepts-on-demand-reserved-instances.html) in the *Amazon EC2 User Guide for Linux Instances* and [ Working with Reserved DB Instances](http://docs.aws.amazon.com/AmazonRDS/latest/DeveloperGuide/USER_WorkingWithReservedDBInstances.html) in the *Amazon Relational Database Service Developer Guide*\.

When you reserve capacity with Reserved Instances, your hourly usage is calculated at a discounted rate for instances of the same usage type in the same Availability Zone\. When you launch additional instances of the same instance type in the same Availability Zone and exceed the number of instances in your reservation, AWS averages the rates of the Reserved Instances and the On\-Demand Instances to give you a *blended rate*\.

## Regional Reserved Instances<a name="Regional_RI"></a>

Regional Reserved Instances do not reserve capacity\. Instead, they provide Availability Zone and instance size flexibility\. Availability Zone flexibility allows you to run one or more instances in any Availability Zone in your reserved region\. The Reserved Instance discount is applied to any usage in any Availability Zone\. Instance size flexibility provides the Reserved Instance discount to instance usage regardless of size, within that instance family\. Instance size flexibility applies to only regional Reserved Instances on the Linux/Unix platform with default tenancy\. For more information about regional Reserved Instances, see [Reserved Instances](billing-reports-costusage-ri.md) in this documentation and [ Applying Reserved Instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-reserved-instances-application.html#apply_ri) in the [Amazon Elastic Compute Cloud User Guide for Linux Instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/)\.

## Blended Rates<a name="Blended_CB"></a>

Blended rates are the averaged rates of the Reserved Instances and On\-Demand Instances that are used by member accounts in an organization\. This section explains how AWS determines the blended rates for customers who use consolidated billing\. 

**Note**  
Member account consoles show a blended rate that is meant for display purposes only, and does not reflect the actual charges\.

Here is how consolidated bills are calculated: 

1. A Reserved Instance is a capacity reservation that provides discounts\. It is not a virtual machine\. It is a commitment by you to pay in advance for specific Amazon EC2 or Amazon RDS instances\. In return, you get a discounted rate over the cost of an On\-Demand Instance\. From a technical perspective, there is no difference between a Reserved Instance and an On\-Demand Instance\. When you launch an instance, AWS checks the account records for Reserved Instance purchases that can be applied to that instance\.

1. If you use AWS Organizations, you have multiple member accounts that roll up into a single master account\. The master account is responsible for paying for all charges that are incurred by the member accounts\. The owner of the master account sees all usage that is incurred by the organization\. This activity is aggregated to the master account, and then *allocated* to the member accounts that generated the charge in proportion to the member account's usage\. If the master account has usage, that account is also charged\. The bill displays an aggregate view that has no blended costs, and an allocated view that has blended costs for each member account and possibly for the master account\. Blended rates appear only in the allocated bill line items\.
**Note**  
As a best practice, don't run any AWS services under the organization's master account\. This practice helps reduce confusion that can arise because master account usage appears twice in the AWS Cost and Usage and detailed billing reports\. It appears once as an aggregated line item and again as an allocated line item\. 

1. Estimated charges for all accounts are calculated several times each day\. Because blended prices are an average for variable usage across an account family, they are dynamic and vary with each set of calculations\. If you look at each iteration of your daily report, you will probably see different values each time in the Blended Rate column for your discount\-eligible usage\. Blended rates are finalized for the last AWS Cost and Usage report for the month and for your AWS invoice\.

### Blended Rate Examples<a name="Blended_Rate_Examples"></a>

This section contains examples of how blended rates are calculated for the following types of operations: 

+ [Calculating Blended Rates for Amazon S3 Standard Storage](#Blended_S3_Stand_Storage)

+ [Calculating Blended Rates for Amazon EC2](#Blended_Calculated)

#### Calculating Blended Rates for Amazon S3 Standard Storage<a name="Blended_S3_Stand_Storage"></a>

Blended rates for Amazon S3 standard storage are calculated by taking the total cost of storage and dividing by the amount of data stored per month\. The following table shows an example of pricing tiers \(your costs might vary\)\.

**Amazon S3 Pricing Tiers**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The following table shows Amazon S3 usage for an organization that includes a master account and three member accounts\.

**Example S3 Usage Blended Cost**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The costs in the preceding table are calculated as follows: 

1. All usage for the organization adds up to 95 TB or 95,000 GB\. This is rolled up into the master account for recording purposes\. The master account has no usage of its own\. Only the member accounts incur usage\. Member 1 uses 1 TB of storage\. This satisfies the first pricing tier for the organization\. The second pricing tier is satisfied by all three member accounts \(14 TB for member 1 \+ 20 TB for member 2 \+ 15 TB for member 3 = 49 TB\)\. The third pricing tier is applied to any usage over 49 TB\. In this example, the third pricing tier is applied to total member account usage of 45 TB\.

1. The total cost is calculated by adding the cost of the first TB \(1,000 GB \* $0\.10 = 1 TB \* $100\.00 = $100\.00\) to the cost of the next 49 TB \(49,000 GB \* $0\.08 = 49 TB \* $80\.00 = $3920\.00\) and the cost of the remaining 45 TB \(45,000 GB \* $0\.06 = 45 TB \* $60\.00 = $2700\.00\), for a total of $6,720 \($100\.00 \+ $3920\.00 \+ $2700\.00 = $6720\.00\)\. 

1. The blended rate in GB is calculated by dividing the total cost \($6,720\) by the amount of storage \(95,000 GB\) to produce a blended rate of $0\.070737/GB\. The blended rate in TB is calculated by dividing the total cost \($6,720\) by the amount of storage \(95 TB\) to produce a blended rate of $70\.737/TB\.

1. The blended cost for each member account is allocated by multiplying the blended rate \(for GB or TB\) by the usage, resulting in the amounts listed in the Blended Cost column\. For example, Member 1 uses 14,000 GB of storage priced at the blended rate of $0\.070737 \(or 14 TB priced at $70\.737\) for a blended cost of $990\.318\.

The preceding example shows how using consolidated billing in AWS Organizations helps lower the overall monthly cost of storage\. If you calculate the cost for each member account separately, the total cost is $6,780 rather than $6,720\. By aggregating the usage of the three accounts, you reach the lower\-priced tiers sooner\. The most expensive storage, the first TB, is charged at the highest price just once, rather than three times\. For example, three TB of storage at the most expensive rate of $100/TB would result in a charge of $300\. Charging this storage as 1 TB \($100\) and two additional TB at $80 \($160\) results in a total charge of $260\.

#### Calculating Blended Rates for Amazon EC2<a name="Blended_Calculated"></a>

##### Calculation Process<a name="Calculation_Process"></a>

Here's how AWS calculates blended rates for Amazon EC2 instances for organizations: 

1. AWS aggregates usage for all accounts in the organization for the month or partial month and calculates costs based on unblended rates such as rates for On\-Demand and Reserved Instances\. Line items for these costs are created for the master account\. This bill computation model attempts to apply the lowest unblended rates for which each line item is eligible\. The allocation logic first applies Reserved Instance hours, then free tier hours, and then applies On\-Demand rates to any remaining usage\. In the AWS Cost and Usage report, you can see line items for these aggregated costs\.

1. AWS identifies each Amazon EC2 usage type in each region and allocates cost from the aggregated master account to the corresponding member account line items for identical usage types in the same region\. In the AWS Cost and Usage report, the **Unblended Rate** column shows that rate applied to each line item\.
**Note**  
When AWS assigns Reserved Instance hours to member accounts, it always starts with the account that purchased the reservation, which is sometimes called Reserved Instance affinity\. If there are hours from the capacity reservation left over, they are applied to other accounts operating identical usage types in the same Availability Zone\. Again, this allocation always uses unblended rates\. 

1. AWS calculates an average cost for all identical usage in the Availability Zone\. AWS lists the result in each line item in the **Blended Rate** column of the AWS Cost and Usage report\. The calculation of this average can result in lines where the unblended cost for the hour is $0\.00, but the blended rate indicates an allocated cost\. See the following example\.

##### Blended Rate Example<a name="blended-rate-example"></a>

The following example shows how the consolidated billing logic aggregates cost to the master account and then allocates it to the member accounts based on proportional usage\. For this example, all usage is of the same usage type, occurs in the same Availability Zone, and is for the same Reserved Instance term\. This example covers Full Upfront and Partial Upfront Reserved Instances\.

The following table shows line items that represent the calculation of line items for Amazon EC2 usage for a 720\-hour \(30\-day\) month\. Each instance is of the same usage type \(`t2.small`\) running in the same Availability Zone\. The organization has purchased three Reserved Instances for a one\-year term\. Member Account 1 has the three Reserved Instances\. Member Account 2 has no Reserved Instances, but uses an On\-Demand Instance\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The data in the preceding table shows the following information: 

+ The organization has purchased 1,440 hours of Reserved Instance capacity at a Full Upfront rate \(two EC2 instances\)\.

+ The organization has purchased 720 hours of Reserved Instance capacity at a Partial Upfront rate \(one EC2 instance\)\.

+ Member account 1 completely uses the two Full Upfront Reserved Instances and the one Partial Upfront Reserved Instance for a total usage of 2,160 hours\. Member account 2 uses 300 hours of an On\-Demand Instance\. Total usage for the organization is 2,460 hours \(2160 \+ 300 = 2,460\)\.

+ The unblended rate for the three Reserved Instances is $0\.00\. The unblended cost of an RI is always $0\.00 because RI charges are not included in blended rate calculations\.

+ The unblended rate for the On\-Demand Instance is $0\.023\. Unblended rates are associated with the current price of the product\. They cannot be verified from information in the preceding table\. 

+ The blended rate is calculated by dividing the total cost \($6\.90\) by the total amount of Amazon EC2 usage \(2460 hours\)\. This produces a rate of $0\.002804878 dollars per hour\.

You can check that your AWS Cost and Usage report is balanced by ensuring that the sum of the blended costs of each member account line item and the rounding error line item equals the total of all master account line items\. 

**Note**  
You can download the AWS Cost and Usage report into a CSV file and then use an Excel spreadsheet to find the member account line items to balance against master account line items in the report\. To do that, filter on the following columns in the specified order:   
Product Name
Usage Type
Operation