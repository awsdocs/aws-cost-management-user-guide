# Consolidated Billing for Organizations<a name="consolidated-billing"></a>

You can use the consolidated billing feature in AWS Organizations to consolidate payment for multiple AWS accounts or multiple AISPL accounts\. Each organization in AWS Organizations has a *master account* that pays the charges of all the *member accounts*\. If you have access to the master account, you can see a combined view of the AWS charges that are incurred by the member accounts\. You also can get a cost report for each member account\. For more information about organizations, see the [AWS Organizations User Guide](http://docs.aws.amazon.com/organizations/latest/userguide/)\.

Consolidated billing has the following benefits:
+ **One bill** – You get one bill for multiple accounts\.
+ **Easy tracking** – You can track each account's charges, and download the cost data in \.csv format\.
+ **Combined usage** – If you have multiple standalone accounts, your charges might decrease if you add the accounts to an organization\. AWS combines usage from all accounts in the organization to qualify you for volume pricing discounts\. For more information, see [Volume Discounts](useconsolidatedbilling-discounts.md)\.
+ **No extra fee** – Consolidated billing is offered at no additional cost\. 

AWS and AISPL accounts can't be consolidated together\. If your contact address is in India, you can use AWS Organizations to consolidate Amazon Internet Services Pvt\. Ltd \(AISPL\) accounts within your organization\.

**Important**  
When a member account leaves an organization, the member account can no longer access Cost Explorer data that was generated when the account was in the organization\. The data is not deleted, and the master account in the organization can still access the data\. If the member account rejoins the organization, the member account can access the data again\.

**Topics**
+ [Consolidated Billing Process](useconsolidatedbilling-procedure.md)
+ [Consolidated Billing in India](useconsolidatedbilling-India.md)
+ [Effective Billing Date](useconsolidatedbilling-effective.md)
+ [Billing and Account Activity](useconsolidatedbilling-activity.md)
+ [Volume Discounts](useconsolidatedbilling-discounts.md)
+ [AWS Credits](useconsolidatedbilling-credits.md)
+ [Reserved Instances](ri-behavior.md)
+ [Understanding Consolidated Bills](con-bill-blended-rates.md)
+ [AWS Support Charges for Accounts in an Organization](consolidatedbilling-support.md)