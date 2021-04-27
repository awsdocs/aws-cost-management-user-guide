# Managing your costs with AWS Cost Categories<a name="manage-cost-categories"></a>

 You can use AWS Cost Categories to map your AWS costs and usage into meaningful categories\. With cost categories, you can organize your costs using a rule\-based engine\. The rules that you configure will organize your costs into categories\. You can then use these categories across products in the AWS Billing and Cost Management console, including Cost Explorer, AWS Budgets, AWS Cost and Usage Reports \(AWS CUR\), and Cost Anomaly Detection\.

You can create groupings of costs using cost categories\. For example, your business is organized by teams, and each team has multiple accounts within\. To build this structure in cost categories, first create a cost category named *Team*\. Then, you can map costs to a cost category value named `Team 1`\.

Companies commonly have multiple perspectives on their business, such as projects, cost centers, and applications, and you can create cost categories to match these perspectives\. Cost category values are groups within cost categories, similar to `Team 1` or `Team 2` from the previous example\. By creating cost categories, you can view your business in multiple, corresponding perspectives\. Furthermore, you can create multilevel hierarchical relationships among your cost categories to replicate your organizational structure\. For example, you can create a cost category named `Business Unit` which includes groupings of multiple teams\. You can then define a cost category value named `BU1` with `Team 1` and `Team 2` selected from your `Teams` cost category and a cost category value `BU2` with `Team 3` and `Team 4` selected from the `Teams` cost category\. 

You can start using cost categories by creating a unique category name\. Then, map costs to cost category values within the cost categories\. In each cost category value, map the type of costs that belong to that value\. For example, if your `Team 1` consists of multiple accounts, you can write that expression by choosing the accounts dimension \(`is` option\) and selecting the applicable accounts\. After creating the cost category value, continue to create other teams by adding values\.

**Note**  
To create hierarchical relationships among your cost categories, you select the cost category dimension from the parent cost category\. This was `Business Unit` in the previous example\. The child cost category would be the cost category name \(`Teams` in the previous example\)\. You can then select values belonging to the child cost category, such as `Team 1` and `Team 2`, into the parent cost category value \(`BU 1` in the example\)\.

 After you create the cost categories, they appear in Cost Explorer, AWS Budgets, AWS CUR and Cost Anomaly Detection\. In Cost Explorer and AWS Budgets, a cost category appears as an additional billing dimension\. You can use this to filter for the specific cost category value, or group by the cost category\. In AWS CUR, the cost category appears as a new column with the cost category value in each row\. In Cost Anomaly Detection, you can use cost category as a monitor type to monitor your total costs across specified cost category values\.

**Note**  
Cost categories are effective at the start of the current month\. If you create or update your cost category in the middle of the month, it retroactively takes effect on cost and usage from the beginning of the month\.

This is an administrative feature, and it can only be customized by the management account or regular accounts in AWS Organizations\.

**Topics**
+ [Supported dimensions](#cost-categories-dimensions)
+ [Supported operations](#cost-categories-ops)
+ [Supported rule types](#cost-categories-rule-types)
+ [Default value](#cost-categories-default-value)
+ [Status](#cost-categories-stat)
+ [Limits](#cost-categories-limits)
+ [Term comparisons](#cost-categories-terms)
+ [Creating cost categories](create-cost-categories.md)
+ [Viewing cost categories](view-cost-categories.md)
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

## Supported rule types<a name="cost-categories-rule-types"></a>

Use rule type to define which cost category values to use to categorize your costs\.

The following rule types are supported\.

**Regular Rule**  
This rule type adds statically defined cost category values that categorize costs based on the defined dimension rules\.

**Inherited Value**  
This rule type adds the flexibility of defining a rule that dynamically inherits the cost category value from the dimension value defined\. For example, if you wanted to dynamically group costs based on the value of a specific tag key, you would first choose the inherited value rule type, then choose the `Tag` dimension and specify the tag key to use\. For example, you could use a tag key, `teams`, to tag your resources with values as `alpha`, `beta`, and `gamma`\. Then, with an inherited value rule, you could select `Tag` as the dimension and use `teams` as the tag key\. This would generate dynamic cost category values `alpha`, `beta`, and `gamma`\. 

## Default value<a name="cost-categories-default-value"></a>

Optionally, if no rules are matched for the cost category, you can define this value to be used instead\.

## Status<a name="cost-categories-stat"></a>

You can use the console to confirm the status of whether your cost categories completed the processing of the cost and usage information\. After you create or edit a cost category, it can take up to 24 hours before it has categorized your cost and usage information in the AWS Cost and Usage Report, Cost Explorer, and other cost management products\.

There are two status states\.

**Applied**  
Cost categories completed processing, and the information in AWS Cost and Usage Report, Cost Explorer, and other cost management products is up to date with the new rules\.

**Processing**  
The cost category updates are still in progress\.

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