# Controlling Access for Cost Explorer<a name="cost-explorer-access"></a>

How you manage access to the information in Cost Explorer depends on how your AWS account is set up\. Your account might be set up to use the AWS Identity and Access Management \(IAM\) service to grant different levels of access to different IAM users\. Your account might be part of consolidated billing in AWS Organizations, in which case it is either a *master account* or a *member account*\. For information about managing access to Billing and Cost Management pages, see [Controlling Access](control-access-billing.md) For more information about consolidated billing, see [Consolidated Billing for Organizations](consolidated-billing.md)\.

## Granting Cost Explorer Access<a name="whocanenable"></a>

You can enable Cost Explorer only if you are the owner of the AWS account and you signed in to the account with your root credentials\. If you are the owner of a master account in an organization, enabling Cost Explorer enables Cost Explorer for all the organization accounts\. In other words, all member accounts in the organization are also granted access\. You can't grant or deny access individually\.

## Cost Explorer and IAM Users<a name="howusertypes"></a>

An AWS account owner who is not using consolidated billing has full access to all Billing and Cost Management information, including Cost Explorer\. After you enable Cost Explorer, you should interact with Cost Explorer as an IAM user\. If you have permission to view the Billing and Cost Management console, you can use Cost Explorer\. 

An IAM user must be granted explicit permission to view pages in the Billing and Cost Management console\. With the appropriate permissions, the IAM user can view costs for the AWS to which the IAM user belongs\. For the policy that grants the necessary permissions to an IAM user, see [Controlling Access](control-access-billing.md)\. 

### Consolidated Billing Considerations<a name="cbconsiderations"></a>

The owner of the master account in an organization has full access to all Billing and Cost Management information for costs incurred by the master account and by member accounts, and can view all costs in Cost Explorer\. The owner of a member account in an organization can see costs for the member account, but can't see costs for any other account in the organization\. For more information, see [Consolidated Billing for Organizations](consolidated-billing.md)\.