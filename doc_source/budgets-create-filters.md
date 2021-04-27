# Available budget filters<a name="budgets-create-filters"></a>



**Usage Type Group**  
Choose one of the groups provided, such as `S3: Data Transfer - Internet (Out) (GB)`\. A usage type group is a collection of usage types that have the same unit of measure\. If you choose both the **Usage Type Group** and the **Usage Type** filters, Cost Explorer shows you usage types that are automatically constrained to the group unit of measure\. For example, when you choose the group `EC2: Running Hours (Hrs)` and then choose the `EC2-Instances` filter for **Usage Type**, Cost Explorer shows you only the usage types that are measured in hours\.

**Usage Type**  
Choose a filter such as `S3` and then choose a usage type value, such as `DataTransfer-Out-Bytes (GB)`\. You can create a usage budget only for a specific unit of measure\. If you choose **Usage Type** but not **Usage Type Group**, Cost Explorer shows you all the available units of measure for the usage type\.

**Service**  
Choose an AWS service\. You can also use the **Service** dimension to filter costs by specific AWS Marketplace software\. This includes your costs for specific AMIs, web services, and desktop apps\. For more information, see [ What Is AWS Marketplace?](https://docs.aws.amazon.com/marketplace/latest/controlling-access/what-is-marketplace.html)  
You can use this filter only for cost, RI utilization, or RI coverage budgets\. Cost Explorer doesn't show revenue or usage for the AWS Marketplace software seller\.   
The RI utilization and RI coverage reports allow filtering by only one service at a time and only for the following services:  
+ Amazon Elastic Compute Cloud \- Compute
+ Amazon Redshift
+ Amazon Relational Database Service
+ Amazon ElastiCache
+ Amazon Elasticsearch Service


**Linked Account**  
Choose an AWS account that is a member of the account that you're creating the budget for\.  
Do not use this filter within a member account\. If the current account is a member account, filtering by `linked account` is not supported\.

**Tag**  
If you have activated any tags, choose a resource tag\. A tag is a label that you can use to organize your resource costs and track them on a detailed level\. There are AWS generated tags and user\-defined tags\. You must activate tags to use them\. For more information, see [Activating the AWS\-Generated Cost Allocation Tags](activate-built-in-tags.md) and [Activating User\-Defined Cost Allocation Tags](activating-tags.md)\.

**Purchase Option**  
Choose `On Demand Instances`, `Standard Reserved Instances`, or `Savings Plans`\.

**Availability Zone**  
Choose the `Availability Zone` in which the resource that you want to create a budget for is running\.

**API Operation**  
Choose an action, such as `CreateBucket`\.

**Billing Entity**  
Choose the organization that bills you for a service\. For AWS service charges, **AWS** is the billing entity\. For third\-party services that are sold through AWS Marketplace, **AWS Marketplace** is the billing entity\.

**Instance Type**  
Choose the type of instance that you want to track with this budget\. 

**Instance Family**  
 Choose the family of instances to track using this budget\.

**Platform**  
Choose the operating system that your RI runs on\. **Platform** is either **Linux** or **Windows**\.

**Tenancy**  
Choose whether you share an RI with another user or not\. **Tenancy** is either **Dedicated** or **Default**\.

**Savings Plans Type**  
Choose what you want to budget for, between **Compute Savings Plans** and **EC2 Instance Savings Plans**\. The Savings Plans type filter is only available for Savings Plans utilization budgets\.