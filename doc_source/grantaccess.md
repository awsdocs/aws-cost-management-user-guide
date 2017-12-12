# Granting Access to Your Billing Information and Tools<a name="grantaccess"></a>

The AWS account owner can access billing information and tools by signing in to the AWS Management Console using the account password\. However, we recommend that you don't use the account password for everyday access to the account, and especially that you don't share account credentials with others to give them access to your account\. 

Instead, you should create a special user identity called an *IAM user* for anyone who might need access to the account\. This approach provides individual sign\-in information for each user, and you can grant each user only the permissions that he or she needs to work with your account\. For example, you can grant some users limited access to some of your billing information and tools, and grant others complete access to all of the information and tools\. \(We recommend that the account owner also access the account by using an IAM user identity\.\)

**Note**  
IAM is a feature of your AWS account\. If you are already signed up for a product that is integrated with IAM, you don't need to do anything else to sign up for IAM, nor will you be charged for using it\.

By default, IAM users do not have access to the [AWS Billing and Cost Management console](https://console.aws.amazon.com/billing/home#/)\. You or your account administrator must grant users access\. Do this by activating IAM user access to the Billing and Cost Management console and attaching an IAM policy, either managed or custom, to your users\. You need to activate IAM user access for IAM policies to take affect\. You need to activate IAM user access only once\. 

**Note**  
Permissions for Cost Explorer apply to all accounts and linked accounts, regardless of IAM policies\. For more information about Cost Explorer access, see [Controlling Access for Cost Explorer](cost-explorer-access.md)

## Activating Access to the Billing and Cost Management Console<a name="ControllingAccessWebsite-Activate"></a>

To be able to grant your IAM users access to your account's Billing and Cost Management console, you must *activate* the functionality\. 

**To activate IAM user access to the Billing and Cost Management console**

1. Sign in to the AWS Management Console with your root account credentials \(the email address and password that you used to create your AWS account\)\. Don't sign in with your IAM user credentials\. 

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Next to **IAM User Access to Billing Information**, choose **Edit**\. 

1. Select the ** Activate IAM Access** check box to activate access to the Billing and Cost Management pages\. You can now use IAM policies to control which pages a user can access\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

   After you have activated IAM user access, you can attach IAM policies to grant or deny access to specific billing features\. For more information about using policies to grant IAM users access to Billing and Cost Management features, see [Billing and Cost Management Permissions Reference](billing-permissions-ref.md)\.
**Important**  
When you activate IAM user access to the Billing and Cost Management console, you grant full access to all users who already have full access to the AWS APIs\. You can restrict their access by applying an IAM policy that constrains their permissions\. See Example [Example 4: Allow full access to AWS services but deny IAM users access to the Billing and Cost Management console](billing-permissions-ref.md#ExampleAllowAllDenyBilling)\.