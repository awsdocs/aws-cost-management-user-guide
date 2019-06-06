# Closing an Account<a name="close-account"></a>

If you no longer need your AWS account, the root user of the account can close it\. AWS can't close accounts on your behalf\. 

**Topics**
+ [Before You Close Your AWS Account](#before-closing)
+ [Closing Your AWS Account](#closing-the-account)
+ [Accessing Your AWS Account after Closure](#accessing-after-closure)
+ [After the Post\-Closure Period](#post-closure-period)
+ [Your Payment Method](#closure-payment)
+ [Your Agreement with AWS](#closure-agreement)
+ [AWS Account Closure FAQ](account-closure-faq.md)

## Before You Close Your AWS Account<a name="before-closing"></a>

Before closing your AWS account, you must pay all of the invoices for your account\. If your account is the master account of an AWS organization, you must also close or unlink all member accounts\.

In addition, you should retrieve all of your content from the account, including any applications and data that you will need later\. For instructions on how to retrieve content from a particular AWS service, see the [ documentation for that service](https://docs.aws.amazon.com/)\. You should then delete any content and terminate all AWS services in your account\.

## Closing Your AWS Account<a name="closing-the-account"></a><a name="closing-the-account-proc"></a>

**To close your AWS account**

1. [Sign in as the root user of the account](https://docs.aws.amazon.com/general/latest/gr/aws_tasks-that-require-root.html) that you want to close, using the email address and password that are associated with the account\. If you sign in as an IAM user or role, you can't close an account\.
**Note**  
 We recommend that member accounts that you create with AWS Organizations leave the organization before you close them\. Otherwise, the closed account counts toward the limit on the number of accounts that the organization can have\. By default, member accounts that you create with AWS Organizations don't have a password associated with the account's root user\. To close a member account, the member account must leave the organization and request a password change\. For more information, see [Closing an AWS Account](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_close.html) in the *AWS Organizations User Guide*\. 

1. Open the Billing and Cost Management console at [https://console.aws.amazon.com/billing/home#/](https://console.aws.amazon.com/billing/home#/)\.

1. On the navigation bar in the upper\-right corner, choose your account name \(or alias\) and then choose **My Account**\.

1. On the **Account Settings** page, scroll to the end of the page to the **Close Account** section\. Read and ensure that you understand the text next to the check box\. After you close an AWS account, you can no longer use it to access AWS services\.

1. Select the check box to accept the terms and then choose **Close Account**\.

1. In the confirmation box, choose **Close Account**\.

## Accessing Your AWS Account after Closure<a name="accessing-after-closure"></a>

After you close an AWS account in accordance with the process above, you can no longer use it to access AWS services, but for 90 days after your account is closed \(the "Post\-Closure Period"\), you can view your AWS account's past billing information and access [AWS Support](https://console.aws.amazon.com//support/home)\.

During the Post\-Closure Period, AWS may retain any content that you didn't delete and any AWS services that you didn't terminate before you closed your AWS account\. You can access any remaining content or AWS services only by reopening your account during the Post\-Closure Period\. You can reopen your AWS account by contacting [AWS Support](https://console.aws.amazon.com//support/home)\. If you choose to reopen your account, you can access the content that you didn't delete and AWS services that you didn't terminate before closing your account, but you might be charged for the cost of running those AWS services during the Post\-Closure Period\. You can estimate the cost of running AWS services using the [AWS Simple Monthly Calculator](http://calculator.s3.amazonaws.com/calc5.html)\.

## After the Post\-Closure Period<a name="post-closure-period"></a>

After the Post\-Closure Period, we permanently close your AWS account, and you can't reopen it\. Any content that you didn't delete is deleted, and any AWS services that you didn't terminate are terminated\. You also can't create a new AWS account using the same email address that was registered to your AWS account at the time of its closure\.

## Your Payment Method<a name="closure-payment"></a>

We charge you through your designated payment method for any usage fees incurred before you closed your AWS account, and we might issue you any refunds that are due through that same payment method\. In addition, if you have any active subscriptions \(such as a Reserved Instance for which you have elected to pay in monthly installments\), even after your account is closed, you might continue to be charged for the subscription through your designated payment method until the subscription expires or is sold in accordance with the terms governing the subscription\. These charges and refunds might occur after you close your account\. In addition, if you reopen your account, you might be charged for the cost of running AWS services \(that you didn't terminate before closing your account\) during the Post\-Closure Period\. Closing your AWS account doesn't affect payment methods that you use on Amazon\.com or other Amazon websites\.

## Your Agreement with AWS<a name="closure-agreement"></a>

Your closure of your AWS account serves as notice to us that you want to terminate the AWS Customer Agreement or other agreement with AWS that governs that AWS account, solely with respect to that AWS account\. If you reopen your AWS account during the Post\-Closure Period, you agree that the same agreement terms will govern your access to and use of the Service Offerings through your reopened AWS account\.