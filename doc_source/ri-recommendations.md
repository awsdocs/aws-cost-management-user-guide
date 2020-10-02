# Accessing Reserved Instance Recommendations<a name="ri-recommendations"></a>

If you enable Cost Explorer, you automatically get Amazon EC2, Amazon RDS, ElastiCache, Amazon ES, and Amazon Redshift Reserved Instance \(RI\) purchase recommendations that could help you reduce your costs\. RIs provide a discounted hourly rate \(up to 75%\) compared to On\-Demand pricing\. Cost Explorer generates your RI recommendations using the following process:
+ Identifies your On\-Demand Instance usage for a service during a specific time period
+ Collects your usage into categories that are eligible for an RI
+ Simulates every combination of RIs in each category of usage
+ Identifies the best number of each type of RI to purchase to maximize your estimated savings

For example, Cost Explorer automatically aggregates your Amazon EC2 Linux, shared tenancy, and c4 family usage in the US West \(Oregon\) Region and recommends that you buy size\-flexible regional RIs to apply to the c4 family usage\. Cost Explorer recommends the smallest size instance in an instance family\. This makes it easier to purchase a size\-flexible RI\. Cost Explorer also shows the equal number of normalized units so that you can purchase any instance size that you want\. For this example, your RI recommendation would be for `c4.large` because that is the smallest size instance in the c4 instance family\.

Cost Explorer recommendations are based on a single account or organization usage of the past seven, 30, or 60 days\. Cost Explorer ignores usage that is already covered by an RI\. Amazon EC2, ElastiCache, Amazon ES, and Amazon Redshift recommendations are for RIs scoped to Region, not Availability Zones, and your estimated savings reflects the application of those RIs to your usage\. Amazon RDS recommendations are scoped to either Single\-AZ or Multi\-AZ RIs\. Cost Explorer updates your recommendations at least once every 24 hours\.

**Note**  
Cost Explorer doesn't forecast your usage or take forecasts into account when recommending RIs\. Instead, Cost Explorer assumes that your historical usage reflects your future usage when determining which RIs to recommend\. 

