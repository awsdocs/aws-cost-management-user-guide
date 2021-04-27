# Overview of managing access permissions<a name="control-access-billing"></a>

AWS Billing and Cost Management integrates with the AWS Identity and Access Management \(IAM\) service so that you can control who in your organization has access to specific pages on the [AWS Billing and Cost Management console](https://console.aws.amazon.com/billing/home#/)\. You can control access to invoices and detailed information about charges and account activity, budgets, payment methods, and credits\.

For more information about how to activate access to the Billing Console, see [Tutorial: Delegate Access to the Billing Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_billing.html) in the *IAM User Guide*\.

**Topics**
+ [Granting access to your billing information and tools](#grantaccess)
+ [Activating access to the Billing and Cost Management console](#ControllingAccessWebsite-Activate)

## Granting access to your billing information and tools<a name="grantaccess"></a>

The AWS account owner can access billing information and tools by signing in to the AWS Management Console using the account password\. We recommend that you don't use the account password for everyday access to the account, and especially that you don't share account credentials with others to give them access to your account\. 

Instead, you should create a special user identity called an *IAM user* for anyone who might need access to the account\. This approach provides individual sign\-in information for each user, and you can grant each user only the permissions they need to work with your account\. For example, you can grant some users limited access to some of your billing information and tools, and grant others complete access to all of the information and tools\. \(We recommend that the account owner also access the account by using an IAM user identity\.\)

By default, IAM users do not have access to the [AWS Billing and Cost Management console](https://console.aws.amazon.com/billing/home#/)\. You or your account administrator must grant users access\. You can do this by activating IAM user access to the Billing and Cost Management console and attaching an IAM policy to your users\. This can be either managed or custom\. Then, you need to activate IAM user access for IAM policies to take effect\. You only need to activate IAM user access once\.

**Note**  
IAM is a feature of your AWS account\. If you are already signed up for a product that is integrated with IAM, you don't need to do anything else to sign up for IAM, nor will you be charged for using it\.  
Permissions for Cost Explorer apply to all accounts and member accounts, regardless of IAM policies\. For more information about Cost Explorer access, see [Controlling access for Cost Explorer](ce-access.md)\.

## Activating access to the Billing and Cost Management console<a name="ControllingAccessWebsite-Activate"></a>

Access to the Billing and Cost Management console \(except for AWS Cost Anomaly Detection, Savings Plan Overview, Savings Plans inventory, Purchase Savings Plan, and Savings Plan cart consoles\) is controlled by the **Activate IAM Access** functionality\. If you want to activate the Billing and Cost Management console for all linked accounts in your organization, you can do so by selecting **Activate IAM Access** from the root user in each member account\. Once IAM access is activated, IAM Users, Roles, and Groups with the necessary IAM policies \(see [Using identity\-based policies \(IAM policies\) for Billing and Cost Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-permissions-ref.html)\) will be able to access AWS Billing and Cost Management consoles\. If IAM access is not activated using this procedure, accounts in your organization won’t be able to access AWS Billing and Cost Management consoles, regardless of if they have the necessary IAM policies\.

This IAM access setting does not control access to AWS Cost Anomaly Detection, Savings Plan overview, Savings Plans inventory, Purchase Savings Plan, and Savings Plan cart pages within Cost Explorer console\. You do not need to select **Activate IAM Access** for these pages\. Access to these pages is controlled using IAM policies only\. 

**Important**  
This functionality activates only AWS Billing and Cost Management console access and does not control access to Billing and Cost management information via the AWS APIs\. See see [Using the Cost Explorer API](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/ce-api.html) for information on how to access billing and cost information using APIs\. In addition to activating IAM access, an IAM User, Role, or Group must have the required IAM actions included in their IAM policy to be able to access AWS Billing and Cost Management console\. 

**To activate IAM user and role access to the Billing and Cost Management console**

1. Sign in to the AWS Management Console with your root account credentials \(the email address and password that you used to create your AWS account\)\.

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Next to **IAM User and Role Access to Billing Information**, choose **Edit**\. 

1. Select the ** Activate IAM Access** check box to activate access to the Billing and Cost Management pages\. 

1. Choose **Update**\.

 You can now use IAM policies to control which pages a user can access\.

After you have activated IAM user access, you can attach IAM policies to grant or deny access to specific billing features\. For more information about using policies to grant IAM users access to Billing and Cost Management features, see [Using identity\-based policies \(IAM policies\) for Billing and Cost Management](billing-permissions-ref.md)\.