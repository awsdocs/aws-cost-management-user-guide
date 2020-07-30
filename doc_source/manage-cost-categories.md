# Managing your costs with Cost Categories<a name="manage-cost-categories"></a>

You can use Cost Categories to map your AWS costs and usage into meaningful categories\. With Cost Categories, you can organize your costs using a rule\-based engine\. The rules that you configure will organize your costs into categories\. You can then use these categories across products in the AWS Billing and Cost Management console, such as Cost Explorer, AWS Budgets, and AWS Cost and Usage Reports \(AWS CUR\)\.

You can create groupings of costs using Cost Categories\. For example, your business is organized by teams, and each team has multiple accounts within\. To build this structure in Cost Categories, first create a Cost Category named *Team*\. Then, you can map costs to a Cost Categories value named `Team 123`\.

Companies commonly have multiple perspectives on their business, such as projects, cost centers, and applications, and you can create Cost Categories to match these perspectives\. Cost Category values are groups within Cost Categories, similar to `Team 123` or `Team 456` from the previous example\. By creating Cost Categories, you can view your business in multiple, corresponding perspectives\.

You can start using Cost Categories by creating a unique category name\. Then, you can map costs to Cost Category values within the Cost Categories\. In each Cost Category value, map the type of costs that belong to that value\. For example, if your `Team 123` consists of multiple accounts, you can write that expression by choosing the accounts dimension \(`is` option\) and selecting the applicable accounts\. After creating the Cost Category value, you can continue to create other teams by adding values\.

After they are created, your Cost Categories appear in Cost Explorer, AWS Budgets, and AWS CUR\. In Cost Explorer and AWS Budgets, a Cost Category appears as an additional billing dimension\. You can use this to filter for the specific Cost Category value, or group by the Cost Category\. In AWS CUR, the Cost Category appears as a new column with the Cost Category value in each row\.

**Note**  
Cost Categories are effective at the start of the current month\. If you create or update your Cost Category in the middle of the month, it retroactively takes effect on cost and usage from the beginning of the month\.

This is an administrative feature, and can only be customized by Payer accounts or Regular accounts in AWS Organizations\.

## Limits<a name="cost-categories-limits"></a>

For more information about Cost Categories quotas, see [Quotas and restrictions](billing-limits.md)\.

## Term comparisons<a name="cost-categories-terms"></a>

`CHARGE_TYPE` is a dimension supported for Cost Category expressions, also called `RECORD_TYPE` in the Cost Explorer API\. This dimension uses different terms, depending on whether you're using the console or the API/JSON editor\. The following table compares the terminology used for both scenarios\.


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

**Topics**
+ [Limits](#cost-categories-limits)
+ [Term comparisons](#cost-categories-terms)
+ [Creating Cost Categories](create-cost-categories.md)
+ [Editing Cost Categories](edit-cost-categories.md)
+ [Deleting Cost Categories](delete-cost-categories.md)