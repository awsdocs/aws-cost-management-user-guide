# What is AWS Billing and Cost Management?<a name="billing-what-is"></a>

AWS Billing and Cost Management is the service that you use to pay your AWS bill, monitor your usage, and analyze and control your costs\. 

AWS automatically charges the credit card that you provided when you signed up for a new account with AWS\. Charges appear on your monthly credit card bill\. You can view or update your credit card information, including designating a different credit card for AWS to charge, on the [https://console.aws.amazon.com/billing/home?#/paymentmethods](https://console.aws.amazon.com/billing/home?#/paymentmethods) page in the Billing and Cost Management console\. AWS Billing and Cost Management provides useful tools to help you gather information related to your cost and usage, analyze your cost drivers and usage trends, and take action to budget your spending\.

**Topics**
+ [Are you a first\-time billing user?](#billingresources)
+ [Features in Billing and Cost Management](#billingfeatures)
+ [Related services](#relatedservices)

## Are you a first\-time billing user?<a name="billingresources"></a>

If you're new to AWS, we recommend that you review [Getting Started with AWS](http://docs.aws.amazon.com/gettingstarted/latest/awsgsg-intro/getstarted.html)\. This guide has useful general information about using AWS and managing your account\. 

If you're new to the AWS Billing and Cost Management service, we recommend that you read the following:

1. [Getting started](billing-getting-started.md) \- Shows you how to use the [Billing and Cost Management](https://console.aws.amazon.com/billing/home) console\. It also shows the feature options that you can use to monitor your AWS usage\.

1. [Using the AWS Free Tier](billing-free-tier.md) \- Describes how you can use the AWS Free Tier for your first 12 months after signing up\.

1. [Managing your payments](manage-payments.md) \- Shows you how to set up your payment methods on your AWS account\.

1. [Actions](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/API_Operations.html) \- Describes the Billing and Cost Management API operations\.

1. [Getting help](billing-get-answers.md) \- Shows you how to get help for your tools and find answers to questions about your bill\. It includes the steps you can take to contact AWS Support about your AWS charges\.

## Features in Billing and Cost Management<a name="billingfeatures"></a>

The Billing and Cost Management service provides features that you can use to do the following:
+ Estimate and plan your AWS costs
+ Receive alerts if your costs exceed a threshold that you set
+ Assess your biggest investments in AWS resources
+ Simplify your accounting if you work with multiple AWS accounts

**Analyzing Costs with Cost Explorer**  
The AWS Billing and Cost Management console includes the no\-cost [Cost Explorer](ce-what-is.md) tool for viewing your AWS cost data as a graph\. With Cost Explorer, you can filter graphs by values such as API operation, Availability Zone, AWS service, custom cost allocation tag, Amazon EC2 instance type, purchase option, AWS Region, usage type, usage type group, and more\. If you use consolidated billing, you can also filter by member account\. In addition, you can see a forecast of future costs based on your historical cost data\.

**AWS Budgets**  
You can use AWS Budgets to track your AWS usage and costs\. Budgets use the cost visualization provided by Cost Explorer to show you the status of your budgets\. This provides forecasts of your estimated costs and tracks your AWS usage, including your free tier usage\. You can also use budgets to create Amazon Simple Notification Service \(Amazon SNS\) notifications that tell you when you go over your budgeted amounts, or when your estimated costs exceed your budgets\.  
For more information about budgets, see [Managing your costs with AWS Budgets](budgets-managing-costs.md)\.

****  
You can choose to have AWS publish billing reports to an Amazon Simple Storage Service \(Amazon S3\) bucket that you own\. You can receive reports that break down your costs by the hour or month, by product or product resource, or by tags that you define yourself\.  
For more details about , see the [ User Guide](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.

**Manage Your payments**  
You can view your estimated bills and pay your AWS invoices in your preferred currency by setting a payment currency\.  
AWS converts your bill to your preferred currency after your bill is finalized\. Until then, all of the preferred currency amounts shown in the console are estimated in USD\. AWS guarantees your exchange rate, so that refunds use the same exchange rate as your original transaction\.  
+ AWS Marketplace invoices are not eligible for this service and are processed in USD\.
+ This service is available only if your default payment method is Visa or MasterCard\.
+ The rates change daily\. The rate applied to your invoice is the current rate when your invoice is created\. You can check the current rate on the Billing and Cost Management console\.
+ You can switch back to USD\.
+ Currency conversion is provided by Amazon Services LLC\.
For more details about your payment methods, see [Managing your payments](manage-payments.md)\.

## Related services<a name="relatedservices"></a>

**IAM**  
The Billing and Cost Management service is tightly integrated with AWS Identity and Access Management \(IAM\)\. You can use IAM with Billing and Cost Management to ensure that other people who work in your account have only as much access as they need to get their job done\.  
You also use IAM to control access to all of your AWS resources, not just your billing information\. It's important that you familiarize yourself with the basic concepts and best practices of IAM before you get too far along with setting up the structure of your AWS account\.  
For details about how to work with IAM and why it's important to do so, see [IAM Concepts](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_Concepts.html) and [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAMBestPractices.html) in the *IAM User Guide*\. 

**AWS Organizations \(Consolidated Billing\)**  
AWS products and services are designed to accommodate every size of company, from small start\-ups to enterprises\. If your company is large or likely to grow, you might want to set up multiple AWS accounts that reflect your company's structure\. For example, you can have one account for the entire company and accounts for each employee, or an account for the entire company with IAM users for each employee\. You can have an account for the entire company, accounts for each department or team within the company, and accounts for each employee\.  
If you create multiple accounts, you can use the Consolidated Billing feature of AWS Organizations to combine all member accounts under a management account, and receive a single bill\. For more information, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.