# Filtering the Data That You Want to View<a name="selectdim"></a>

With Cost Explorer, you can filter how you view your AWS costs by any of the following values:

+ **Service**

+ **Linked Account**

+ **Region**

+ **Availability Zone \(AZ\)**

+ **Instance Type**

+ **Usage Type**

+ **Usage Type Group**

+ **Tag**

+ **Include All**

+ **API operation**

+ **Platform**

+ **Purchase Option**

+ **Tenancy**

+ **Billing Entity**

You can apply multiple filters to look at intersecting data sets\. For example, you can use the **Linked Account** and **Services** filters to identify the linked account that spent the most money on Amazon EC2\. 

**To filter your data**

1. Open Cost Explorer\.

1. For **Filters**, choose a value\. After you make a selection, a new control appears with additional options\.

1. In the new control, select the items from each list that you want to display in the chart, or begin typing in the search box to have Cost Explorer auto\-complete your selection\. After you choose your filters, choose **Apply**\.

You can continue refining your cost analysis by using multiple filters, by grouping your data by filter type, and by using the options in the **Advanced Options** tab\. 

## Combining Filters to Show Data in Common<a name="filtersandoperators"></a>

Cost Explorer displays a chart that represents the data in common to the filters you've selected, which means that you can use filters together to analyze subsets of cost data\. For example, if you set the **Service** filter to show costs related to Amazon EC2 and Amazon RDS services, and then select **Reserved** using the **Purchase Option** filter, the cost chart shows how much money **Reserved** instances on Amazon EC2 and Amazon RDS cost for each of the three months specified\.

**Note**  
You can filter Reserved Instance Utilization reports by only one service at a time\.

## Filters and Logical Operations \(AND/OR\)<a name="logicops"></a>

When you select multiple filters, and values for each filter, Cost Explorer applies rules that emulate the logical AND and OR operators to your selections\. Within each filter, Cost Explorer emulates the logical OR filter to your selection of filter types\. In other words, the chart it displays adds the aggregate costs for each item together\. Using the previous example, you see bars for both of the selected services, Amazon EC2 and Amazon RDS\. 

When you select multiple filters, Cost Explorer applies the logical AND operator to your selections\. In other words, if you use the **Services** filter and specify Amazon EC2 and Amazon RDS costs for inclusion, and then also apply the **Purchase Options** filter to select a single type of purchase option, you see *only* the **Non\-Reserved** charges incurred by Amazon EC2 and Amazon RDS\. 

## Filter and Group Options<a name="filtergrouptypes"></a>

In Cost Explorer, you can filter by the following groups:

+ **API Operation**

  Requests made to and tasks performed by a service, such as write and get requests to Amazon S3\.

+ **Availability Zone**

  Distinct locations within a region that are insulated from failures in other Availability Zones\. They provide inexpensive, low\-latency network connectivity to other Availability Zones in the same region\. 

+ **Billing Entity**

  The organization that bills the customer for a service\. For AWS service charges, AWS is the billing entity\. For third party services sold through AWS Marketplace, AWS Marketplace is the billing entity\. 

+ **Instance Type**

  Type of RI that you specified when you launched an Amazon EC2 host, Amazon RDS instance class, Amazon Redshift node, or Amazon ElastiCache node\. The instance type determines the hardware of the computer used to host your instance\.

+ **Linked Account**

  Member accounts in an organization\. For more information, see [Consolidated Billing for Organizations](consolidated-billing.md)\.

+ **Platform**

  The operating system that your RI runs on\. Platform is either **Linux** or **Windows**\.

+ **Purchase Option**

   The method you choose to pay for your Amazon EC2 instances, including Reserved Instances, Spot Instances, Scheduled Reserved Instances, and On\-Demand Instances\. 

+ **Region**

  Geographic areas where AWS hosts your resources\.

+ **Service**

  AWS products\. To learn what's available, see [AWS Products and Services](https://aws.amazon.com/products/)\. You can use this dimension to filter costs by specific AWS Marketplace software, including your costs for AMIs, web services, and desktop apps\. See the [ What is AWS Marketplace? ](http://docs.aws.amazon.com/marketplace/latest/controlling-access/what-is-marketplace.html) guide for more information\. 
**Note**  
The RI Utilization reports allow filtering by only one service at a time, and only for the following services:  
**Amazon EC2**, **Amazon Redshift**, **Amazon RDS**, **ElastiCache**

+ **Tag**

  Label that you can use to track costs associated with specific areas/entities within your business\.

