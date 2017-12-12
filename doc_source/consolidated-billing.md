# Consolidated Billing for Organizations<a name="consolidated-billing"></a>

You can use the consolidated billing feature in AWS Organizations to consolidate payment for multiple AWS accounts or multiple AISPL accounts\. With consolidated billing, you can see a combined view of AWS charges incurred by all of your accounts\. You also can get a cost report for each member account that is associated with your master account\. Consolidated billing is offered at no additional charge\. AWS and AISPL accounts can't be consolidated together\. For more information about organizations, see the [AWS Organizations User Guide](http://docs.aws.amazon.com/organizations/latest/userguide/)\.

If you previously signed up for consolidated billing on the AWS Billing and Cost Management console, your consolidated billing account family has been migrated automatically to a new organization in AWS Organizations\. This topic explains the similarities and differences between consolidated billing in Billing and Cost Management and in AWS Organizations\. Organizations gives you the same consolidated billing features of Billing and Cost Management, but also provides advanced features that give you more control over your accounts\.

When you used consolidated billing on the Billing and Cost Management console, you had one account that was designated as a payer account\. The payer account paid the charges that were accrued by all the other accounts, known as linked accounts, in your consolidated billing family\. The same idea applies to AWS Organizations: Each organization has one account, called a master account, that pays the charges of all the member accounts in that organization\. The member accounts are linked to the master account for billing purposes, just like the linked accounts in consolidated billing were linked to a payer account\.

AWS Organizations also provides the AWS Cost and Usage report that you can use to track the costs in your organization, just as you did for your consolidated billing family\. For example, you can see a combined view of AWS charges that are incurred by all accounts in the organization, and you can get a report for each member account\. The AWS Cost and Usage report is available at no additional charge\.

Consolidated billing has the following benefits:

+ **One Bill** – You get one bill for multiple accounts\.

+ **Easy Tracking** – You can easily track each account's charges and download the cost data in CSV format\.

+ **Combined Usage** – If you have multiple accounts today, your charges might decrease because AWS combines usage from all accounts in the organization to qualify you for volume pricing discounts\. For more information, see [Volume Discounts](useconsolidatedbilling-discounts.md)\.

**Note**  
If your contact address is in India, you can use AWS Organizations to consolidate Amazon Internet Services Pvt\. Ltd \(AISPL\) accounts within your organization\.


+ [Consolidated Billing Process](useconsolidatedbilling-procedure.md)
+ [Consolidated Billing in India](useconsolidatedbilling-India.md)
+ [Effective Billing Date](useconsolidatedbilling-effective.md)
+ [Billing and Account Activity](useconsolidatedbilling-activity.md)
+ [Volume Discounts](useconsolidatedbilling-discounts.md)
+ [AWS Credits](useconsolidatedbilling-credits.md)
+ [Reserved Instances](ri-behavior.md)
+ [Understanding Consolidated Bills](con-bill-blended-rates.md)
+ [AWS Support Charges for Accounts in an Organization](consolidatedbilling-support.md)