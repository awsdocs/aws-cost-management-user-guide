# Overview of managing access permissions<a name="control-access-billing"></a>

AWS Billing integrates with the AWS Identity and Access Management \(IAM\) service so that you can control who in your organization has access to specific pages on the [AWS Billing console](https://console.aws.amazon.com/billing/)\. You can control access to invoices and detailed information about charges and account activity, budgets, payment methods, and credits\.

For instructions on how to activate access to the AWS Billing console, see [Tutorial: Delegate Access to the Billing Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_billing.html) in the *IAM User Guide*\.

**Topics**
+ [Granting access to your billing information and tools](#grantaccess)
+ [Activating access to the AWS Billing console](#ControllingAccessWebsite-Activate)

## Granting access to your billing information and tools<a name="grantaccess"></a>

The AWS account owner can access billing information and tools by signing in to the AWS Management Console using the account password\. We don't recommend that you use the account password for everyday access to the account or share your account credentials with others\. 

Instead, you should create a special user identity that's called an *IAM user* for anyone who might need access to the account\. This approach provides individual sign\-in information for each user, and you can grant each user only the permissions they need\. More specifically, you can grant some users limited access to some of your billing information and tools\. Then, grant others complete access to all of the information and tools\. We also recommend that the account owner also access the account by using an IAM user identity\.

By default, IAM users don't have access to the [AWS Billing console](https://console.aws.amazon.com/billing/)\. You or your account administrator must grant users access\. You can do this by activating IAM user access to the Billing console and attaching an IAM policy to your users\. This can be either managed or custom\. Then, you must activate IAM user access for IAM policies to take effect\. You only need to activate IAM user access once\.

**Note**  
IAM is a feature of your AWS account\. If you're already signed up for a product that's integrated with IAM, you don't need to do anything else to sign up for IAM\. Moreover, you're not charged for using IAM\.  
Permissions for Cost Explorer apply to all accounts and member accounts, regardless of the IAM policies\. For more information about Cost Explorer access, see [Controlling access for Cost Explorer](ce-access.md)\.

## Activating access to the AWS Billing console<a name="ControllingAccessWebsite-Activate"></a>

By default, IAM users and roles within an AWS account can't access the Billing console pages\. This is true even if the IAM user or role has IAM policies that grant access to certain Billing features\. The AWS account root user can allow IAM users and roles access to Billing console pages by using the **Activate IAM Access** setting\.

On the Billing console, the **Activate IAM Access** setting controls IAM user and role access to the following pages:
+ Home
+ Cost Explorer
+ Budgets
+ Budgets Reports
+ AWS Cost and Usage Reports
+ Cost categories
+ Cost allocation tags
+ Bills
+ Payments
+ Credits
+ Purchase Order
+ Billing preferences
+ Payment methods
+ Tax settings

On the Cost Management console, the **Activate IAM Access** setting controls IAM user and role access to the following pages:
+ Home
+ Cost Explorer
+ Reports
+ Rightsizing recommendations
+ Savings Plans recommendations
+ Savings Plans utilization report
+ Savings Plans coverage report
+ Reservations overview
+ Reservations recommendations
+ Reservations utilization report
+ Reservations coverage report
+ Preferences

**Important**  
Activating IAM access alone doesn't grant IAM users and roles the necessary permissions for these Billing console pages\. In addition to activating IAM access, you must also attach the required IAM policies to those users or roles\. For more information, see [Using identity\-based policies \(IAM policies\) for AWS Billing](billing-permissions-ref.md)\.

The **Activate IAM Access** setting doesn't control access to the following pages and resources:
+ The console pages for AWS Cost Anomaly Detection, Savings Plans overview, Savings Plans inventory, Purchase Savings Plans, and Savings Plans cart
+ The Cost Management view in the AWS Console Mobile Application
+ The Billing SDK APIs \(AWS Cost Explorer, AWS Budgets, and AWS Cost and Usage Reports APIs\)
+ The cost and usage widget on the AWS Console and AWS Systems Manager Application Manager\.

To activate the **Activate IAM Access** setting, you must log in to your AWS account using the root user credentials, and then select the setting in the [My Account](https://console.aws.amazon.com/billing/home#/account) page\. Activate this setting in each account where you want to allow IAM user and role access to the Billing console pages\. If you use AWS Organizations, activate this setting in each management or member account where you want to allow IAM user and role access to console pages\.

**Note**  
The **Activate IAM Access** setting isn't available to IAM users with administrator access\. This setting is available only to the root user of the account\.

If the **Activate IAM Access** setting isn't activated, then IAM users and roles in the account can't access the Billing console pages\. This is true even if they have administrator access or the required IAM policies\.<a name="billing-activate-iam-access"></a>

**To activate IAM user and role access to the Billing and Cost Management console**

1. Sign in to the AWS Management Console with your root account credentials \(specifically, the email address and password that you used to create your AWS account\)\.

1. On the navigation bar, choose your account name, and then choose [My Account](https://console.aws.amazon.com/billing/home#/account)\.

1. Next to **IAM User and Role Access to Billing Information**, choose **Edit**\.

1. Select the **Activate IAM Access** check box to activate access to the Billing and Cost Management console pages\.

1. Choose **Update**\.

After you activate IAM access, you must also attach the required IAM policies to the IAM users or roles\. The IAM policies can grant or deny access to specific Billing features\. For more information, see [Using identity\-based policies \(IAM policies\) for AWS Billing](billing-permissions-ref.md)\.