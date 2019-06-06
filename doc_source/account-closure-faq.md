# AWS Account Closure FAQ<a name="account-closure-faq"></a>

This FAQ guides you through the changes\.

**Topics**
+ [Q: I received an error message when I tried to close my AWS account\. What do I need to do?](#closure-question-1)
+ [Q: What happens when I close my AWS account?](#closure-question-2)
+ [Q: What could I be charged if I reopen my AWS account?](#closure-question-3)
+ [Q: Does closing a member account remove it from my organization?](#closure-question-4)
+ [Q: Are you retaining my content after I close my account?](#closure-question-5)
+ [Q: I have granted other AWS accounts access to my account's AWS services\. Can they access my AWS services after I have closed my account?](#closure-question-6)

## Q: I received an error message when I tried to close my AWS account\. What do I need to do?<a name="closure-question-1"></a>

If you receive an error message while trying to close your AWS account, you can contact your account representative or [contact us](https://aws.amazon.com/contact-us/) to open a billing or account support case for assistance\. Common reasons why you might not be able to close your AWS account include the following:
+ Your account is the master account of an AWS organization with open member accounts\.
+ You have unpaid invoices for your account\.
+ You have not signed in to the account as the root user\.
+ You are an active AWS Marketplace Seller\. 

## Q: What happens when I close my AWS account?<a name="closure-question-2"></a>

When you close your AWS account, the following things happen:
+ Your access to the AWS Management Console for the closed AWS account is restricted\. You can still sign in to your AWS account to view your past billing information and access AWS Support during the Post\-Closure Period\. You can't access any other AWS services or start any new AWS services in the closed account\.
+ Any remaining content and unterminated AWS services in your AWS account is deleted and terminated after the Post\-Closure Period\. You should retrieve all content from your AWS account before closing your AWS account\. For instructions on how to retrieve your content, see [ documentation for that service](https://docs.aws.amazon.com/)\.
+ Billing for on\-demand charges stops, but you're billed for any usage that has accrued up until the time you closed your account, and you're charged for that usage at the beginning of the next month\. In addition, if you purchased any subscriptions with ongoing payment obligations, you might continue to be charged for them after your account is closed\.

## Q: What could I be charged if I reopen my AWS account?<a name="closure-question-3"></a>

If you reopen your AWS account during the Post\-Closure Period, you might be billed for the cost of any AWS services not terminated before you closed your account\. For example, if you reopen your AWS account 30 days after closure, your AWS account had only an active t\-example\.example Amazon EC2 instance at closure, and the price for a t\-example\.example Amazon EC2 instance in your region is $0\.01 per hour, you might be charged for 30 days x 24 hours x $0\.01 per hour = $7\.20 for your AWS services\. 

## Q: Does closing a member account remove it from my organization?<a name="closure-question-4"></a>

Closing an account removes it from an organization after the Post\-Closure Period\. Until then, a closed member account in an organization still counts toward your limit of accounts in the organization\. You can remove an account from an organization to avoid it counting against the limit\.

## Q: Are you retaining my content after I close my account?<a name="closure-question-5"></a>

We don't retain any content that you delete before account closure, but we might not delete your content during the Post\-Closure Period\. After the Post\-Closure Period, any remaining content in your account is deleted\. If you want to delete your content before that time, you should delete your content before closing your account\. 

## Q: I have granted other AWS accounts access to my account's AWS services\. Can they access my AWS services after I have closed my account?<a name="closure-question-6"></a>

No\. After you close your AWS account, any access requests to your closed account's AWS services from other AWS accounts fail even if you have granted the other accounts permission to access your account's AWS services\. If you reopen your AWS account, other AWS accounts can access your account's AWS services if you have granted the other accounts the necessary permissions