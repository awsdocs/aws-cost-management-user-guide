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

If you use the AWS Free Tier, Billing and Cost Management automatically provides AWS Free Tier usage alerts through AWS Budgets\. With free tier usage alerts, AWS Budgets notifies you if you exceed any one of the free tier quotas\. It also notifies you if you're forecasted to exceed any of the free tier quotas\. AWS Budgets sends these notiﬁcations to the email address that you used to create your account\.

In addition to the free tier usage alerts, you can use AWS Budgets to notify you if your cost or usage exceeds or is forecasted to exceed a threshold that you set\. For more information, see [Creating a budget](budgets-create.md)

By default, IAM users can't access billing information, and therefore don't have access to budgets\. If you're logged in to AWS as an IAM user, verify that the account owner granted IAM users access to AWS Budgets\. For more information about IAM restrictions, see [AWS Identity and Access Management for AWS Billing and Cost Management](security-iam.md)\.

## Step 5: Get answers to questions about your bill<a name="billing-gs-answer"></a>

If you have questions about your bill, see the [AWS Knowledge Center](http://aws.amazon.com/premiumsupport/knowledge-center/)\. If you don't find the answer that you're looking for in the Knowledge Center, you can access account and billing support free of charge\. For more information about AWS Support, see [Getting help with AWS Billing and Cost Management](billing-get-answers.md)\. For information about closing your account, see [Closing an account](close-account.md)\.

## Where do I go from here?<a name="whereto"></a>

 Explore some of the features designed to help you dig a little deeper and streamline your accounting practices\. 
+ [Tracking your AWS Free Tier usage](tracking-free-tier-usage.md)
+ [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)
+ [Analyzing your costs with Cost Explorer](ce-what-is.md)
+ [Managing your costs with AWS Budgets](budgets-managing-costs.md)
+ [Consolidated billing for AWS Organizations](consolidated-billing.md)