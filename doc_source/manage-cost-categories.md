# Managing Your Costs with Cost Categories<a name="manage-cost-categories"></a>


|  | 
| --- |
| Cost Category is in preview release for AWS Billing and Cost Management and is subject to change\. Your use of Cost Categories is subject to the Beta Service Participation terms of the [AWS Service Terms](https://aws.amazon.com/service-terms/) \(Section 1\.10\)\. | 

Cost Categories enables you to map your cost and usage into meaningful categories\. You can use Cost Categories to organize your costs using a rule\-based engine\. The rules you configure will organize your costs into categories\. You can use these categories across products in the Billing and Cost Management console, such as Cost Explorer and AWS Budgets\.

You can create groupings of costs using Cost Categories\. For example, your business is organized by teams and each team has multiple accounts within\. To build this structure in Cost Categories, first create a Cost Category called "Team"\. Then, use a rule\-based engine to add accounts to each team\.

Companies commonly have multiple perspectives on their business, such as projects, cost centers, and applications\. These views are uniquely independent, and organized in various ways\. By creating Cost Categories, you have the ability to view your business in multiple, corresponding perspectives\. You can also use Cost Allocation Tags to define your rules for further granularity when organizing your costs\.

You can start using Cost Categories by creating a unique category name\. To configure rules, you'll first enter a value name, then select a dimension you want to use to map the value against\. You can then select the dimension’s attributes\. Category names must be unique, but rule values do not\. The system will evaluate each usage record and add the cost category value if the criteria match\.

**Note**  
Cost Categories are effective at the start of the current month\. If you create or update your Cost Category in the middle of the month, it will retroactively take effect on cost and usage from the beginning of the month\.

This is an administrative feature, and can only be customized by Payer accounts in AWS Organizations or Regular accounts\.

## Limits<a name="cost-categories-limits"></a>

For more information on Cost Categories limits, see [Cost Categories](billing-limits.md#limits-categories) in the AWS Billing and Cost Management User Guide\.

**Topics**
+ [Limits](#cost-categories-limits)
+ [Creating Cost Categories](create-cost-categories.md)
+ [Editing Cost Categories](edit-cost-categories.md)
+ [Deleting Cost Categories](delete-cost-categories.md)