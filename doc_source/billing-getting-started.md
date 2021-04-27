# Getting started<a name="billing-getting-started"></a>

The following steps discuss a few of the most common tasks that you're likely to perform when using the Billing and Cost Management console\. 

**Topics**
+ [Step 1: Review your usage](#billing-gs-review)
+ [Step 2: Turn on reports](#step-2)
+ [Step 3: Download or print your bill](#billing-gs-download)
+ [Step 4: Set up budgets to monitor your account](#billing-gs-alerts)
+ [Step 5: Get answers to questions about your bill](#billing-gs-answer)
+ [Where do I go from here?](#whereto)

## Step 1: Review your usage<a name="billing-gs-review"></a>

Billing and Cost Management offers you a number of different ways to view and monitor your AWS usage\. Here's how to quickly check to see what you have used so far in the current month\.

**To open the Billing and Cost Management console and review your usage and charges**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\. The console opens to the **Dashboard**, where you can see your current month\-to\-date usage graphs\. 

1. On the navigation pane, choose the applicable option:  
**Cost Explorer**  
 Choose [Cost Explorer](https://console.aws.amazon.com/cost-reports/home?#/custom) to track and analyze your AWS usage\. Cost Explorer is free for all accounts\. For more information about Cost Explorer, see [Analyzing your costs with Cost Explorer](ce-what-is.md)\.   
**Budgets**  
 Choose [Budgets](https://console.aws.amazon.com/billing/home?region=us-east-1#/budgets) to manage budgets for your account\. For more information about budgets, see [Monitoring your usage and costs](monitoring-costs.md)\.   
You can also check the status of your free tier with the provided AWS Free Tier usage alerts using AWS Budgets\. For more information about AWS Free Tier usage alerts, see [AWS Free Tier usage alerts using AWS Budgets](tracking-free-tier-usage.md#free-budget)\.   
**Bills**  
 Choose [Bills](https://console.aws.amazon.com/billing/home?region=us-east-1#/bill) to see details about your current charges\.   
**Orders and Invoices**  
 Choose [Orders and invoices](https://console.aws.amazon.com/billing/home?region=us-east-1#/paymenthistory/history?redirected) to see your past payment transactions\. 

## Step 2: Turn on reports<a name="step-2"></a>

 In addition to the features described in step 1, AWS Billing and Cost Management offers a set of billing reports about your AWS usage\. The reports show you which AWS services you used, the amount of time that you used them, the amount of data that you transferred in and out of storage, the average storage space that you used, and more\. 

To learn more about how to set up your reports, see [Creating Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/creating-cur.html) in the *Cost and Usage Report Guide*\.

## Step 3: Download or print your bill<a name="billing-gs-download"></a>

AWS Billing and Cost Management closes the billing period at midnight on the last day of each month and then calculates your bill\. Most bills are ready for you to download by the seventh accounting day of the month\. 

**To download your bill**

1. Sign into the AWS Management Console and open the Billing and Cost Management at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\. 

1. On the navigation pane, choose **Bills**\.

1. For **Date**, choose the month of the bill you want to work with\.

1. Choose **Download CSV** to download a comma\-separated variable file or choose **Print**\.

## Step 4: Set up budgets to monitor your account<a name="billing-gs-alerts"></a>

If you use the AWS Free Tier, Billing and Cost Management automatically provides AWS Free Tier usage alerts via AWS Budgets to track your free tier usage\. Billing and Cost Management notifies you when you go over the free tier limits or are forecasted to go over the free tier limits\. AWS sends these notifications to the email that you used to create your AWS account\.

In addition to the free tier usage alerts, you can use budgets to notify you when your monthly charges for using an AWS product exceed or are forecast to exceed a threshold that you set\. 

 By default, IAM users don't have access to billing information, and therefore don't have access to budgets\. If you're logged in to AWS as an IAM user, verify that the account owner has granted IAM users access to AWS Budgets\. For more information about IAM restrictions,  <a name="cost-budget-alarm"></a>

**To create a budget**

Use this procedure to create a cost\-based budget\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Budgets**\.

1. At the top of the page, choose **Create budget**\.

1. For **Select budget type**, choose **Cost budget**\.

1. Choose **Set up your budget**\.

1. For **Name**, enter the name of your budget\. Your budget name must be unique within your account and can use A\-Z, a\-z, spaces, and the following characters:

   ```
   _.:/=+-%@
   ```

1. For **Period**, choose how often you want the budget to reset the actual and forecasted spend\. Choose **Monthly** for every month, **Quarterly** for every three months, and **Annually** for every year\.

1. For **Budgeted Amount**, enter the total amount that you want to spend for this budget period\.

1. \(Optional\) For **Budget effective dates**, choose **Recurring Budget** for a budget that resets after the budget period or **Expiring Budget** for a one\-time budget that doesn't reset after the budget period\.

   For **Start Month**, choose the month that you want the budget to start on\.

   For an **Expiring Budget**, for **End Month**, choose the month that you want the budget to end on\.

   All budget times are in UTC\.

1. \(Optional\) Under **Budget parameters \(optional\)**, for **Filtering**, choose one or more of the [available filters](budgets-create-filters.md)\. Your choice of budget type determines the set of filters that is displayed on the console\.

1. \(Optional\) Under **Budget parameters \(optional\)**, for **Advanced options**, choose one or more of the following filters\. If you're signed in from a member account in an organization instead of from a management account, you might not see all of the advanced options\.  
**Refunds**  
Any refunds that you received\.  
**Credits**  
Any AWS credits that are applied to your account\.  
**Upfront reservation fees**  
Any upfront fees that are charged to your account\. When you purchase an All Upfront or Partial Upfront Reserved Instance from AWS, you pay an upfront fee in exchange for a lower rate for using the instance\.   
**Recurring reservation charges**  
Any recurring charges to your account\. When you purchase a Partial Upfront or No Upfront Reserved Instance from AWS, you pay a recurring charge in exchange for a lower rate for using the instance\.   
**Taxes**  
Any taxes that are associated with the charges or fees in your budget\.  
**Support charges**  
Any charges that AWS charges you for a support plan\. When you purchase a support plan from AWS, you pay a monthly charge in exchange for service support\.   
**Other subscription costs**  
  
**Use blended costs**  
The cost of the instance hours that you used\. A blended rate doesn't include either the RI upfront costs or the RI discounted hourly rate\.  
**Use amortized costs**  
The amortized cost of any reservation hours that you used\. For more information about amortized costs, see [Show amortized costs](ce-advanced.md#show-amortized-costs)\.

1. Choose **Configure alerts**\.

1. Under **Configure alerts**, for **Alert 1**, choose **Actual** to create a notification for actual spend and **Forecast** to create a notification for your forecasted spend\.

1. For **Alert threshold**, enter the amount that you want to be notified at\. This can be either an absolute value or a percentage\. For example, for a budget of 200 dollars, if you want to be notified at 160 dollars \(80% of your budget\), enter 160 for an absolute budget or 80 for a percentage budget\.

   Next to the amount, choose **Absolute amount** to be notified when the threshold amount is passed and **% of budgeted amount** to be notified when the threshold percentage of the budget is passed\.

1. \(Optional\) For **Email contacts**, enter the email addresses that you want the notifications to be sent to and choose **Add email contact**\. Separate multiple email addresses with a comma\. A notification can have up to 10 email addresses\.

   To receive a notification, you must specify an email address\. You can also specify an Amazon SNS topic\.

1. \(Optional\) For **SNS topic ARN**, enter the ARN for your Amazon SNS topic and then choose **Verify**\. If you want to use an Amazon SNS topic for your notification but don't have one, see [Create a Topic](https://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html) in the *Amazon Simple Notification Service Developer Guide*\.

   AWS verifies that your budget has permission to send notifications to your Amazon SNS topic by sending a test email to your Amazon SNS topic\. If the Amazon SNS topic ARN is valid but the **Verify** step fails, check the Amazon SNS topic policy to make sure that it allows your budget to publish to that topic\. 

   For a sample policy and instructions on granting your budget permissions, see [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)\. A notification can be subscribed to only one Amazon SNS topic\.

   To receive a notification, you must specify an email address\. You can also specify an Amazon SNS topic\.

1. Choose **Confirm budget**\.

1. Review your budget settings and choose **Create**\.

**Important**  
When you finish creating a budget with Amazon SNS notifications, Amazon SNS sends a confirmation email to the email addresses that you specify\. The subject line is **AWS Notification \- Subscription Confirmation**\. A recipient must choose **Confirm subscription** in the confirmation email to begin receiving notifications\. 

## Step 5: Get answers to questions about your bill<a name="billing-gs-answer"></a>

If you have questions about your bill, see the [AWS Knowledge Center](http://aws.amazon.com/premiumsupport/knowledge-center/)\. If you don't find the answer that you're looking for in the Knowledge Center, you can access account and billing support free of charge\. For more information about AWS Support, see [Getting help with AWS Billing and Cost Management](billing-get-answers.md)\. For information about closing your account, see [Closing an account](close-account.md)\.

## Where do I go from here?<a name="whereto"></a>

 Explore some of the features designed to help you dig a little deeper and streamline your accounting practices\. 
+ [Tracking your AWS Free Tier usage](tracking-free-tier-usage.md)
+ [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)
+ [Analyzing your costs with Cost Explorer](ce-what-is.md)
+ [Managing your costs with AWS Budgets](budgets-managing-costs.md)
+ [Consolidated billing for AWS Organizations](consolidated-billing.md)