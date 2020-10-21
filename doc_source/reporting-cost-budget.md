# Reporting your budget metrics with budget reports<a name="reporting-cost-budget"></a>

AWS Budgets enables you to configure a report to monitor the performance of your existing budgets on a daily, weekly, or monthly cadence and deliver that report to up to 50 email addresses\.

You can create up to 50 reports per standalone account or AWS Organizations management account\. Each budget report costs $\.01 USD per report delivered, regardless of the number of recipients receiving the report\. For example, a daily budget report costs $\.01 per day, a weekly budget report costs $\.01 per week, and a monthly budget report costs $\.01 per month\.

If you use consolidated billing in an organization and you own the management account, you can use IAM policies to control access to budgets by member accounts\. By default, owners of member accounts can create their own budgets but can't create or edit budgets for other users\. You can use IAM to allow users in a member account to create, edit, delete, or read the budget for your management account\. Do this, for example, to allow another account to administer your budget\. For more information, see [Overview of managing access permissions](control-access-billing.md)\. For more information about AWS Organizations, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\.

**Topics**
+ [Creating an AWS Budgets report](create-budget-report.md)
+ [Editing an AWS Budgets report](edit-budget-report.md)
+ [Copying an AWS Budgets report](copy-budget-report.md)
+ [Deleting an AWS Budgets report](delete-budget-report.md)