# Controlling access for Cost Explorer<a name="ce-access"></a>

You can manage access to your Cost Explorer in the following ways:
+ The management account can enable Cost Explorer at a root level, automatically enabling all member accounts\.
+ After member accounts are enabled, the management account can use the Cost Explorer settings to control the level of information you want to expose in Cost Explorer\. Levels of information can include cost, refunds or credits, discounts \(for example, reservation volume discounts, bundled discounts\), and Reserved Instance \(RI\) recommendations\.
+ After you enable Cost Explorer at the management account level, you can control the IAM policies of your IAM users to restrict access to Cost Explorer at the account level\. Users either get all access or no access with this option\.

This topic provides details about how to control access in Cost Explorer\.

For information about managing access to Billing and Cost Management pages, see [Overview of managing access permissions](control-access-billing.md)\. 

To reference Cost Explorer IAM policies, see [Using identity\-based policies \(IAM policies\) for Billing and Cost Management](billing-permissions-ref.md)\.

For more information about consolidated billing, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.

**Topics**
+ [Granting Cost Explorer access](#grant-ce-access)
+ [Controlling access using Cost Explorer preferences](#ce-controlling-access)
+ [Cost Explorer and IAM users](#ce-iam-users)

## Granting Cost Explorer access<a name="grant-ce-access"></a>

You can enable Cost Explorer access if you are signed into the management account with your root credentials through the Billing and Cost Management console\. Enabling Cost Explorer at the management account level enables Cost Explorer for all of your organization accounts\. All accounts in the organization are granted access, and you can't grant or deny access individually\.

## Controlling access using Cost Explorer preferences<a name="ce-controlling-access"></a>

A management account can grant access to Cost Explorer for all or none of the member accounts\. Access isn’t customizable for each individual member account\.

The management account in AWS Organizations has full access to all Billing and Cost Management information for costs incurred by both the management account and member accounts\. Member accounts only have access to their own cost and usage data in Cost Explorer\.

The owner of a management account can:
+ View all costs in Cost Explorer\.
+ Grant all member accounts the permission to see the costs for their own member account, refunds, credits, and RI recommendations\.

Member account owners can't see costs, refunds, and RI recommendations for other accounts in the Organizations\. For more information about consolidated billing, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.

If you're an AWS account owner and not using consolidated billing, you have full access to all Billing and Cost Management information including Cost Explorer\.

### Organizations account status use cases<a name="ce-ao-usecases"></a>

An account’s status with an organization affects what cost and usage data is visible in the following ways:
+ If a standalone account joins an organization, the account loses access to cost and usage data from when the account was a standalone account\.
+ If a member account leaves an organization and becomes a standalone account, the account no longer has access to cost and usage data from when the account was a member of their previous organization\. The account only has access to the data that is generated as a standalone account\.
+ If a member account leaves organization A to join organization B, the account no longer has access to cost and usage data from organization A\. The account has access only to the data that is generated as a member of organization B\.
+ If an account rejoins an organization that it previously belonged to, the account regains access to its historical cost and usage data\.

### Controlling member accounts’ access using Cost Explorer preferences<a name="ce-controlling-member-settings"></a>

You can grant or restrict the access to all member accounts in your Organizations\. When you enable your account at the management account level, all member accounts are granted access to their cost and usage data by default\.<a name="control-members-access"></a>

**To control member account access to Cost Explorer data**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the Cost Explorer page, choose **Launch Cost Explorer**\.

1. In the navigation pane, choose **Preferences**\.

1. On the **Preferences** page, select or clear the **Linked Account Access** check box\.

1. Choose **Save**\.

## Cost Explorer and IAM users<a name="ce-iam-users"></a>

After you enable Cost Explorer at the management account level, you can use IAM to manage access to your billing data for individual IAM users\. This enables you to grant or revoke access on an individual level for each account, rather than granting access to all member accounts\.

An IAM user must be granted explicit permission to view pages in the Billing and Cost Management console\. With the appropriate permissions, the IAM user can view costs for the AWS account that the IAM user belongs to\. For the policy that grants the necessary permissions to an IAM user, see [Overview of managing access permissions](control-access-billing.md)\. 