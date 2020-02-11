# What Is AWS Billing and Cost Management?<a name="billing-what-is"></a>

AWS Billing and Cost Management is the service that you use to pay your AWS bill, monitor your usage, and budget your costs\. 

AWS automatically charges the credit card you provided when you signed up for a new account with AWS\. Charges appear on your credit card bill monthly\. You can view or update credit card information, and designate a different credit card for AWS to charge, on the [https://console.aws.amazon.com/billing/home?#/paymentmethods](https://console.aws.amazon.com/billing/home?#/paymentmethods) page in the Billing and Cost Management console\. For more information about accessing the console, see [Opening the Billing and Cost Management Console and Dashboard](view-billing-dashboard.md#opening-billing-dashboard)\.

**Note**  
If you chose India as your contact address country when you signed up, you might be an Amazon Internet Services Pvt\. Ltd \(AISPL\) customer, and you might need to approve the charges before your credit card can be billed\. For more information about paying as an AISPL customer, see [To pay your AISPL bill](edit-aispl-payment-method.md#aispl-pay-bill)\.

**Topics**
+ [Features in Billing and Cost Management](#billingfeatures)
+ [Are You a First\-Time Billing User?](#billingresources)
+ [Related Services](#relatedservices)

## Features in Billing and Cost Management<a name="billingfeatures"></a>

The Billing and Cost Management service provides features that you can use to estimate and plan your AWS costs, receive alerts if your costs exceed a threshold that you set, assess your biggest investments in AWS resources, and, if you work with multiple AWS accounts, simplify your accounting\.

**Analyzing Costs with Graphs**  
The AWS Billing and Cost Management console includes the no\-cost [Cost Explorer](ce-what-is.md) tool for viewing your AWS cost data as a graph\. With Cost Explorer, you can filter graphs by values such as API operation, Availability Zone, AWS service, custom cost allocation tag, Amazon EC2 instance type, purchase option, region, usage type, usage type group, and more\. If you use consolidated billing, you can also filter by member account\. In addition, you can see a forecast of future costs based on your historical cost data\.

**Budgets**  
You can use budgets to track your AWS usage and costs\. Budgets use the cost visualization provided by Cost Explorer to show you the status of your budgets, to provide forecasts of your estimated costs, and to track your AWS usage, including your free tier usage\. You can also use budgets to create Amazon SNS notifications that notify you when you go over your budgeted amounts, or when your estimated costs exceed your budgets\.  
For more information about budgets, see [Managing Your Costs with Budgets](budgets-managing-costs.md)\.

**AWS Cost and Usage Reports**  
You can choose to have AWS publish billing reports to an Amazon Simple Storage Service \(Amazon S3\) bucket that you own\. You can receive reports that break down your costs by the hour or month, by product or product resource, or by tags that you define yourself\.  
For more details about AWS Cost and Usage Reports, see the [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.

**Payment Currencies**  
You can view your estimated bills and pay your AWS invoices in your preferred currency by setting a payment currency\.  
AWS converts your bill to your preferred currency after your bill is finalized\. Until then, all of the preferred currency amounts shown in the console are estimated in USD\. AWS guarantees your exchange rate, so that refunds use the same exchange rate as your original transaction\.  
Additional details:  
+ AWS Marketplace invoices are not eligible for this service and are processed in USD\.
+ This service is available only if your default payment method is Visa or MasterCard\.
+ The rates change daily\. The rate applied to your invoice is the current rate when your invoice is created\. You can check the current rate on the Billing and Cost Management console\.
+ You can switch back to USD\.
+ Currency conversion is provided by Amazon Services LLC\.

## Are You a First\-Time Billing User?<a name="billingresources"></a>

If you're new to the AWS Billing and Cost Management service, we recommend that you begin with the [Getting Started](billing-getting-started.md) section, which shows you how to use the **Billing and Cost Management** console\.

If you're new to AWS, we recommend that you review [Getting Started with AWS](http://docs.aws.amazon.com/gettingstarted/latest/awsgsg-intro/getstarted.html)\. This guide has useful general information about using AWS and managing your account\. 

## Related Services<a name="relatedservices"></a>

**IAM**  
The Billing and Cost Management service is tightly integrated with the AWS Identity and Access Management \(IAM\) service\. You can use IAM with Billing and Cost Management to ensure that other people who work in your account have only as much access as they need to get their job done\.  
The IAM service is also how you control access to all of your AWS resources, not just your billing information, so it's important to familiarize yourself with the basic concepts and best practices of IAM before you get too far along with setting up the structure of your AWS account\.  
For details about how to work with IAM and why it's important to do so, see [IAM Concepts](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_Concepts.html) and [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAMBestPractices.html) in the *IAM User Guide*\. 

**AWS Organizations \(Consolidated Billing\)**  
The AWS platform is designed to accommodate every size of company, from small startups to enterprises\. If your company is large or likely to grow, you might want to set up multiple AWS accounts that reflect your company's structure\. For example, you can have one account for the entire company and accounts for each employee, you can have an account for the entire company with IAM users for each employee, or you can have an account for the entire company, accounts for each department or team within the company, and accounts for each employee\.  
If you create multiple accounts, you can use the Consolidated Billing feature of AWS Organizations to combine all member accounts under a master account, and receive a single bill\. For more information, see [Consolidated Billing for Organizations](consolidated-billing.md)\.