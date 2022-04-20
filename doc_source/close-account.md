# Closing an account<a name="close-account"></a>

This page highlights some key concepts for those considering closing your AWS account\. If you have any questions throughout the process, you can contact your account representative or contact AWS Support for assistance\. For more information about contacting AWS Support, see [Contacting AWS Support](billing-get-answers.md#billing-support)\.

For details about closing your AWS Organizations accounts, see [Closing an AWS account](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_close.html) in the *AWS Organizations User Guide*\.

**Topics**
+ [Considerations before you close your AWS account](#before-closing)
+ [Troubleshooting errors when closing an AWS account](#troubleshooting-closing)
+ [Closing your AWS account](#closing-the-account)
+ [Accessing your AWS account after closure](#accessing-after-closure)
+ [After the post\-closure period](#post-closure-period)

## Considerations before you close your AWS account<a name="before-closing"></a>

Before closing your AWS account, consider the following:

**Topics**
+ [Your agreement with AWS](#aws-agreement)
+ [AWS management console access](#console-access)
+ [Existing content and services still in use](#existing-content)
+ [Your payment method](#closure-payment)
+ [Accounts protected by MFA](#mfa-closure)
+ [On\-Demand charges](#on-demand-closure)
+ [Domains registered with Amazon Route 53](#closure-domains)
+ [Charges if you reopen your AWS account](#reopen-charges)
+ [Closing a member account](#closing-member-account)
+ [Cross\-account access to the account you’re closing](#cross-access)
+ [Removing Amazon VPC peering connection](#vpc-peering)

### Your agreement with AWS<a name="aws-agreement"></a>

Your closure of your AWS account serves as a notice to us that you want to terminate the AWS customer agreement or other agreements with AWS that governs your AWS account, solely with respect to the specific AWS account\. If you reopen your AWS account during the *post\-closure period* \(that is, within 90 days after your account is closed\), you agree that the same agreement terms will govern your access to and use of the service offerings through your reopened AWS account\.

If you close the account that you're using for the AWS Firewall Manager administrator, AWS and Firewall Manager handle the closure as follows:

 AWS retains the policy data for the account for 90 days from the effective date of the administrator account closure\. At the end of the 90 day period, AWS permanently deletes all policy data for the account\. 
+  To retain findings for more than 90 days, you can archive the policies\. You can also use a custom action with an EventBridge rule to store the findings in an S3 bucket\. 
+  As long as AWS retains the policy data, when you reopen the closed account, AWS reassigns the account as the service administrator and recovers the service policy data for the account\. 

**Important**  
 For customers in the AWS GovCloud \(US\) Regions:   
 Before closing your account, back up and then delete your policy data and other account resources\. You will no longer have access to them after you close the account\. 

### AWS management console access<a name="console-access"></a>

Your access to the AWS Management Console for the closed AWS account is restricted\. During the post\-closure period, you can still sign in to your AWS account to view your past billing information and access AWS Support\. You can't access any other AWS services or start any new AWS services in the closed account\.

### Existing content and services still in use<a name="existing-content"></a>

Before you close your AWS account, we recommend that you retrieve the content that you want to keep and delete the remaining resources\. For instructions on how to retrieve data and delete resources, see the documentation for that service\.

After the post\-closure period, any remaining content in your AWS account is deleted, and services that are still in use are terminated\. For more information about the post\-closure period, see [Accessing your AWS account after closure](#accessing-after-closure)\.

### Your payment method<a name="closure-payment"></a>

We charge you through your designated payment method for any usage fees incurred before you closed your AWS account\. We might issue you any refunds that are due through that same payment method\. If you have active subscriptions, even after your account is closed, you might continue to be charged for the subscription until the subscription expires or is sold according to the terms governing the subscription\. If you're charged, you're charged through your designated payment method\. This situation might apply to you if, for example, you have a Reserved Instance that you pay for on a monthly basis\. These charges and refunds might occur after you close your account\.

In addition, if you reopen your account, you might be charged for the cost of running AWS services during the post\-closure period\. This is specifically for any services that you didn't terminate before closing your account\.

**Important**  
Closing your AWS account doesn't affect payment methods that you use on Amazon\.com or other Amazon websites\.

### Accounts protected by MFA<a name="mfa-closure"></a>

If you've turned on [multi\-factor authentication \(MFA\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html) on your AWS account root user, or configured an [MFA device on an IAM user](https://docs.aws.amazon.com/IAM/latest/UserGuide/console_sign-in-mfa.html), the MFA isn't removed automatically when you close the account\. If you choose to leave the MFA turned on during the 90 days post\-closure period, keep the virtual hardware MFA device active until the post\-closure period expired in case you need to access the account during that time\.

You have the option to [turn off the MFA device](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_disable.html) before closing the account\. MFA devices for [IAM users](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users_manage.html#id_users_deleting) must be deleted by the account administrator\.

### On\-Demand charges<a name="on-demand-closure"></a>

During the post\-closure period, billing for On\-Demand charges stops\. However, you're billed for any usage that has accrued up until the time you closed your account\. You'll be charged for that usage at the beginning of the next month\. In addition, if you purchased any subscriptions with ongoing payment obligations, you might continue to be charged for them after your account is closed\.

**Important**  
If you don't terminate your resources, you will continue to generate costs\.

### Domains registered with Amazon Route 53<a name="closure-domains"></a>

Domains that are registered with Route 53 are not deleted automatically\. When you're closing your AWS account, you have three options:
+ You can disable automatic renewal, and the domains are deleted when the registration period expires\. For more information, see [Enabling or Disabling Automatic Renewal for a Domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-enable-disable-auto-renewal.html) in the *Amazon Route 53 Developer Guide*\.
+ You can transfer the domains to another AWS account\. For more information, see [Transferring a Domain to a Different AWS account](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-between-aws-accounts.html)\.
+ You can transfer the domains to another domain registrar\. For more information, see [Transferring a Domain from Route 53 to Another Registrar](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-from-route-53.html)\.

If you already closed the account, you can open a case with AWS Support to get help with disabling automatic renewal or transferring your domains\. For more information, see [Contacting AWS Support About Domain Registration Issues](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-contact-support.html)\. There is no charge to open a case for domain registration issues\.

### Charges if you reopen your AWS account<a name="reopen-charges"></a>

If you reopen your AWS account during the post\-closure period, you might be billed for the cost of any AWS services that aren't terminated before you closed your account\.

#### Example<a name="reopen-charges-example"></a>

You reopen your AWS account 30 days after closure, and your AWS account had only an active `t-example.example` Amazon EC2 instance at closure\. The price for a `t-example.example` Amazon EC2 instance in your AWS Region is $0\.01 each hour\. In this case, you might be charged for 30 days x 24 hours x $0\.01 per hour = $7\.20 for your AWS services\.

### Closing a member account<a name="closing-member-account"></a>

When you close an account that was created with AWS Organizations, that account isn't removed from the organization until after the post\-closure period\. During the post\-closure period, a closed member account still counts toward your quota of accounts in the organization\.

To avoid having the account count against the limit, remove member accounts from the organization before closing it\. For more information, see [Closing an AWS account](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_close.html) in the *AWS Organizations User Guide*\.

### Cross\-account access to the account you’re closing<a name="cross-access"></a>

After you close your AWS account, any access requests to your closed account's AWS services from other AWS accounts fail\. This occurs even if you have granted the other accounts permission to access your account's AWS services\. If you reopen your AWS account, other AWS accounts can access your account's AWS services if you have granted the other accounts the necessary permissions\.

### Removing Amazon VPC peering connection<a name="vpc-peering"></a>

AWS currently doesn't delete Amazon VPC peering connections when you close one of the accounts participating in the VPC peering connection\. Any traffic that's destined for the VPC peering connection and originates from other active accounts is dropped\. This is because AWS terminates instances and deletes any security groups in the closed account\. To remove the VPC peering connection, you can delete it from your account using the Amazon VPC console, AWS CLI, or Amazon EC2 API\.

## Troubleshooting errors when closing an AWS account<a name="troubleshooting-closing"></a>

If you receive an error message while trying to close your AWS account, you can contact your account representative or contact us to open a billing or account support case\. Common reasons why you can't close your AWS account include the following situations:
+ Your account is the management account of an organization in AWS Organizations with open member accounts\.
+ You have unpaid invoices for your account\.
+ You aren't signed in to the account as the root user\.
+ You are an active AWS Marketplace seller\.

## Closing your AWS account<a name="closing-the-account"></a>

You can close your AWS account using the following procedure\.<a name="closing-the-account-proc"></a>

**To close your AWS account**

1. Open the Billing and Cost Management console at [https://console.aws.amazon.com/billing/home#/](https://console.aws.amazon.com/billing/home#/)\.

1. On the navigation bar in the upper\-right corner, choose your account name \(or alias\), and choose **Account**\.

1. Scroll to the end of the page to the **Close Account** section\. Read and ensure that you understand the text next to the check box\. After you close an AWS account, you can no longer use it to access AWS services\.

   If the account has a [multi\-factor authentication \(MFA\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa.html) device turned on, keep your MFA device until the 90 day post\-closure period expires, or [turn off](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_disable.html) before closing the account\.

1. Select the check box to accept the terms, and choose **Close Account**\.

1. In the confirmation box, choose **Close Account**\.

## Accessing your AWS account after closure<a name="accessing-after-closure"></a>

After you close an AWS account following the process described in the preceding steps, you can no longer use it to access AWS services\. However, during the Post\-Closure Period, which are the 90 days after your account is closed, you can still view your AWS account's past billing information and access [AWS Support](https://console.aws.amazon.com/support/home)\.

During the Post\-Closure Period, AWS might retain any content that you didn't delete and any AWS services that you didn't terminate before you closed your AWS account\. You can access any remaining content or AWS services only by reopening your account during the Post\-Closure Period\. You can reopen your AWS account by contacting [AWS Support](https://console.aws.amazon.com/support/home)\. If you choose to reopen your account, you can access the content that you didn't delete and AWS services that you didn't terminate before closing your account\. However, you might be charged for the cost of running those AWS services during the Post\-Closure Period\. You can estimate the cost of running AWS services using the [AWS Pricing Calculator](https://docs.aws.amazon.com/pricing-calculator/latest/userguide/what-is-pricing-calculator.html) in the *AWS Pricing Calculator User Guide*\.

## After the post\-closure period<a name="post-closure-period"></a>

After the Post\-Closure Period, we permanently close your AWS account, and you can't reopen it\. Any content that you didn't delete is deleted, and any AWS services that you didn't terminate are terminated\. Service attributes can be retained as long as needed for billing and administration purposes\. You also can't create a new AWS account using the same alias or email address that was registered to your AWS account at the time of its closure\.

If you close the account that you're using for the AWS Firewall Manager administrator, AWS and Firewall Manager handle the closure as follows:

 AWS retains the policy data for the account for 90 days from the effective date of the administrator account closure\. At the end of the 90 day period, AWS permanently deletes all policy data for the account\. 
+  To retain findings for more than 90 days, you can archive the policies\. You can also use a custom action with an EventBridge rule to store the findings in an S3 bucket\. 
+  As long as AWS retains the policy data, when you reopen the closed account, AWS reassigns the account as the service administrator and recovers the service policy data for the account\. 

**Important**  
 For customers in the AWS GovCloud \(US\) Regions:   
 Before closing your account, back up and then delete your policy data and other account resources\. You will no longer have access to them after you close the account\. 