Linked accounts can see recommendations only if they have the relevant permissions\. Linked accounts need permissions to view Cost Explorer and permissions to view recommendations\. For more information, see [Viewing the Cost Explorer Reservation Recommendations](#viewing-rex)\.

**Topics**
+ [RI Recommendations for Size\-Flexible RIs](#rex-flex)
+ [Viewing the Cost Explorer Reservation Recommendations](#viewing-rex)
+ [Reading the Cost Explorer RI Recommendations](#reading-rex)
+ [Modifying Your RI Recommendations](#modifying-rex)
+ [Saving Your RI Recommendations](#saving-rex)
+ [Using Your RI Recommendations](#using-rex)

## RI Recommendations for Size\-Flexible RIs<a name="rex-flex"></a>

Cost Explorer also considers the benefits of size\-flexible regional RIs when generating your RI purchase recommendations\. Size\-flexible regional RIs help maximize your estimated savings across eligible instance families in your recommendations\. AWS uses the concept of normalized units to compare the various sizes within an instance family\. Cost Explorer uses the smallest normalization factor to represent the instance type that it recommends\. For more information, see [Instance Size Flexibility for EC2 Reserved Instances](https://aws.amazon.com/blogs/aws/new-instance-size-flexibility-for-ec2-reserved-instances)\.

For example, let’s say you own an EC2 RI for a `c4.8xlarge`\. This RI applies to any usage of a `Linux/Unix c4` instance with shared tenancy in the same region as the RI, such as the following instances:
+ One `c4.8xlarge` instance
+ Two `c4.4xlarge` instances
+ Four `c4.2xlarge` instances
+ Sixteen `c4.large` instances

It also includes combinations of EC2 usage, such as one `c4.4xlarge` and eight `c4.large` instances\.

If you own an RI that is smaller than the instance that you're running, you are charged the prorated, On\-Demand price for the excess\. This means that you could buy an RI for a `c4.4xlarge`, use a `c4.4xlarge` instance most of the time, but occasionally scale up to a `c4.8xlarge` instance\. Some of your `c4.8xlarge` usage is covered by the purchased RI, and the rest is charged at On\-Demand prices\. For more information, see [How Reserved Instances Are Applied](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/apply_ri.html) in the *Amazon Elastic Compute Cloud User Guide*\.

## Viewing the Cost Explorer Reservation Recommendations<a name="viewing-rex"></a>

Linked accounts need the following permissions to view recommendations:
+ `ViewBilling`
+ `ViewAccount`

For more information, see [Using identity\-based policies \(IAM policies\) for Billing and Cost Management](billing-permissions-ref.md)\.

**To view your RI recommendations**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

   The console opens to the **Dashboard**, where you can see your current month\-to\-date usage graphs\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the **Cost Explorer** page, choose **Launch Cost Explorer**\.

1. On the navigation bar, choose the menu\. Under **Select a service**, choose the service that you want recommendations for\. The default recommendation is for RIs with a one\-year term and a payment option of Partial Upfront \(based on your previous 30 days of usage\)\.

## Reading the Cost Explorer RI Recommendations<a name="reading-rex"></a>

The RI recommendation page shows you your estimated potential savings, your RI purchase recommendations, and the parameters that Cost Explorer used to create your recommendations\. You can change the parameters to get recommendations that might match your use case more closely\.

The top of the RI recommendations page show you three numbers:
+ **Estimated Annual Savings** – Your **Estimated Annual Savings** is how much Cost Explorer calculates that you could save by purchasing all the recommended RIs\.
+ **Savings vs\. On\-Demand** – Your **Savings vs\. On\-Demand** is your estimated savings as a percentage of your current costs\.
+ **Purchase Recommendations** – Your **Purchase Recommendations** is how many different RI purchase options that Cost Explorer found for you\.

These numbers enable you to see a rough estimate of how much you could potentially save by buying more RIs\. You can recalculate these numbers for a different use case by using the parameters in the pane on the right\. The pane allows you to change the following parameters:
+ **RI term** – The length of the RI reservation that you want recommendations for\.
+ **Offering class** – Whether you want recommendations for a standard RI or a convertible RI\.
+ **Payment option** – Whether you want to pay for recommended RIs upfront\.
+ **Based on the past** – How many days of your previous instance usage that you want your recommendations to take into account\.

At the bottom of the page are tabs with some of your savings estimates\. The **All accounts** tab enables you to see the recommendations based on the combined usage across your entire organization, and the **Individual accounts** tab enables you to see recommendations that Cost Explorer generated on a per\-linked\-account basis\. The table on each tab shows the different purchase recommendations and details about the recommendations\. If you want to see the usage that Cost Explorer based a recommendation on, choose the **View associated usage** link in the recommendation details\. This takes you to a report that shows the exact parameters that Cost Explorer used to generate your recommendation\. The report also shows your costs and associated usage grouped by **Purchase option**, so that you can view the On\-Demand Instance usage that your recommendation is based on\.

**Note**  
Recommendations that Cost Explorer bases on an individual linked account consider all usage by that linked account, including any RIs used by that linked account\. This includes RIs shared by another linked account\. The recommendations don't assume that an RI will be shared with the linked account in the future\. 

You can sort your recommendations by **Monthly estimated savings**, **Upfront RI cost**, **Purchase recommendation**, or **Instance type**\.

## Modifying Your RI Recommendations<a name="modifying-rex"></a>

You can change the information that Cost Explorer uses when it creates your recommendations, and you can also change the types of recommendations that you want\. This allows you to see recommendations for the RIs that work best for you, such as All UpFront RIs with a one\-year term, based on your last 30 days of usage\. 

**Note**  
Instead of forecasting your future usage, Cost Explorer assumes that your future usage is the same as your previous usage\. Cost Explorer also assumes that you are renewing any expiring RIs\.<a name="modify-rex"></a>

**To modify your RI recommendations**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

   The console opens to the **Dashboard**, where you can see your current month\-to\-date usage graphs\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the **Cost Explorer** page, choose **Launch Cost Explorer**\.

1. On the navigation bar, choose the menu, choose **RI Recommendations** and then under **Select a service** choose the service that you want to modify the recommendations for\.

1. In the **RI Recommendation Parameters** pane, change the parameters that you want to change\. Your estimated savings update automatically\.

   1. For **RI term**, select the RI term that you want\.

   1. For **Offering class**, select the RI class that you want\.

   1. For **Payment option**, select the purchase option that you want\.

   1. For **Recommendation type**, select the logic that you want your recommendations based on\.

   1. For **Based on the past**, select how many days of usage that you want your RI recommendations to be based on\.

1. Choose either **All accounts** or **Individual accounts** to see recommendations based either on your organization\-wide usage or on all of your linked accounts based on their individual account usage\.

## Saving Your RI Recommendations<a name="saving-rex"></a>

You can save your RI recommendations as a CSV file\.<a name="save-rex"></a>

**To save your RI recommendations**

1. On the **Reserved Instance Recommendations** page, in the RI parameter pane, change any parameters that you want to change\. Your estimated savings update automatically\.

1. Above the recommendation table, choose **Download CSV**\.

The CSV file contains the following columns\.


**RI Recommendation CSV Columns**  

|  Column Name  | Service |  Column Explanation  | 
| --- | --- | --- | 
|  Average hourly normalized unit usage in Historical Period   | EC2, RDS |  The average number of normalized units used per hour over the period chosen for generating recommendations\.  | 
|  Average hourly usage in Historical Period   | EC2, RDS, RS, ELC, ES |  The average number of instance hours used per hour over the period chosen for generating recommendations\.  | 
|  Break Even Months  | EC2, RDS, RS, ELC, ES |  The estimated length of time before you recoup your upfront costs for this set of recommended reservations\.  | 
| Cache Engine | ELC | The kind of engine that the recommended ElastiCache reserved node runs, such as Redis or Memcheched\. | 
| Database Edition | RDS | The edition of the database engine that the recommended RDS reserved instance runs\. | 
| Database Engine | RDS | The kind of engine that the recommended RDS RI runs, such as Aurora MySQL or MariaDB\. | 
| Deployment Option | RDS | Whether your RI is for an RDS instance in a single Availability Zone or an RDS instance with a backup in another Availability Zone\. | 
|  Instance Type   | EC2, RDS, ES |  The type of instance that the recommendation is generated for \(for example, `m4.large` or `t2.nano`\)\. For size\-flexible recommendations, Cost Explorer aggregates all usage in a organization \(for example, the m4 family\) and shows a recommendation for the smallest instance type RI that is available for purchase \(for example, `m4.large`\)\.  | 
|  Location   | EC2, RDS, RS, ELC, ES |  The region of the instances used to generate a recommendation\. You must purchase the recommended RIs in the recommended region to see potential savings\.  | 
|  Max hourly normalized unit usage in Historical Period   | EC2, RDS |  The maximum number of normalized units used in an hour over the period chosen for generating recommendations\.  | 
|  Max hourly usage in Historical Period   | EC2, RDS, RS, ELC, ES |  The maximum number of instance hours used in an hour over the period chosen for generating recommendations\.  | 
|  Min hourly normalized unit usage in Historical Period   | EC2, RDS |  The minimum number of normalized units used in an hour over the period chosen for generating recommendations\.  | 
|  Min hourly usage in Historical Period   | EC2, RDS, RS, ELC, ES |  The minimum number of instance hours used in an hour over the period chosen for generating recommendations\.  | 
|  Node Type   | ELC, RS |  The type of node that the recommendation is generated for, such as `ds2.xlarge`\.  | 
|  OS   | EC2 |  The operating system and license model for the recommended RI instance type\.  | 
|  Owner Account   | EC2, RDS, RS, ELC, ES |  The account associated with your recommendation\.  | 
|  Payment Option   | EC2, RDS, RS, ELC, ES |  The recommended payment option for the recommendation\.  | 
|  Projected RI Utilization   | EC2, RDS, RS, ELC, ES |  How much of the recommended RI Cost Explorer estimates you will use\.  | 
|  Recommendation Date  | EC2, RDS, RS, ELC, ES |  The date that Cost Explorer generated your recommendation\.  | 
|  Recommended Instance Quantity Purchase   | EC2, RDS |  How many reservations Cost Explorer recommends that you buy\.  | 
|  Recommended Normalized Unit Quantity Purchase  | EC2, RDS, RS, ELC, ES |  How many normalized units that Cost Explorer recommends that you buy\.  | 
|  Recurring Monthly Cost   | EC2, RDS, RS, ELC, ES |  The recurring monthly cost of the recommended reservations\.  | 
|  Size Flexible Recommendation   | EC2, RDS |  Whether a recommended RI is size\-flexible\.  | 
|  Tenancy   | EC2 |  The tenancy for the recommended RI purchase\. Valid values are **shared** or **dedicated**\.  | 
|  Term  | EC2, RDS, RS, ELC, ES |  The recommended term length for the recommendation\.  | 

## Using Your RI Recommendations<a name="using-rex"></a>

To purchase the recommended reservations, go to the purchase page on a service console\. You can also save a CSV file of your recommendations and purchase the reservations at a later date\. <a name="use-rex-ec2"></a>

**To use Amazon Elastic Compute Cloud recommendations**

1. On the **Reserved Instance Recommendations** page, choose [Amazon EC2 RI Purchase Console](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#ReservedInstances:sort=reservedInstancesId) to go to the Amazon EC2 Purchase Console\.

1. Purchase your RIs by following the instructions at [Buying Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-concepts-buying.html) in the *Amazon EC2 User Guide for Linux Instances*\.<a name="use-rex-rds"></a>

**To use Amazon Relational Database Service recommendations**

1. On the **Reserved Instances** page in the Amazon RDS console, choose **Purchase Reserved DB Instance**\. 

1. Purchase your reservations by following the instructions at [Working with Reserved DB Instances](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithReservedDBInstances.html) in the *Amazon RDS User Guide*\.<a name="use-rex-rs"></a>

**To use Amazon Redshift recommendations**

1. On the **Reserved Node** page in the Amazon Redshift console, choose **Purchase Reserved Nodes**\. 

1. Purchase your reservations by following the instructions at [Purchasing a Reserved Node Offering with the Amazon Redshift Console](https://docs.aws.amazon.com/redshift/latest/mgmt/purchase-reserved-node-offering-console.html) in the *Amazon Redshift Cluster Management Guide*\.<a name="use-rex-es"></a>

**To use Amazon Elasticsearch Service recommendations**

1. On the **Reserved Instances** page in the Amazon ES console, choose **Purchase Reserved Instance**\. 

1. Purchase your reservations by following the instructions at [Amazon Elasticsearch Service Reserved Instances](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/aes-ri.html) in the *Amazon Elasticsearch Service Developer Guide*\.<a name="use-rex-elc"></a>

**To use Amazon ElastiCache recommendations**

1. On the **Reserved Cache Nodes** page in the ElastiCache console, choose **Purchase Reserved Cache Node**\. 

1. Purchase your reservations by following the instructions at [Purchasing a Reserved Node](https://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/reserved-nodes-purchasing.html) in the *Amazon ElastiCache User Guide*\.