+ **Tenancy**

  Specifies whether you share an Amazon EC2 RI with another user or not\. Tenancy is either **Dedicated** or **Default**\. 

+ **Usage Type**

  Usage types are the units that each service uses to measure the usage of a specific type of resource\. For example, the `BoxUsage:t2.micro(Hrs)` usage type filters by the running hours of Amazon EC2 `t2.micro` instances\.

+ **Usage Type Group**

  Usage type groups are filters that collect a specific category of usage type filters into one filter\. For example, `BoxUsage:c1.medium(Hrs)`, `BoxUsage:m3.xlarge(Hrs)`, and `BoxUsage:t1.micro(Hrs)` are all filters for Amazon EC2 instance running hours, so they are collected into the `EC2: Running Hours` filter\.

  Usage type groups are available for Amazon EC2, DynamoDB, and Amazon S3\. The specific groups available to your account depend on what services you've used\. The list of groups that might be available includes but is not limited to the following:

  + **DDB: Data Transfer \- Internet \(In\)**

    Filters by costs associated with how many GB are transferred to your DynamoDB databases\.

  + **DDB: Data Transfer \- Internet \(Out\)**

    Filters by costs associated with how many GB are transferred from your DynamoDB databases\.

  + **DDB: Indexed Data Storage**

    Filters by costs associated with how many GB that you have stored in DynamoDB\.

  + **DDB: Provisioned Throughput Capacity \- Read**

    Filters by costs associated with how many units of read capacity that your DynamoDB databases used\.

  + **DDB: Provisioned Throughput Capacity \- Write**

    Filters by costs associated with how many units of write capacity that your DynamoDB databases used\.

  + **EC2: CloudWatch \- Alarms**

    Filters by costs associated with how many CloudWatch alarms that you have\.

  + **EC2: CloudWatch \- Metrics**

    Filters by costs associated with how many CloudWatch metrics that you have\.

  + **EC2: CloudWatch \- Requests**

    Filters by costs associated with how many CloudWatch requests that you make\.

  + **EC2: Data Transfer \- CloudFront \(Out\)**

    Filters by costs associated with how many GB are transferred from your Amazon EC2 instances to a CloudFront distribution\.

  + **EC2: Data Transfer \- CloudFront \(In\)**

    Filters by costs associated with how many GB are transferred to your Amazon EC2 instances from a CloudFront distribution\.

  + **EC2: Data Transfer \- Inter AZ**

    Filters by costs associated with how many GB are transferred into, out of, or between your Amazon EC2 instances in different Availability Zones\.

  + **EC2: Data Transfer \- Internet \(In\)**

    Filters by costs associated with how many GB are transferred to your Amazon EC2 instances from outside of the AWS network\.

  + **EC2: Data Transfer \- Internet \(Out\)**

    Filters by costs associated with how many GB are transferred from an Amazon EC2 instance to a host outside of the AWS network\.

  + **EC2: Data Transfer \- Region to Region \(In\)**

    Filters by costs associated with how many GB are transferred to your Amazon EC2 instances from a different AWS Region\.

  + **EC2: Data Transfer \- Region to Region \(Out\)**

    Filters by costs associated with how many GB are transferred from your Amazon EC2 instances to a different AWS Region\.

  + **EC2: EBS \- I/O Requests**

    Filters by costs associated with how many I/O requests that you make to your Amazon EBS volumes\.

  + **EC2: EBS \- Magnetic**

    Filters by costs associated with how many GB that you have stored on Amazon EBS Magnetic volumes\.

  + **EC2: EBS \- Provisioned IOPS**

    Filters by costs associated with how many IOPS\-months that you have provisioned for Amazon EBS\.

  + **EC2: EBS \- SSD\(gp2\)**

    Filters by costs associated with how many GB per month of General Purpose storage that your Amazon EBS volumes use\.

  + **EC2: EBS \- SSD\(io1\)**

    Filters by costs associated with how many GB per month of Provisioned IOPS SSD storage that your Amazon EBS volumes use\.

  + **EC2: EBS \- Snapshots**

    Filters by costs associated with how many GB per month that your Amazon EBS snapshots store\.

  + **EC2: EBS \- Optimized**

    Filters by costs associated with how many MB per instance hour that your Amazon EBS\-optimized instances use\.

  + **EC2: ELB \- Running Hours**

    Filters by costs associated with how many hours that your Elastic Load Balancing load balancers ran\.

  + **EC2: Elastic IP \- Additional Address**

    Filters by costs associated with how many Elastic IP addresses that you have attached to running Amazon EC2 instances\.

  + **EC2: Elastic IP \- Idle Address**

    Filters by costs associated with Elastic IP addresses that you have that are not attached to running Amazon EC2 instances\.

  + **EC2: NAT Gateway \- Data Processed**

    Filters by costs associated with how many GB that your network address translation gateways \(NAT gateways\) processed\.

  + **EC2: NAT Gateway \- Running Hours**

    Filters by costs associated with how many hours that your NAT gateways ran\.

  + **EC2: Running Hours**

    Filters by costs associated with how many hours that your Amazon EC2 instances ran\.

  + **ElastiCache: Running Hours**

    Filters by costs associated with how many hours that your Amazon ElastiCache nodes ran\.

  + **ElastiCache: Storage**

    Filters by costs associated with how many GB that you have stored in Amazon ElastiCache\.

  + **RDS: Running Hours**

    Filters by costs associated with how many hours that your Amazon RDS databases ran\.

  + **RDS: Data Transfer – CloudFront – In**

    Filters by costs associated with how many GB are transferred into Amazon RDS from a CloudFront distribution\.

  + **RDS: Data Transfer – CloudFront – Out**

    Filters by costs associated with how many GB are transferred from a CloudFront distribution to Amazon RDS data transfers\.

  + **RDS: Data Transfer – Direct Connect Locations – In**

    Filters by costs associated with how many GB are transferred into Amazon RDS through a Direct Connect network connection\.

  + **RDS: Data Transfer – Direct Connect Locations – Out**

    Filters by costs associated with how many GB are transferred from Amazon RDS through a Direct Connect network connection\.

  + **RDS: Data Transfer – InterAZ**

    Filters by costs associated with how many GB are transferred into, out of, or between Amazon RDS buckets in different Availability Zones\.

  + **RDS: Data Transfer – Internet – In**

    Filters by costs associated with how many GB are transferred to your Amazon RDS databases\.

  + **RDS: Data Transfer – Internet – Out**

    Filters by costs associated with how many GB are transferred from your Amazon RDS databases\.

  + **RDS: Data Transfer – Region to Region – In**

    Filters by costs associated with how many GB are transferred to your Amazon RDS instances from a different AWS Region\.

  + **RDS: Data Transfer – Region to Region – Out**

    Filters by costs associated with how many GB are transferred from your Amazon RDS instances to a different AWS Region\.

  + **RDS: I/O Requests**

    Filters by costs associated with how many I/O requests that you make to your Amazon RDS instance\.

  + **RDS: Provisioned IOPS**

    Filters by costs associated with how many IOPS\-months that you have provisioned for Amazon RDS\.

  + **RDS: Storage**

    Filters by costs associated with how many GB that you have stored in Amazon RDS\.

  + **Redshift: DataScanned**

    Filters by costs associated with how many GB that your Amazon Redshift nodes scanned\.

  + **Redshift: Running Hours**

    Filters by costs associated with how many hours that your Amazon Redshift nodes ran\.

  + **S3: API Requests \- Standard**

    Filters by costs associated with `GET` and all other standard storage Amazon S3 requests\.

  + **S3: Data Transfer \- CloudFront \(In\)**

    Filters by costs associated with how many GB are transferred into Amazon S3 from a CloudFront distribution\.

  + **S3: Data Transfer \- CloudFront \(Out\)**

    Filters by costs associated with how many GB are transferred from a CloudFront distribution to Amazon S3 data transfers, such as how much data was uploaded from your Amazon S3 bucket to your CloudFront distribution\.

  + **S3: Data Transfer \- Inter AZ**

    Filters by costs associated with how many GB are transferred into, out of, or between Amazon S3 buckets in different Availability Zones\.

  + **S3: Data Transfer \- Internet \(In\)**

    Filters by costs associated with how many GB are transferred to an Amazon S3 bucket from outside of the AWS network\.

  + **S3: Data Transfer \- Internet \(Out\)**

    Filters by costs associated with how many GB are transferred from an Amazon S3 bucket to a host outside of the AWS network\.

  + **S3: Data Transfer \- Region to Region \(In\)**

    Filters by costs associated with how many GB are transferred to Amazon S3 from a different AWS Region\.

  + **S3: Data Transfer \- Region to Region \(Out\)**

    Filters by costs associated with how many GB are transferred from Amazon S3 to a different AWS Region\.

  + **S3: Storage \- Standard**

    Filters by costs associated with how many GB that you have stored in Amazon S3\.