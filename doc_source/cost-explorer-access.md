# Controlling Access for Cost Explorer<a name="cost-explorer-access"></a>

How you manage access to the information in Cost Explorer depends on how your AWS account is set up\. Your account might be set up to use the AWS Identity and Access Management \(IAM\) service to grant different levels of access to different IAM users\. Your account might be part of consolidated billing in AWS Organizations, in which case it is either a *master account* or a *member account*\. For information about managing access to Billing and Cost Management pages, see [Controlling Access](control-access-billing.md)\. For more information about consolidated billing, see [Consolidated Billing for Organizations](consolidated-billing.md)\.

## Granting Cost Explorer Access<a name="whocanenable"></a>

You can enable Cost Explorer only if you're the owner of the AWS account and you signed in to the account with your root credentials\. If you're the owner of a master account in an organization, enabling Cost Explorer enables Cost Explorer for all of the organization accounts\. In other words, all member accounts in the organization are also granted access\. You can't grant or deny access individually\.

## Cost Explorer and IAM Users<a name="howusertypes"></a>

An AWS account owner who isn't using consolidated billing has full access to all Billing and Cost Management information, including Cost Explorer\. After you enable Cost Explorer, you should interact with Cost Explorer as an IAM user\. If you have permission to view the Billing and Cost Management console, you can use Cost Explorer\. 

An IAM user must be granted explicit permission to view pages in the Billing and Cost Management console\. With the appropriate permissions, the IAM user can view costs for the AWS account that the IAM user belongs to\. For the policy that grants the necessary permissions to an IAM user, see [Controlling Access](control-access-billing.md)\. 

## Cost Explorer and Consolidated Billing<a name="cbconsiderations"></a>

The owner of the payer \(master\) account in an AWS Organizations organization has full access to all Billing and Cost Management information for costs incurred by the master account and by linked \(member\) accounts, and can view all costs in Cost Explorer\. The owner of a payer account can also grant linked accounts the permissions to see the costs for the linked account, refunds and credits, and RI recommendations\. Owners of a linked account can't see the costs, refunds, or RI recommendations for any other account in the organization\. For more information about consolidated billing, see [Consolidated Billing for Organizations](consolidated-billing.md)\.

### Granting Owners of a Member Account Access to Cost Explorer Data<a name="cb-granted-members-access"></a>

You can grant or restrict the access that a linked account has to some of the information from Cost Explorer\. <a name="grant-members-access"></a>

**To grant the owner of a linked account access to Cost Explorer data**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the Cost Explorer page, choose **Launch Cost Explorer**\.

1. On the Cost Explorer dashboard, choose **Settings** on the top right\.

1. On the **Settings** page, select the data categories that you want your member accounts to have access to\.

1. Choose **Save**\.

**Note**  
An account’s status with an organization affects what cost and usage data is visible:  
When a standalone account joins an organization, the account no longer has access to cost and usage data from the time range when the account was a standalone account\.
If a member account leaves an organization and becomes a standalone account, the account no longer has access to cost and usage data from the time range when the account was a member of the organization\. The account has access only to the data that is generated as a standalone account\. 
If a member account leaves organization A to join organization B, the account no longer has access to cost and usage data from the time range when the account was a member of organization A\. The account has access only to the data that is generated as a member of organization B\. 
If an account rejoins an organization that it previously belonged to, the account regains access to its historical cost and usage data\.