# What is AWS Billing?<a name="billing-what-is"></a>

Welcome to the Billing User Guide\.

The AWS Billing console contains features to pay your AWS bills and report your AWS cost and usage\. You can also use the AWS Billing console to manage your consolidated billing if you're a part of AWS Organizations\. Amazon Web Services automatically charges the credit card that you provided when you sign up for an AWS account\. You can view or update your credit card information at any time, including designating a different credit card for AWS to charge\. You can do this on the [https://console.aws.amazon.com/billing/home?#/paymentmethods](https://console.aws.amazon.com/billing/home?#/paymentmethods) page in the Billing console\. For more details on the Billing features available, see [Features of AWS Billing console](#billingfeatures)\.

**How to find answers about your AWS bills**  
For questions about your AWS bills or to appeal any of your charges, contact AWS Support to address your inquiries immediately\. For options on how you can get help, see [Getting help with AWS Billing](billing-get-answers.md)\. To understand your bills page contents, see [Viewing your monthly charges](invoice.md)\.

**Key differences between AWS Billing console and AWS Cost Management console features**  
The Billing console works closely with the AWS Cost Management console\. The Billing console contains features to manage your ongoing payments and payment methods registered to your AWS account\. The AWS Cost Management console features are useful to optimize your future costs\. You can use both for a holistic approach to managing your current and ongoing costs\. For information about AWS resources to optimize your costs, see the [https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html](https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html)\.

**Pricing and marketing materials for AWS Billing features**  
For more information about individual feature pricing and marketing materials, see the [http://aws.amazon.com/aws-cost-management/](http://aws.amazon.com/aws-cost-management/)\.

## Features of AWS Billing console<a name="billingfeatures"></a>

With the features in AWS Billing console, you can do the following tasks:
+ [**Manage your account**](change-account-settings.md): Manage your account settings using the AWS Management Console and Billing console\. This includes designating your default currency, editing alternate contacts, adding or removing AWS Regions, updating your tax information, and closing your AWS account\. The [Closing an account](close-account.md) highlights considerations before you close your AWS account\. For example, terminating resources before you close the account so you aren't charged for unused services\.
+ [**View your bill**](getting-viewing-bill.md): You can use the AWS Billing console to view your past bill details or your estimated charges for your current month at any time\. This section outlines how you can view your bills, download PDF copies of your charges, and set up monthly emails to receive your invoices\. It also covers how you can use other resources such as [AWS Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.
+ [**Managing your payments**](manage-payments.md): You can view your estimated bills and pay your AWS invoices in your preferred currency by setting a payment currency\. AWS converts your bill to your preferred currency after your bill is finalized\. Until then, all of the preferred currency amounts shown in the console are estimated in USD\. AWS guarantees your exchange rate\. This is so that refunds use the same exchange rate as your original transaction\.
**Note**  
AWS Marketplace invoices aren't eligible for this service and are processed in US dollar\.
This service is available only if your default payment method is Visa or MasterCard\.
The rates change daily\. The rate that's applied to your invoice is the current rate at the time when your invoice was created\. You can check the current rate on the Billing console\.
Currency conversion is provided by Amazon Services LLC\.
+ [**AWS Purchase Order Management**](manage-purchaseorders.md): Manage your AWS purchase orders in a self\-service fashion by taking care of multiple purchase orders all in one place\. This can help to reduce your overhead costs and increase the accuracy and efficiency in your overall procure\-to\-pay process\. Use the Billing console to manage your purchase orders and configure how it reflects on your invoices\. In this section, learn how to add, edit, view details, and set up notifications regarding your purchase orders in the console\.
+ [**AWS Cost Categories**](manage-cost-categories.md): Manage your AWS costs with AWS Cost Categories by mapping your cost and usage into meaningful categories\. This section defines terms that are used in the console for supported dimensions, operations, rule types, and status\. The section also provides more information on how you can create, edit, delete, and split the charges within cost categories\.
+ [**Payment profile**](manage-paymentprofiles.md): You can use payment profiles to assign more than one payment method to your automatic payments\. If you receive invoices from more than one AWS service provider \("seller of record"\), you can use payment profiles to assign a unique payment method for each one\. After you create a payment profile for a service provider, your payment profile pays your AWS bills automatically\. In this section, learn how to use the Billing console to set up custom payment profile\.
+ [**Consolidate billing for AWS Organizations**](consolidated-billing.md): Use the consolidated billing feature for AWS Organizations to combine your billing for multiple AWS accounts\. This chapter outlines the consolidated billing process, differences for Amazon Web Services India Private Limited accounts, and details for discounts\.

## Related services<a name="relatedservices"></a>

[https://docs.aws.amazon.com/account-billing/index.html](https://docs.aws.amazon.com/account-billing/index.html)  
AWS Billing Conductor is a custom billing service to group your accounts by financial owner, configure billing parameters, and generate AWS Cost and Usage Reports per group\. AWS Billing Conductor is a fully managed service that can support the showback and chargeback workflows of AWS Solution Providers and Enterprise customers\.

[https://docs.aws.amazon.com/iam/?icmpid=docs_homepage_security](https://docs.aws.amazon.com/iam/?icmpid=docs_homepage_security)  
The Billing service and AWS Cost Management service is closely integrated with AWS Identity and Access Management \(IAM\)\. You can use IAM with Billing to ensure that other people who work in your account have as much access as they need to get their jobs done\.  
You also use IAM to control access to all of your AWS resources, not only your billing information\. It's important that you familiarize yourself with the major concepts and best practices of IAM before you get too far along with setting up the structure of your AWS account\.

[https://docs.aws.amazon.com/organizations/?icmpid=docs_homepage_mgmtgov](https://docs.aws.amazon.com/organizations/?icmpid=docs_homepage_mgmtgov)  
You can use AWS products and services to accommodate a company of any size, from small start\-ups to enterprises\. If your company is large or likely to grow, you might want to set up multiple AWS accounts that reflect your company's specific structure\. For example, you can have one account for the entire company and accounts for each employee, or an account for the entire company with IAM users for each employee\. You can have an account for the entire company, accounts for each department or team within the company, and accounts for each employee\.  
If you create multiple accounts, you can use the consolidated billing feature of AWS Organizations to combine all member accounts under a management account\. That way, you can receive a single bill for all of your member accounts\. For more information, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.