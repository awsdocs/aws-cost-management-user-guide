# AWS Identity and Access Management for AWS Billing<a name="security-iam"></a>

AWS Identity and Access Management \(IAM\) is an AWS service that helps an administrator securely control access to AWS resources\. IAM administrators control who can be *authenticated* \(signed in\) and *authorized* \(have permissions\) to use Billing resources\. IAM is an AWS service that you can use with no additional charge\.

To start activating access to the Billing console, see [Tutorial: Delegate Access to the Billing Console](https://docs.aws.amazon.com/IAM/latest/UserGuide/tutorial_billing.html) in the *IAM User Guide*\.

**Topics**
+ [Audience](#security_iam_audience)
+ [Overview of managing access permissions](control-access-billing.md)
+ [Using identity\-based policies \(IAM policies\) for AWS Billing](billing-permissions-ref.md)
+ [AWS Billing policy examples](billing-example-policies.md)

## Audience<a name="security_iam_audience"></a>

How you use IAM differs, depending on the work you do in AWS Billing\.

**Service user** – If you use the AWS Billing service to do your job, your administrator provides you with the credentials and permissions that you need\. As you use more Billing and Cost Management features, you might need additional permissions\. Understanding how access is managed helps you request the right permissions from your administrator\.

**Service administrator** – If you're in charge of AWS Billing resources, you probably have full access to AWS Billing\. You're responsible to determine which AWS Billing features and resources employees access\. You're also responsible for submitting requests to your IAM administrator to change the permissions of your service users\. Review the information on this page to understand the basic concepts of IAM\.

**IAM administrator** – If you're an IAM administrator, you might want to learn more about how you can write policies to manage access to AWS Billing\.

This table summarizes the default actions that are permitted in AWS Billing for each type of billing user\.


**User types and billing permissions**  

| User type | Description | Billing permissions | 
| --- | --- | --- | 
| Account owner |  The person or entity that your account is set up under\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 
| IAM user |  A person or application that's defined as a user in an account by an account owner or administrative user\. Accounts can contain multiple IAM users\.  |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 
| Organization management account owner |  The person or entity that's associated with an AWS Organizations management account\. The management account pays for AWS usage that's incurred by a member account in an organization\.   |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 
| Organization member account owner |  The person or entity that's associated with an AWS Organizations member account\. The management account pays for AWS usage that's incurred by a member account in an organization\.   |  [\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/security-iam.html)  | 