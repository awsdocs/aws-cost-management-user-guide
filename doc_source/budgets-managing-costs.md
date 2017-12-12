# Managing Your Costs with Budgets<a name="budgets-managing-costs"></a>

Budgets enable you to plan your service usage, service costs, and your RI utilization\. You can also track how close your plan is to your budgeted amount or to the free tier limits\. Budgets provide you with a quick way to see your usage\-to\-date and current estimated charges from AWS and to see how much your predicted usage accrues in charges by the end of the month\. Budgets also compare current estimates and charges to the amount that you indicated you want to use or spend and lets you see how much of your budget has been used\. AWS updates your budget status several times a day\. Budgets track your unblended costs, subscriptions, and refunds\. You can create the following types of budgets:

+ Cost budgets allow you to say how much you want to spend on a service\.

+ Usage budgets allow you to say how many hours you want to use one or more services\.

+ RI utilization budgets allow you to define a utilization threshold and receive alerts when RIs are tracking below that threshold\.

You can create up to 20,000 budgets per AWS master account\. Your first two budgets are free of charge\. Each additional budget costs $0\.02 per day\. You can set up optional notifications that warn you if you exceed, or are forecasted to exceed, your budgeted amount\. You can have notifications sent to an Amazon SNS topic, to an email address, or to both\. For more information, see [Creating an Amazon SNS Topic for Budget Notifications](budgets-sns-policy.md)\.  AWS Free Tier usage alerts via AWS Budgets are provided for you, and do not count toward your budget limits\.

If you use consolidated billing in an organization and you own the master account, you can use IAM policies to control access to budgets by member accounts\. By default, owners of member accounts can create their own budgets but can't create or edit budgets for other users\. You can use IAM to allow users in a member account to create, edit, delete, or read the budget for your master account\. Do this, for example, to allow another account to administer your budget\. For more information, see [Controlling Access](control-access-billing.md)\. 


+ [Creating a Budget](budgets-create.md)
+ [Viewing Your Budgets](budgets-view.md)
+ [Editing a Budget](budgets-edit.md)
+ [Downloading a Budget](budgets-export.md)
+ [Copying a Budget](budgets-copy.md)
+ [Deleting a Budget](budgets-delete.md)
+ [Creating an Amazon SNS Topic for Budget Notifications](budgets-sns-policy.md)