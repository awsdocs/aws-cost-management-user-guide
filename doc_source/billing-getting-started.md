# Getting started<a name="billing-getting-started"></a>

This section provides information that you need to get started with using the Billing console\.

**Topics**
+ [Sign up for AWS and create an IAM user](#billing-gs-review)
+ [Review your bills and usage](#step-3)
+ [Step 4: Download or print your bill](#billing-gs-download)
+ [Step 5: Learn more about the Billing features](#billing-gs-features)
+ [What do I do next?](#what-next)

## Sign up for AWS and create an IAM user<a name="billing-gs-review"></a>

If you're new to AWS, create an AWS account\. For more information, see [Getting Started with AWS](http://aws.amazon.com/getting-started/)\.

### Sign up for an AWS account<a name="sign-up-for-aws"></a>

If you do not have an AWS account, complete the following steps to create one\.

**To sign up for an AWS account**

1. Open [https://portal\.aws\.amazon\.com/billing/signup](https://portal.aws.amazon.com/billing/signup)\.

1. Follow the online instructions\.

   Part of the sign\-up procedure involves receiving a phone call and entering a verification code on the phone keypad\.

   When you sign up for an AWS account, an *AWS account root user* is created\. The root user has access to all AWS services and resources in the account\. As a security best practice, [assign administrative access to an administrative user](https://docs.aws.amazon.com/singlesignon/latest/userguide/getting-started.html), and use only the root user to perform [tasks that require root user access](https://docs.aws.amazon.com/accounts/latest/reference/root-user-tasks.html)\.

AWS sends you a confirmation email after the sign\-up process is complete\. At any time, you can view your current account activity and manage your account by going to [https://aws\.amazon\.com/](https://aws.amazon.com/) and choosing **My Account**\.

### Create an administrative user<a name="create-an-admin"></a>

After you sign up for an AWS account, create an administrative user so that you don't use the root user for everyday tasks\.

**Secure your AWS account root user**

1.  Sign in to the [AWS Management Console](https://console.aws.amazon.com/) as the account owner by choosing **Root user** and entering your AWS account email address\. On the next page, enter your password\.

   For help signing in by using root user, see [Signing in as the root user](https://docs.aws.amazon.com/signin/latest/userguide/console-sign-in-tutorials.html#introduction-to-root-user-sign-in-tutorial) in the *AWS Sign\-In User Guide*\.

1. Turn on multi\-factor authentication \(MFA\) for your root user\.

   For instructions, see [Enable a virtual MFA device for your AWS account root user \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_enable_virtual.html#enable-virt-mfa-for-root) in the *IAM User Guide*\.

**Create an administrative user**
+ For your daily administrative tasks, grant administrative access to an administrative user in AWS IAM Identity Center \(successor to AWS Single Sign\-On\)\.

  For instructions, see [Getting started](https://docs.aws.amazon.com/singlesignon/latest/userguide/getting-started.html) in the *AWS IAM Identity Center \(successor to AWS Single Sign\-On\) User Guide*\.

**Sign in as the administrative user**
+ To sign in with your IAM Identity Center user, use the sign\-in URL that was sent to your email address when you created the IAM Identity Center user\.

  For help signing in using an IAM Identity Center user, see [Signing in to the AWS access portal](https://docs.aws.amazon.com/signin/latest/userguide/iam-id-center-sign-in-tutorial.html) in the *AWS Sign\-In User Guide*\.

## Review your bills and usage<a name="step-3"></a>

Use features in the Billing console to view your current AWS charges and AWS usage\.

**To open the Billing console and view your usage and charges**

1. Sign into the AWS Management Console and open the Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Choose **Bills** to see details about your current charges\.

   Choose **Payments** to see your historical payment transactions\.

   Choose **AWS Cost and Usage Reports** to see reports that break down your costs\.

For more information about setting up and using AWS Cost and Usage Reports, see the [AWS Cost and Usage Reports User Guide](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.

## Step 4: Download or print your bill<a name="billing-gs-download"></a>

AWS Billing closes the billing period at midnight on the last day of each month and calculates your bill\. Most bills are ready for you to download by the seventh accounting day of the month\.

**To download your bill**

1. Sign into the AWS Management Console and open the Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\. 

1. On the navigation pane, choose **Bills**\.

1. For **Date**, choose the month of the bill you want to work with\.

1. Choose **Download CSV** to download a comma\-separated variable file or choose **Print**\.

## Step 5: Learn more about the Billing features<a name="billing-gs-features"></a>

Understand the features available to you in the Billing console\.
+ **Account settings**: [Managing your account](change-account-settings.md)
+ **AWS Free Tier**: [Using the AWS Free Tier](billing-free-tier.md)
+ **Payments**: [Managing your payments](manage-payments.md)
+ **Viewing your bills**: [Viewing your bill](getting-viewing-bill.md)
+ **AWS Cost Categories**: [Managing your costs with AWS Cost Categories](manage-cost-categories.md)
+ **Cost Allocation Tags**: [Using AWS cost allocation tags](cost-alloc-tags.md)
+ **AWS Purchase Orders**: [Managing your purchase orders](manage-purchaseorders.md)
+ **AWS Cost and Usage Reports**: [Using AWS Cost and Usage Reports](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)
+ **Using AWS CloudTrail**: [Logging Billing and Cost Management API calls with AWS CloudTrail](logging-using-cloudtrail.md)
+ **Consolidated billing**: [Consolidated billing for AWS Organizations](consolidated-billing.md)

## What do I do next?<a name="what-next"></a>

Now that you can view and pay your AWS bill, you're ready to use the features available to you\. The rest of this guide helps you navigate your journey using the console\.

### Optimize your spending using AWS Cost Management features<a name="Billing-CMG"></a>

Use the AWS Cost Management features to budget and forecast costs so you can optimize your AWS spends and reduce your overall AWS bill\. Combine and use the Billing console resources to manage your payments, while using AWS Cost Management features to optimize your future costs\.

For more information about AWS Cost Management features, see the [AWS Cost Management User Guide](https://docs.aws.amazon.com/cost-management/latest/userguide/what-is-costmanagement.html)\.

### Using the Billing and Cost Management API<a name="Billing-API"></a>

Use the [AWS Billing and Cost Management API Reference](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/Welcome.html) to programmatically use some AWS Cost Management features\.

### Learn more<a name="Billing-tutorials"></a>

You can find more information about Billing features including presentations, virtual workshops, and blog posts on the marketing page [Cloud Financial Management with AWS](http://aws.amazon.com/aws-cost-management/)\.

You can find virtual workshops by choosing the **Services** drop\-down and selecting your feature\.

### Get help<a name="Billing-gethelp"></a>

If you have questions about any Billing features, there are many resources available for you\. To learn more, see [Getting help with AWS Billing](billing-get-answers.md)\.