# Consolidated Billing for Organizations<a name="consolidated-billing"></a>

You can use the consolidated billing feature in AWS Organizations to consolidate billing and payment for multiple AWS accounts or multiple Amazon Internet Services Pvt\. Ltd \(AISPL\) accounts\. Every organization in AWS Organizations has a *master account* that pays the charges of all the *member accounts*\. For more information about organizations, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\. For the rest of this guide, the master account is called a payer account, and the member account is called a linked account, even when we talk about organizations\.

Consolidated billing has the following benefits:
+ **One bill** – You get one bill for multiple accounts\.
+ **Easy tracking** – You can track the charges across multiple accounts and download the combined cost and usage data\. 
+ **Combined usage** – You can combine the usage across all accounts in the organization to share the volume pricing discounts and Reserved Instance discounts\. This can result in a lower charge for your project, department, or company than with individual standalone accounts\. For more information, see [Volume Discounts](useconsolidatedbilling-discounts.md)\.
+ **No extra fee** – Consolidated billing is offered at no additional cost\. 

**Note**  
The linked account bills are for informational purpose only\. The payer account might reallocate the additional volume discounts and Reserved Instance discounts that your account receives\. 

If you have access to the payer account, you can see a combined view of the AWS charges that the linked accounts incur\. You also can get a cost report for each linked account\.

AWS and AISPL accounts can't be consolidated together\. If your contact address is in India, you can use AWS Organizations to consolidate AISPL accounts within your organization\.

**Important**  
When a linked account leaves an organization, the linked account can no longer access Cost Explorer data that was generated when the account was in the organization\. The data isn't deleted, and the payer account in the organization can still access the data\. If the linked account rejoins the organization, the linked account can access the data again\.

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