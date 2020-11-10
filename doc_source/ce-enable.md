# Enabling Cost Explorer<a name="ce-enable"></a>

You can enable Cost Explorer for your account using this procedure on the Billing and Cost Management console\. You can't enable Cost Explorer using the API\. After you enable Cost Explorer, AWS prepares the data about your costs for the current month and the last 12 months, and then calculates the forecast for the next 12 months\. The current month's data is available for viewing in about 24 hours\. The rest of your data takes a few days longer\. Cost Explorer updates your cost data at least once every 24 hours\.

By default, you can launch Cost Explorer if your account is a member account in an organization\. The management account can, however, block your access\. For more information, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.

**Note**  
An account’s status with an organization affects what cost and usage data is visible:  
When a standalone account joins an organization, the account no longer has access to cost and usage data from the time range when the account was a standalone account\.
If a member account leaves an organization and becomes a standalone account, the account no longer has access to cost and usage data from the time range when the account was a member of the organization\. The account has access only to the data that is generated as a standalone account\. 
If a member account leaves organization A to join organization B, the account no longer has access to cost and usage data from the time range when the account was a member of organization A\. The account has access only to the data that is generated as a member of organization B\. 
If an account rejoins an organization that it previously belonged to, the account regains access to its historical cost and usage data\.

Signing up to receive the AWS Cost and Usage Reports or the Detailed Billing Report doesn't automatically enable Cost Explorer\. You must still enable it by performing the following procedure\.

**To sign up for Cost Explorer**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation pane, choose **Cost Explorer**\.

1. On the **Welcome to Cost Explorer** page, choose **Launch Cost Explorer**\. 

For more information about controlling access to Cost Explorer, see [Controlling access for Cost Explorer](ce-access.md)\. 