# AWS Identity and Access Management for AWS Billing and Cost Management<a name="security-iam"></a>

AWS Identity and Access Management \(IAM\) is an AWS service that helps an administrator securely control access to AWS resources\. IAM administrators control who can be *authenticated* \(signed in\) and *authorized* \(have permissions\) to use Billing and Cost Management resources\. IAM is an AWS service that you can use with no additional charge\.

To start activating access to the Billing console, first see [Tutorial: Delegate Access to the Billing Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_billing.html) in the *IAM User Guide*\.

**Topics**
+ [Audience](#security_iam_audience)
+ [Overview of managing access permissions](control-access-billing.md)
+ [Using identity\-based policies \(IAM policies\) for Billing and Cost Management](billing-permissions-ref.md)
+ [Billing and Cost Management policy examples](billing-example-policies.md)

## Audience<a name="security_iam_audience"></a>

How you use IAM differs, depending on the work you do in Billing and Cost Management\.

**Service user** – If you use the Billing and Cost Management service to do your job, then your administrator provides you with the credentials and permissions that you need\. As you use more Billing and Cost Management features to do your work, you might need additional permissions\. Understanding how access is managed can help you request the right permissions from your administrator\.

**Service administrator** – If you're in charge of Billing and Cost Management resources at your company, you probably have full access to Billing and Cost Management\. It's your job to determine which Billing and Cost Management features and resources your employees should access\. You must then submit requests to your IAM administrator to change the permissions of your service users\. Review the information on this page to understand the basic concepts of IAM\.

**IAM administrator** – If you're an IAM administrator, you might want to learn details about how you can write policies to manage access to Billing and Cost Management\.

This table summarizes the default actions that are permitted in Billing and Cost Management for each type of billing user\.


**User types and billing permissions**  

| User type | Description | Billing permissions | 
| --- | --- | --- | 
| Account owner |  The person or entity in whose name your account is set up as\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 
| IAM user |  A person or application defined as a user in an account by an account owner or administrative user\. Accounts can contain multiple IAM users\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 
| Organization management account owner |  The person or entity associated with an AWS Organizations management account\. The management account pays for AWS usage that is incurred by a member account in an organization\.   |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 
| Organization member account owner |  The person or entity associated with an AWS Organizations member account\. The management account pays for AWS usage that is incurred by a member account in an organization\.   |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 