# Understanding Consolidated Bills<a name="con-bill-blended-rates"></a>

If you manage an organization in AWS Organizations, you can use consolidated billing to view aggregated usage costs for accounts in the organization\. Consolidated billing can also help you reduce those costs\. For example, to ensure that you pay the lowest available prices for AWS products and services, AWS offers pricing tiers that reward higher usage with lower prices and discounted rates for purchasing instances in advance \(known as *reservations* or *Reserved Instances*\)\. Using consolidated billing, you can combine usage from multiple accounts into a single invoice, allowing you to reach the tiers with lower prices faster\. You can also apply unused reservations from one account to another account's instance usage\.

**Topics**
+ [Calculating Consolidated Bills](#Calculating)
+ [Pricing Tiers](#Blended_Rate_Overview)
+ [Reserved Instances](#Instance_Reservations)
+ [Savings Plans](#cb_savingsplans)
+ [Blended Rates and Costs](#Blended_CB)

## Calculating Consolidated Bills<a name="Calculating"></a>

In an organization, the management account is responsible for paying all charges that the member accounts incur\. If you're an administrator of a management account and you have the appropriate permissions, you can view aggregated usage costs for Reserved Instance discounts and volume tiering for all member accounts\. You can also view the charges that individual member accounts incur, because AWS creates a separate bill for each member account based on that account’s usage\. AWS also includes invoice summaries for each account in the management account invoice\. During each billing period, AWS calculates your estimated charges several times each day so that you can track your costs as your organization incurs them\. Your bill is not finalized until the beginning of the next month\.

**Note**  
Like member accounts, a management account can incur usage charges\. However, as a best practice you shouldn't use the management account to run AWS services\. An exception is for services and resources that are required to manage the organization itself\. For example, as part of managing your consolidated billing you might create an S3 bucket in the management account to store AWS Cost and Usage Reports\. 

## Pricing Tiers<a name="Blended_Rate_Overview"></a>

Some AWS services are priced in *tiers*, which specify unit costs for defined amounts of AWS usage\. As your usage increases, your usage crosses thresholds into new pricing tiers that specify lower unit costs for additional usage in a month\. Your AWS usage is measured every month\. To measure usage, AWS treats all accounts in an organization as a single account\. Member accounts don't reach tier thresholds individually\. Instead, all usage in the organization is aggregated for each service, which ensures faster access to lower\-priced tiers\. As each month begins, your service usage is reset to zero\.

Each AWS service publishes its pricing information independently\. You can access all individual pricing pages from the [AWS Pricing](http://aws.amazon.com/pricing/) page\.



### Calculating Costs for Amazon S3 Standard Storage<a name="tier-example"></a>

The following table shows an example of pricing tiers \(your costs might vary\)\. 

**Amazon S3 Pricing Tiers**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The following table shows Amazon S3 usage for an organization that includes a management account and three member accounts\. 

**Example S3 Usage Blended Cost**

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The costs in the preceding table are calculated as follows: 

1. All usage for the organization adds up to 95 TB or 95,000 GB\. This is rolled up into the management account for recording purposes\. The management account has no usage of its own\. Only the member accounts incur usage\. Member 1 uses 1 TB of storage\. This satisfies the first pricing tier for the organization\. The second pricing tier is satisfied by all three member accounts \(14 TB for member 1 \+ 20 TB for member 2 \+ 15 TB for member 3 = 49 TB\)\. The third pricing tier is applied to any usage over 49 TB\. In this example, the third pricing tier is applied to total member account usage of 45 TB\.

1. The total cost is calculated by adding the cost of the first TB \(1,000 GB \* $0\.10 = 1 TB \* $100\.00 = $100\.00\) to the cost of the next 49 TB \(49,000 GB \* $0\.08 = 49 TB \* $80\.00 = $3920\.00\) and the cost of the remaining 45 TB \(45,000 GB \* $0\.06 = 45 TB \* $60\.00 = $2700\.00\), for a total of $6,720 \($100\.00 \+ $3920\.00 \+ $2700\.00 = $6720\.00\)\. 

The preceding example shows how using consolidated billing in AWS Organizations helps lower the overall monthly cost of storage\. If you calculate the cost for each member account separately, the total cost is $6,780 rather than $6,720\. By aggregating the usage of the three accounts, you reach the lower\-priced tiers sooner\. The most expensive storage, the first TB, is charged at the highest price just once, rather than three times\. For example, three TB of storage at the most expensive rate of $100/TB would result in a charge of $300\. Charging this storage as 1 TB \($100\) and two additional TB at $80 \($160\) results in a total charge of $260\.

## Reserved Instances<a name="Instance_Reservations"></a>

AWS also offers discounted hourly rates in exchange for an upfront fee and term contract\.

### Zonal Reserved Instances<a name="Capacity_Reservations"></a>

A Reserved Instance is a reservation that provides a discounted hourly rate in exchange for an upfront fee and term contract\. Services such as Amazon Elastic Compute Cloud \([Amazon EC2](http://aws.amazon.com/ec2/reserved-instances/)\) and Amazon Relational Database Service \([Amazon RDS](http://aws.amazon.com/rds/reserved-instances/)\) use this approach to sell reserved capacity for hourly use of *Reserved Instances*\. It is not a virtual machine\. It is a commitment to pay in advance for specific Amazon EC2 or Amazon RDS instances\. In return, you get a discounted rate as compared to On\-Demand Instance usage\. From a technical perspective, there is no difference between a Reserved Instance and an On\-Demand Instance\. When you launch an instance, AWS checks for qualifying usage across all accounts in an organization that can be applied to an active reservation\. For more information, see [Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-on-demand-reserved-instances.html) in the *Amazon EC2 User Guide for Linux Instances* and [ Working with Reserved DB Instances](https://docs.aws.amazon.com/AmazonRDS/latest/DeveloperGuide/USER_WorkingWithReservedDBInstances.html) in the *Amazon Relational Database Service Developer Guide*\.

When you reserve capacity with Reserved Instances, your hourly usage is calculated at a discounted rate for instances of the same usage type in the same Availability Zone\. 

### Regional Reserved Instances<a name="Regional_RI"></a>

Regional Reserved Instances don't reserve capacity\. Instead, they provide Availability Zone flexibility and in certain cases instance size flexibility\. Availability Zone flexibility allows you to run one or more instances in any Availability Zone in your reserved AWS Region\. The Reserved Instance discount is applied to any usage in any Availability Zone\. Instance size flexibility provides the Reserved Instance discount to instance usage regardless of size, within that instance family\. Instance size flexibility applies to only regional Reserved Instances on the Linux/Unix platform with default tenancy\. For more information about regional Reserved Instances, see see [Reservation Details](https://docs.aws.amazon.com/cur/latest/userguide/reservation-columns.html) in the *Cost and Usage Reports Guide* in this documentation and [ Applying Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-reserved-instances-application.html#apply_ri) in the [Amazon Elastic Compute Cloud User Guide for Linux Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/)\.

### Calculating Costs for Amazon EC2 with Reserved Instances<a name="Blended_Calculated"></a>

AWS calculates the charges for Amazon EC2 instances by aggregating all the EC2 usage for a specific instance type in a specific AWS Region for an organization\.

#### Calculation Process<a name="Calculation_Process"></a>

AWS calculates blended rates for Amazon EC2 instances using the following logic:

1. AWS aggregates usage for all accounts in an organization for the month or partial month, and calculates costs based on unblended rates such as rates for On\-Demand and Reserved Instances\. Line items for these costs are created for the management account\. This bill computation model attempts to apply the lowest unblended rates that each line item is eligible for\. The allocation logic first applies Reserved Instance hours, then free tier hours, and then On\-Demand rates to any remaining usage\. In the AWS Cost and Usage Reports, you can see line items for these aggregated costs\.

1. AWS identifies each Amazon EC2 usage type in each AWS Region and allocates cost from the aggregated management account to the corresponding member account line items for identical usage types in the same region\. In the AWS Cost and Usage Reports, the **Unblended Rate** column shows that rate applied to each line item\.
**Note**  
When AWS assigns Reserved Instance hours to member accounts, it always starts with the account that purchased the reservation\. If there are hours from the capacity reservation left over, AWS applies them to other accounts that operate identical usage types in the same Availability Zone\.  
AWS allocates a regional RI by instance size: The RI is applied first to the smallest instance in the instance family, then to the next smallest, and so on\. AWS applies an RI or a fraction of an RI based on the [normalization factor](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/apply_ri.html#apply-regional-ri) of the instance\. The order in which AWS applies RIs doesn't result in a price difference\.

## Savings Plans<a name="cb_savingsplans"></a>

Savings Plans is a flexible pricing model that can help you reduce your AWS usage bill\. Compute Savings Plans enables you to commit to an amount each hour, and receive discounted Amazon EC2, Fargate, and AWS Lambda usage up to that amount\.

### Calculating Costs with Savings Plans<a name="cb_calculating_sp"></a>

AWS calculates the charges for Amazon EC2, Fargate, and AWS Lambda by aggregating all usage that's not covered by Reserved Instances, and applying the Savings Plans rates starting with the highest discount\.

The Savings Plans are applied to the account that owns the Savings Plans\. Then, it is shared with other accounts in the AWS organization\. For more information, see [Understanding How Savings Plans are Applied to Your Usage](https://docs.aws.amazon.com/savingsplans/latest/userguide/sp-applying.html) in the *Savings Plans User Guide*\.

## Blended Rates and Costs<a name="Blended_CB"></a>

Blended rates are the averaged rates of the Reserved Instances and On\-Demand Instances that are used by member accounts in an organization in AWS Organizations\. AWS calculates blended costs by multiplying the blended rate for each service with an account’s usage of that service\.

**Note**  
AWS shows each member account their charges as unblended costs\. AWS continues to apply all of the consolidated billing benefits such as reservations and tiered prices across all member accounts in an AWS Organizations organization\. 

 This section includes examples that show how AWS calculates blended rates for the following services\.
+ [Calculating Blended Rates for Amazon S3 Standard Storage](#Blended_S3_Stand_Storage)
+ [ Calculating Blended Rates for Amazon EC2 ](#blended-rate-example)

### <a name="Blended_Rate_Examples"></a>

#### Calculating Blended Rates for Amazon S3 Standard Storage<a name="Blended_S3_Stand_Storage"></a>

AWS calculates blended rates for Amazon S3 standard storage by taking the total cost of storage and dividing by the amount of data stored per month\. Using the example from [Calculating Consolidated Bills](#Calculating) where we calculated a cost of $6,720 for a management account and three member accounts, we calculate the blended rates for the accounts using the following logic:

1. The blended rate in GB is calculated by dividing the total cost \($6,720\) by the amount of storage \(95,000 GB\) to produce a blended rate of $0\.070737/GB\. The blended rate in TB is calculated by dividing the total cost \($6,720\) by the amount of storage \(95 TB\) to produce a blended rate of $70\.737/TB\.

1. The blended cost for each member account is allocated by multiplying the blended rate \(for GB or TB\) by the usage, resulting in the amounts listed in the Blended Cost column\. For example, Member 1 uses 14,000 GB of storage priced at the blended rate of $0\.070737 \(or 14 TB priced at $70\.737\) for a blended cost of $990\.318\.

#### Calculating Blended Rates for Amazon EC2<a name="blended-rate-example"></a>

The following example shows how the consolidated billing logic aggregates Amazon EC2 costs to the management account and then allocates it to the member accounts based on proportional usage\. For this example, all usage is of the same usage type, occurs in the same Availability Zone, and is for the same Reserved Instance term\. This example covers Full Upfront and Partial Upfront Reserved Instances\.

The following table shows line items that represent the calculation of line items for Amazon EC2 usage for a 720\-hour \(30\-day\) month\. Each instance is of the same usage type \(`t2.small`\) running in the same Availability Zone\. The organization has purchased three Reserved Instances for a one\-year term\. Member Account 1 has three Reserved Instances\. Member Account 2 has no Reserved Instances, but uses an On\-Demand Instance\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The data in the preceding table shows the following information: 
+ The organization has purchased 1,440 hours of Reserved Instance capacity at a Full Upfront rate \(two EC2 instances\)\.
+ The organization has purchased 720 hours of Reserved Instance capacity at a Partial Upfront rate \(one EC2 instance\)\.
+ Member account 1 completely uses the two Full Upfront Reserved Instances and the one Partial Upfront Reserved Instance for a total usage of 2,160 hours\. Member account 2 uses 300 hours of an On\-Demand Instance\. Total usage for the organization is 2,460 hours \(2160 \+ 300 = 2,460\)\.
+ The unblended rate for the three Reserved Instances is $0\.00\. The unblended cost of an RI is always $0\.00 because RI charges are not included in blended rate calculations\.
+ The unblended rate for the On\-Demand Instance is $0\.023\. Unblended rates are associated with the current price of the product\. They can't be verified from information in the preceding table\. 
+ The blended rate is calculated by dividing the total cost \($6\.90\) by the total amount of Amazon EC2 usage \(2460 hours\)\. This produces a rate of $0\.002804878 dollars per hour\.