# Consolidated billing process<a name="useconsolidatedbilling-procedure"></a>

AWS Organizations provides consolidated billing so that you can track the combined costs of all the member accounts in your organization\. The following steps provide an overview of the process for creating an organization and viewing your consolidated bill\.

1. Open the [AWS Organizations console](https://console.aws.amazon.com/organizations/) or the [AWS Billing and Cost Management console](https://console.aws.amazon.com/billing/)\. If you open the AWS Billing and Cost Management console, choose **Consolidated Billing**, and then choose **Get started**\. You are redirected to the AWS Organizations console\.

1. Choose **Create organization** on the AWS Organizations console\.

1. Create an organization from the account that you want to be the management account of your new organization\. For details, see [Creating an Organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_create.html)\. The management account is responsible for paying the charges of all the member accounts\.

1. \(Optional\) Create accounts that are automatically member to the organization\. For details, see [ Creating an AWS Account in Your Organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_create.html)\.

1. \(Optional\) Invite existing accounts to join your organization\. For details, see [ Inviting an AWS Account to Join Your Organization](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_accounts_invites.html)\.

1. Each month AWS charges your management account for all the member accounts in a consolidated bill\. The following illustration shows an example of a consolidated bill\.

![\[Consolidated bill for an organization's management account\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/BillingBitsOfOrganizations.png)

The management account is billed for all charges of the member accounts\. However, unless the organization is changed to support all features in the organization \(not consolidated billing features only\) and member accounts are explicitly restricted by policies, each member account is otherwise independent from the other member accounts\. For example, the owner of a member account can sign up for AWS services, access resources, and use AWS Premium Support unless the management account restricts those actions\. Each account owner continues to use their own IAM user name and password, with account permissions assigned independently of other accounts in the organization\.

**Securing the consolidated billing management account**  
The owner of the management account in an organization should secure the account by using [AWS Multi\-Factor Authentication](https://aws.amazon.com/mfa/) and a strong password that has a minimum of eight characters with both uppercase and lowercase letters, at least one digit, and at least one special character\. You can change your password on the [AWS Security Credentials](https://aws.amazon.com/security-credentials) page\.