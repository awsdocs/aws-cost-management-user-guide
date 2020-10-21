# Managing your costs with AWS Cost Categories<a name="manage-cost-categories"></a>

You can use AWS Cost Categories to map your AWS costs and usage into meaningful categories\. With cost categories, you can organize your costs using a rule\-based engine\. The rules that you configure will organize your costs into categories\. You can then use these categories across products in the AWS Billing and Cost Management console, including Cost Explorer, AWS Budgets, and AWS Cost and Usage Reports \(AWS CUR\)\.

You can create groupings of costs using cost categories\. For example, your business is organized by teams, and each team has multiple accounts within\. To build this structure in cost categories, first create a cost category named *Team*\. Then, you can map costs to a cost category value named `Team 123`\.

Companies commonly have multiple perspectives on their business, such as projects, cost centers, and applications, and you can create cost categories to match these perspectives\. Cost category values are groups within cost categories, similar to `Team 123` or `Team 456` from the previous example\. By creating cost categories, you can view your business in multiple, corresponding perspectives\.

You can start using cost categories by creating a unique category name\. Then, map costs to cost category values within the cost categories\. In each cost category value, map the type of costs that belong to that value\. For example, if your `Team 123` consists of multiple accounts, you can write that expression by choosing the accounts dimension \(`is` option\) and selecting the applicable accounts\. After creating the cost category value, continue to create other teams by adding values\.

After your cost categories are created, they appear in Cost Explorer, AWS Budgets, and AWS CUR\. In Cost Explorer and AWS Budgets, a cost category appears as an additional billing dimension\. You can use this to filter for the specific cost category value, or group by the cost category\. In AWS CUR, the cost category appears as a new column with the cost category value in each row\.

**Note**  
Cost categories are effective at the start of the current month\. If you create or update your cost category in the middle of the month, it retroactively takes effect on cost and usage from the beginning of the month\.

This is an administrative feature, and it can only be customized by the management account or regular accounts in AWS Organizations\.

**Topics**
+ [Supported dimensions](#cost-categories-dimensions)
+ [Supported operations](#cost-categories-ops)
+ [Status](#cost-categories-stat)
+ [Limits](#cost-categories-limits)
+ [Term comparisons](#cost-categories-terms)
+ [Creating cost categories](create-cost-categories.md)
+ [Editing cost categories](edit-cost-categories.md)
+ [Deleting cost categories](delete-cost-categories.md)

## Supported dimensions<a name="cost-categories-dimensions"></a>

You can select from a list of billing dimensions to create your cost category rules\. These billing dimensions are used to group your data\. For example, if you wanted to group a set of accounts to form a team, you would first choose the account billing dimension, and then choose the list of accounts that you want to include in the team\.

The following billing dimensions are supported\.

**Account**  
This can be the AWS account name or the account ID, depending on the operation\. If you're using an exact match operation \(`is` or `is not`\), account refers to the account ID\. If you're using an approximate match operation \(`starts with`, `ends with`, or `contains`\), account refers to account name\.

**Service**  
AWS services, such as Amazon EC2, Amazon RDS, and Amazon S3\.

**Charge type**  
The type of charges based on line items details\. Also referred to as the `RECORD_TYPE` in the Cost Explorer API\. For more information, see [Term comparisons](#cost-categories-terms)\.

**Tag key**  
The cost allocation tag keys that are specified on the resource\. For more information, see [Using Cost Allocation Tags](cost-alloc-tags.md)\.

**Cost category**  
A dimension from another cost category\. Using cost categories as a dimension helps you organize the levels of categories\.

## Supported operations<a name="cost-categories-ops"></a>

You can use these operations to create the filter expression when you're creating a cost category rule\.

The following operations are supported\.

**Is**  
The exact match operation used to filter for the exact value specified\.

**Is not**  
The exact match operation used to filter for the exact value that is not specified\.

**Contains**  
The approximate match used to filter for a text string containing this value\. This value is case sensitive\.

**Starts with**  
The approximate match used to filter for a text string that starts with this value\. This value is case sensitive\.

**Ends with**  
The approximate match used to filter for a text string that ends with this value\. This value is case sensitive\.

## Status<a name="cost-categories-stat"></a>

You can use the console to confirm the status of whether your cost categories completed the processing of the cost and usage information\. After you create or edit a cost category, it takes approximately 8 hours before it has categorized your cost and usage information in the AWS Cost and Usage Report or Cost Explorer\.

There are two status states\.

**Applied**  
Cost categories completed processing, and the information in AWS Cost and Usage Report and Cost Explorer is up to date with the new rules\.

**Processing**  
The cost categories are still in progress\.

## Limits<a name="cost-categories-limits"></a>

For more information about cost categories quotas, see [Quotas and restrictions](billing-limits.md)\.

## Term comparisons<a name="cost-categories-terms"></a>

`CHARGE_TYPE` is a dimension supported for cost category expressions, also called `RECORD_TYPE` in the Cost Explorer API\. This dimension uses different terms, depending on whether you're using the console or the API/JSON editor\. The following table compares the terminology used for both scenarios\.


**Term comparison**  

| Value in API or JSON editor | Name used in the console | 
| --- | --- | 
| Usage | Usage | 
| SavingsPlanCoveredUsage | Savings Plan Covered Usage | 
| DiscountedUsage | Reservation applied usage | 
| RIFee | Recurring reservation fee | 
| SavingsPlanRecurringFee | Savings Plan Recurring Fee | 
| Tax | Tax | 
| Credit | Credit | 
| SavingsPlanNegation | Savings Plan Negation | 