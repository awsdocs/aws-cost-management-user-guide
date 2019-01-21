# Managing Your Costs with Budgets<a name="budgets-managing-costs"></a>

AWS Budgets enable you to plan your service usage, service costs, and instance reservations\. Budgets provide you with a way to see the following information:
+ How close your plan is to your budgeted amount or to the free tier limits
+ Your usage to date, including how much you have used of your Reserved Instances \(RIs\)
+ Your current estimated charges from AWS and how much your predicted usage will incur in charges by the end of the month
+ How much of your budget has been used

AWS Budgets information is updated up to three times a day\. Budgets track your unblended costs, subscriptions, refunds, and RIs\. You can create the following types of budgets:
+ **Cost budgets** – Plan how much you want to spend on a service\.
+ **Usage budgets** – Plan how much you want to use one or more services\.
+ **RI utilization budgets** – Define a utilization threshold and receive alerts when your RI usage falls below that threshold\. This lets you see if your RIs are unused or under\-utilized\.
+ **RI coverage budgets** – Define a coverage threshold and receive alerts when the number of your instance hours that are covered by RIs fall below that threshold\. This lets you see how much of your instance usage is covered by a reservation\.

You can create up to 20,000 budgets per standalone account or AWS Organizations master account\. Your first two budgets are free of charge\. Each additional budget costs $0\.02 per day\. You can set up optional notifications that warn you if you exceed, or are forecasted to exceed, your budgeted amount for cost or usage budgets or fall below your budgeted amount for RI budgets\. You can have notifications sent to an Amazon SNS topic, to an email address, or to both\. For more information, see [Creating an Amazon SNS Topic for Budget Notifications](budgets-sns-policy.md)\. AWS Free Tier usage alerts through AWS Budgets are provided for you and don't count toward your budget limits\.

If you use consolidated billing in an organization and you own the master account, you can use IAM policies to control access to budgets by member accounts\. By default, owners of member accounts can create their own budgets but can't create or edit budgets for other users\. You can use IAM to allow users in a member account to create, edit, delete, or read the budget for your master account\. Do this, for example, to allow another account to administer your budget\. For more information, see [Controlling Access](control-access-billing.md)\. For more information about AWS Organizations, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\.

**Note**  
There can be a delay between when you incur a charge and when you receive a notification from AWS Budgets for the charge\. This is due to a delay between when an AWS resource is used and when that resource usage is billed\. You might incur additional costs or usage that exceed your budget notification threshold before AWS Budgets can notify you\.

**Topics**
+ [Creating a Budget](budgets-create.md)
+ [Viewing Your Budgets](budgets-view.md)
+ [Editing a Budget](budgets-edit.md)
+ [Downloading a Budget](budgets-export.md)
+ [Copying a Budget](budgets-copy.md)
+ [Deleting a Budget](budgets-delete.md)
+ [Creating an Amazon SNS Topic for Budget Notifications](budgets-sns-policy.md)