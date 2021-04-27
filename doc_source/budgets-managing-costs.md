# Managing your costs with AWS Budgets<a name="budgets-managing-costs"></a>

You can use AWS Budgets to track and take action on your AWS cost and usage\. You can use AWS Budgets to monitor your aggregate utilization and coverage metrics for your Reserved Instances \(RIs\) or Savings Plans\. If you're new to AWS Budgets, see [Best practices for AWS Budgets](budgets-best-practices.md)\.

You can use AWS Budgets to enable simple\-to\-complex cost and usage tracking\. Some examples include:
+ Setting a monthly cost budget with a fixed target amount to track all costs associated with your account\. You can choose to be alerted for both actual \(after accruing\) and forecasted \(before accruing\) spends\.
+ Setting a monthly cost budget with a variable target amount, with each subsequent month growing the budget target by 5 percent each month\. Then, you can configure your notifications for 80 percent of your budgeted amount and apply an action\. For example, you could automatically apply a custom IAM policy that denies you the ability to provision additional resources within an account\.
+ Setting a monthly usage budget with a fixed usage amount and forecasted notifications to help ensure that you are staying within the service limits for a specific service\. You can also be sure you are staying under a specific AWS Free Tier offering\.
+ Setting a daily utilization or coverage budget to track your RI or Savings Plans\. You can choose to be notified through email and Amazon SNS topics when your utilization drops below 80 percent for a given day\.

AWS Budgets information is updated up to three times a day\. Updates typically occur 8–12 hours after the previous update\. Budgets can track your unblended costs, amortized, and blended costs\. Budgets can include or exclude charges such as descriptions, refunds, support fees, and taxes\. 

You can create the following types of budgets:
+ **Cost budgets** – Plan how much you want to spend on a service\.
+ **Usage budgets** – Plan how much you want to use one or more services\.
+ **RI utilization budgets** – Define a utilization threshold and receive alerts when your RI usage falls below that threshold\. This lets you see if your RIs are unused or under\-utilized\.
+ **RI coverage budgets** – Define a coverage threshold and receive alerts when the number of your instance hours that are covered by RIs fall below that threshold\. This lets you see how much of your instance usage is covered by a reservation\.
+ **Savings Plans utilization budgets** – Define a utilization threshold and receive alerts when the usage of your Savings Plans falls below that threshold\. This lets you see if your Savings Plans are unused or under\-utilized\.
+ **Savings Plans coverage budgets** – Define a coverage threshold and receive alerts when your Savings Plans eligible usage that is covered by Savings Plans fall below that threshold\. This lets you see how much of your instance usage is covered by Savings Plans\.

You can set up optional notifications that warn you if you exceed, or are forecasted to exceed, your budgeted amount for cost or usage budgets or fall below your target utilization and coverage for RI or Savings Plans budgets\. You can have notifications sent to an Amazon SNS topic, to an email address, or to both\. For more information, see [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)\.

If you use consolidated billing in an organization and you own the management account, you can use IAM policies to control access to budgets by member accounts\. By default, owners of member accounts can create their own budgets but can't create or edit budgets for other users\. You can create IAM users with permissions that allow them to create, edit, delete, or read budgets in a specific account\. However, we do not support cross\-account usage\. 

A budget is only visible to users with access to the account that created the budget, and with access to the budget itself\. For example, a management account can create a budget that tracks a specific member account's cost, but the member account can only view the same budget if they receive access to the management account\. For more information, see [Overview of managing access permissions](control-access-billing.md)\. For more information about AWS Organizations, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\.

**Note**  
There can be a delay between when you incur a charge and when you receive a notification from AWS Budgets for the charge\. This is due to a delay between when an AWS resource is used and when that resource usage is billed\. You might incur additional costs or usage that exceed your budget notification threshold before AWS Budgets can notify you\.

**Topics**
+ [Best practices for AWS Budgets](budgets-best-practices.md)
+ [Creating a budget](budgets-create.md)
+ [Viewing your budgets](budgets-view.md)
+ [Editing a budget](budgets-edit.md)
+ [Downloading a budget](budgets-export.md)
+ [Copying a budget](budgets-copy.md)
+ [Deleting a budget](budgets-delete.md)
+ [Configuring AWS Budgets controls](budgets-controls.md)
+ [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)
+ [Receiving budget alerts in Amazon Chime and Slack](sns-alert-chime.md)