# Closing an account<a name="close-account"></a>

Only the AWS account root user can close an AWS account\. AWS can't close accounts on your behalf\. If you have any questions throughout the process, you can contact your account representative or contact AWS Support for assistance\. For more information about contacting AWS Support, see [Contacting AWS Support](billing-get-answers.md#billing-support)\.

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
+ [On\-Demand charges](#on-demand-closure)
+ [Domains registered with Amazon Route 53](#closure-domains)
+ [Charges if you reopen your AWS account](#reopen-charges)
+ [Closing a member account](#closing-member-account)
+ [Cross\-account access to the account you’re closing](#cross-access)
+ [Removing Amazon VPC peering connection](#vpc-peering)

### Your agreement with AWS<a name="aws-agreement"></a>

Your closure of your AWS account serves as notice to us that you want to terminate the AWS customer agreement or other agreement with AWS that governs your AWS account, solely with respect to the specific AWS account\. If you reopen your AWS account during the *post\-closure period* \(that is, within 90 days after your account is closed\), you agree that the same agreement terms will govern your access to and use of the service offerings through your reopened AWS account\.

### AWS management console access<a name="console-access"></a>

Your access to the AWS Management Console for the closed AWS account is restricted\. During the post\-closure period, you can still sign in to your AWS account to view your past billing information and access AWS Support\. You can't access any other AWS services or start any new AWS services in the closed account\.

### Existing content and services still in use<a name="existing-content"></a>

After the post\-closure period, any remaining content in your AWS account is deleted, and services that are still in use are terminated\. Before closing your account, you should retrieve all content from the account\. For instructions on how to retrieve your content, see the documentation for that service\. For more information about the post\-closure period, see [Accessing your AWS account after closure](#accessing-after-closure)\.

### Your payment method<a name="closure-payment"></a>

We charge you through your designated payment method for any usage fees incurred before you closed your AWS account\. We might issue you any refunds that are due through that same payment method\. If you have active subscriptions \(such as a Reserved Instance that you pay for monthly\), even after your account is closed, you might continue to be charged for the subscription through your designated payment method until the subscription expires or is sold according to the terms governing the subscription\. These charges and refunds might occur after you close your account\.

In addition, if you reopen your account, you might be charged for the cost of running AWS services \(that you didn't terminate before closing your account\) during the post\-closure period\. Closing your AWS account doesn't affect payment methods that you use on Amazon\.com or other Amazon websites\.

### On\-Demand charges<a name="on-demand-closure"></a>

During the post\-closure period, billing for On\-Demand charges stops\. However, you're billed for any usage that has accrued up until the time you closed your account\. You'll be charged for that usage at the beginning of the next month\. In addition, if you purchased any subscriptions with ongoing payment obligations, you might continue to be charged for them after your account is closed\.

**Important**  
You will continue to generate costs if you don't terminate your resources\.

### Domains registered with Amazon Route 53<a name="closure-domains"></a>

Domains that are registered with Route 53 are not deleted automatically\. When you're closing your AWS account, you have three options:
+ You can disable automatic renewal, and the domains are deleted when the registration period expires\. For more information, see [Enabling or Disabling Automatic Renewal for a Domain](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-enable-disable-auto-renewal.html) in the *Amazon Route 53 Developer Guide*\.
+ You can transfer the domains to another AWS account\. For more information, see [Transferring a Domain to a Different AWS Account](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-between-aws-accounts.html)\.
+ You can transfer the domains to another domain registrar\. For more information, see [Transferring a Domain from Route 53 to Another Registrar](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-transfer-from-route-53.html)\.

If you already closed the account, you can open a case with AWS Support to get help with disabling automatic renewal or transferring your domains\. For more information, see [Contacting AWS Support About Domain Registration Issues](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-contact-support.html)\. There is no charge to open a case for domain registration issues\.

### Charges if you reopen your AWS account<a name="reopen-charges"></a>

If you reopen your AWS account during the post\-closure period, you might be billed for the cost of any AWS services that are not terminated before you closed your account\.

#### Example<a name="reopen-charges-example"></a>

You reopen your AWS account 30 days after closure, and your AWS account had only an active `t-example.example` Amazon EC2 instance at closure\. The price for a `t-example.example` Amazon EC2 instance in your AWS Region is $0\.01 per hour\. In this case, you might be charged for 30 days x 24 hours x $0\.01 per hour = $7\.20 for your AWS services\.

### Closing a member account<a name="closing-member-account"></a>

When you close an account that was created with AWS Organizations, that account is not removed from the organization until after the post\-closure period\. During the post\-closure period, a closed member account still counts toward your limit of accounts in the organization\.

To avoid having the account count against the limit, remove member accounts from the organization before closing it\. For more information, see [Closing an AWS Account](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_close.html) in the *AWS Organizations User Guide*\.

### Cross\-account access to the account you’re closing<a name="cross-access"></a>

After you close your AWS account, any access requests to your closed account's AWS services from other AWS accounts fail\. This occurs even if you have granted the other accounts permission to access your account's AWS services\. If you reopen your AWS account, other AWS accounts can access your account's AWS services if you have granted the other accounts the necessary permissions\.

### Removing Amazon VPC peering connection<a name="vpc-peering"></a>

AWS currently does not delete Amazon VPC peering connections when you close one of the accounts participating in the VPC peering connection\. Any traffic destined for the VPC peering connection originating from other active accounts is dropped because AWS terminates instances and deletes any security groups in the closed account\. To remove the VPC peering connection, you can delete it from your account using the Amazon VPC console, AWS CLI, or Amazon EC2 API\.

## Troubleshooting errors when closing an AWS account<a name="troubleshooting-closing"></a>

If you receive an error message while trying to close your AWS account, you can contact your account representative or contact us to open a billing or account support case for assistance\. Common reasons why you might not be able to close your AWS account include the following:
+ Your account is the management account of an organization in AWS Organizations with open member accounts\.
+ You have unpaid invoices for your account\.
+ You have not signed in to the account as the root user\.
+ You are an active AWS Marketplace seller\.

## Closing your AWS account<a name="closing-the-account"></a>

You can close your AWS account using the following procedure\.<a name="closing-the-account-proc"></a>

**To close your AWS account**

1. [Sign in as the root user of the account](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html) that you want to close, using the email address and password that are associated with the account\. If you sign in as an AWS Identity and Access Management \(IAM\) user or role, you can't close an account\.

1. Open the Billing and Cost Management console at [https://console.aws.amazon.com/billing/home#/](https://console.aws.amazon.com/billing/home#/)\.

1. On the navigation bar in the upper\-right corner, choose your account name \(or alias\), and then choose **My Account**\.

1. On the **Account Settings** page, scroll to the end of the page to the **Close Account** section\. Read and ensure that you understand the text next to the check box\. After you close an AWS account, you can no longer use it to access AWS services\.

1. Select the check box to accept the terms, and then choose **Close Account**\.

1. In the confirmation box, choose **Close Account**\.

## Accessing your AWS account after closure<a name="accessing-after-closure"></a>

After you close an AWS account in accordance with the process above, you can no longer use it to access AWS services, but for 90 days after your account is closed \(the "Post\-Closure Period"\), you can view your AWS account's past billing information and access [AWS Support](https://console.aws.amazon.com/support/home)\.

During the Post\-Closure Period, AWS may retain any content that you didn't delete and any AWS services that you didn't terminate before you closed your AWS account\. You can access any remaining content or AWS services only by reopening your account during the Post\-Closure Period\. You can reopen your AWS account by contacting [AWS Support](https://console.aws.amazon.com/support/home)\. If you choose to reopen your account, you can access the content that you didn't delete and AWS services that you didn't terminate before closing your account, but you might be charged for the cost of running those AWS services during the Post\-Closure Period\. You can estimate the cost of running AWS services using the [AWS Pricing Calculator](https://docs.aws.amazon.com/pricing-calculator/latest/userguide/what-is-pricing-calculator.html) in the *AWS Pricing Calculator User Guide*\.

## After the post\-closure period<a name="post-closure-period"></a>

After the Post\-Closure Period, we permanently close your AWS account, and you can't reopen it\. Any content that you didn't delete is deleted, and any AWS services that you didn't terminate are terminated\. Service attributes can be retained as long as needed for billing and administration purposes\. You also can't create a new AWS account using the same alias or email address that was registered to your AWS account at the time of its closure\.