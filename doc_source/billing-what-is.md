# What is AWS Billing?<a name="billing-what-is"></a>

Welcome to the Billing User Guide\.

The AWS Billing console contains features to organize and report your AWS cost and usage based on user\-defined methods, and manage your billing and control costs\.

The Billing console works closely with the AWS Cost Management console so you can holistically manage your costs\. The Billing console contains resources to manage your ongoing payments, while the AWS Cost Management console resources are designed to help you optimize your future costs\. For information about AWS resources to optimize your costs, see the [https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html](https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html)\.

AWS automatically charges the credit card that you provided when you signed up for a new account with AWS\. Charges appear on your monthly credit card bill\. You can view or update your credit card information, including designating a different credit card for AWS to charge, on the [https://console.aws.amazon.com/billing/home?#/paymentmethods](https://console.aws.amazon.com/billing/home?#/paymentmethods) page in the Billing console\. Billing provides useful tools to help you gather information related to your cost and usage, analyze your cost drivers and usage trends, and take action to budget your spending\.

With the AWS Cost Management console and the Billing console, you can do the following tasks:


| Use cases | Description | AWS Cost Management feature names | Billing console feature names | 
| --- | --- | --- | --- | 
| Organize | Construct your cost allocation and governance foundation with your own tagging strategy\. | \- | [AWS Cost Categories](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/manage-cost-categories.html) [AWS Cost Allocation Tags](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html) | 
|  Report  | Raise awareness and accountability of your cloud spend with the detailed, allocable cost data\. |  [AWS Cost Explorer](ce-what-is.md)  | [AWS Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html) | 
| Access | Track billing information across the organization in a consolidated view\. | \- | [AWS Consolidated Billing](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/consolidated-billing.html) [AWS Purchase Order Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/manage-purchaseorders.html) [AWS Credits](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/useconsolidatedbilling-credits.html) | 
|  Control  | Establish effective governance mechanisms with the right guardrails in place\. |  [AWS Cost Anomaly Detection](manage-ad.md)  | \- | 
| Forecast | Estimate your resource utilization and spend with forecast dashboards that you create\. | [AWS Cost Explorer](ce-what-is.md) [AWS Budgets](budgets-managing-costs.md) | \- | 
| Budget | Keep your spend in check with custom budget threshold and auto alert notification\. | [AWS Budgets](budgets-managing-costs.md) [AWS Budgets Actions](budgets-controls.md) | \- | 
| Purchase | Leverage free trials and programmatic discounts based on your workload pattern and needs\. |  [Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html) [AWS Reserved Instances](ri-recommendations.md)  | [AWS Free Tier](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-free-tier.html) | 
| Rightsize | Align your service allocation size to your actual workload demand\. |  [Rightsizing Recommendations](ri-recommendations.md)  | \- | 
| Inspect | Stay up\-to\-date with your resource deployment and cost optimization opportunities\. |  [AWS Cost Explorer](ce-what-is.md)  | \- | 

## Features of Billing<a name="billingfeatures"></a>

**Manage your account**  
Use the AWS Management Console and Billing console to manage your account settings\. This includes specifying your default currency, editing alternate contacts, adding or removing Regions, updating your tax information, and closing your AWS account\. The [Closing an account](close-account.md) section calls out considerations such as terminating resources before you proceed with closing an account, so you aren't charged for unused services\.  
**Documentation:** [Managing your account](change-account-settings.md)

**View your bill**  
You can use the Billing console to view your past bill details or your estimated charges for your current month at any time\. This section outlines how you can view your bills, download PDF copies of your charges, set up monthly emails to receive your invoices, and how you can utilize other resources like [AWS Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.  
**Documentation:** [Viewing your bill](getting-viewing-bill.md)

**Managing your payments**  
You can view your estimated bills and pay your AWS invoices in your preferred currency by setting a payment currency\. AWS converts your bill to your preferred currency after your bill is finalized\. Until then, all of the preferred currency amounts shown in the console are estimated in US dollar\. AWS guarantees your exchange rate, so that refunds use the same exchange rate as your original transaction\.  
+ AWS Marketplace invoices are not eligible for this service and are processed in US dollar\.
+ This service is available only if your default payment method is Visa or MasterCard\.
+ The rates change daily\. The rate applied to your invoice is the current rate when your invoice is created\. You can check the current rate on the Billing console\.
+ Currency conversion is provided by Amazon Services LLC\.
**Documentation:** [Managing your payments](manage-payments.md)\.

**AWS Purchase Order Management**  
Manage your AWS purchase orders in a self\-service manner by centralizing the management of multiple purchase orders, reduce overhead costs, and increase the accuracy and efficiency in you procure\-to\-pay process\. Use the Billing console to manage your purchase orders and configure how they reflect on your invoices\. In this chapter, learn how to add, edit, view details, and set up notifications regarding your purchase orders in the console\.  
**Documentation:** [Managing your purchase orders](manage-purchaseorders.md)

**AWS Cost Categories**  
Manage your AWS costs with AWS Cost Categories by mapping your cost and usage into meaningful categories\. This section defines terms used in the console for supported dimensions, operations, rule types, and status\. The section also provides more information on how you can create, edit, delete, and split the charges within cost categories\.  
**Documentation:** [Managing your costs with AWS Cost Categories](manage-cost-categories.md)

**Consolidate billing for AWS Organizations**  
Use the consolidated billing feature for AWS Organizations to combine your billing for multiple AWS accounts\. This chapter outlines the consolidated billing process, differences for Amazon Internet Services Pvt\. Ltd accounts, and details for discounts\.  
**Documentation:** [Consolidated billing for AWS Organizations](consolidated-billing.md)

## Related services<a name="relatedservices"></a>

**IAM**  
The Billing service and AWS Cost Management service is tightly integrated with AWS Identity and Access Management \(IAM\)\. You can use IAM with Billing to ensure that other people who work in your account have as much access as they need to get their jobs done\.  
You also use IAM to control access to all of your AWS resources, not just your billing information\. It's important that you familiarize yourself with the basic concepts and best practices of IAM before you get too far along with setting up the structure of your AWS account\.  
For details about how to work with IAM and why it's important to do so, see [IAM Concepts](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAM_Concepts.html) and [IAM Best Practices](https://docs.aws.amazon.com/IAM/latest/UserGuide/IAMBestPractices.html) in the *IAM User Guide*\. 

**AWS Organizations \(Consolidated Billing\)**  
AWS products and services are designed to accommodate every size of company, from small start\-ups to enterprises\. If your company is large or likely to grow, you might want to set up multiple AWS accounts that reflect your company's structure\. For example, you can have one account for the entire company and accounts for each employee, or an account for the entire company with IAM users for each employee\. You can have an account for the entire company, accounts for each department or team within the company, and accounts for each employee\.  
If you create multiple accounts, you can use the consolidated billing feature of AWS Organizations to combine all member accounts under a management account, and receive a single bill\. For more information, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.