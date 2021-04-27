# Managing an AWS account<a name="manage-account-payment"></a>

You can use the Billing and Cost Management console to change account settings, including your contact and alternate contact information, the currency that you pay your bills in, the Regions that you can create resources in, and your tax registration numbers\.

**Note**  
Some sections can only be edited by the AWS account root user\. If you do not see the **Edit** option, switch to the root user\.

**Topics**
+ [Editing Your Account name, root user password, and root user email address](#manage-account-payment-edit-user-name)
+ [Editing contact information](#manage-account-payment-edit-contacts)
+ [Changing which currency you use to pay your bill](#manage-account-payment-change-currency)
+ [Adding, changing, or removing alternate contacts](#manage-account-payment-alternate-contacts)
+ [Enabling and disabling regions](#manage-account-payment-enable-disable-regions)
+ [Updating and deleting tax registration numbers](#manage-account-payment-update-delete-tax-numbers)
+ [Enabling tax setting inheritance](#manage-account-tax-linked-accounts)

## Editing Your Account name, root user password, and root user email address<a name="manage-account-payment-edit-user-name"></a>

To edit your account name, root user password, or email address, perform the following procedure\. Email in this case refers to the AWS account root user email address\. This is the email address you use to sign in\.<a name="account-info"></a>

**To edit your account name, root user password, or root user email address**

1. Sign in to the **Account Settings** page in the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home?\#/account](https://console.aws.amazon.com/billing/home?#/account)\.

   You can also find this by signing into the Billing and Cost Management console \([https://console\.aws\.amazon\.com/billing/home](https://console.aws.amazon.com/billing/home?#/account)\), selecting your account name on the top right, and choosing **My account**\. 

1. On the **Account Settings** page, next to **Account Settings**, choose **Edit**\.

1. Next to the field to update, choose **Edit**\.

1. After you have entered your changes, choose **Save changes**\.

1. After you have made all of your changes, choose **Done**\.

## Editing contact information<a name="manage-account-payment-edit-contacts"></a>

You can change the contact information associated with your account, including your mailing address, telephone number, and website address\. To edit your contact information, perform the following procedure\.<a name="contact-info"></a>

**To edit your contact information**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Under **Contact Information**, choose **Edit**\.

1. For the fields to change, enter your updated information and then choose **Update**\.

**Note**  
You can add an email address for billing in the **Alternate Contacts** section to have AWS send a copy of billing\-related emails to that email address\. For example, AWS sends your **Billing contact address** a message that your monthly bill is ready\.

## Changing which currency you use to pay your bill<a name="manage-account-payment-change-currency"></a>

To change the currency that you use to pay your bill, for example, from Danish kroner to South African rand, perform the following procedure\.<a name="local-currency"></a>

**To change the local currency associated with your account**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Scroll down to the **Payment Currency Preference** section\. Next to **Payment Currency Preference**, choose **Edit**\.

1. For **Select Payment Currency**, select the currency to pay your bill in and then choose **Update**\.

## Adding, changing, or removing alternate contacts<a name="manage-account-payment-alternate-contacts"></a>

Alternate contacts enable AWS to contact another person about issues with your account, even if you're unavailable\. The alternate contact doesn't have to be a specific person\. You could instead add an email distribution list if you have a team that is responsible for managing billing, operations and security related issues\. To add, change, or delete alternate contacts for your account, perform the following procedure\.<a name="account-contacts"></a>

**To add, update, or remove alternate contacts**



1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Scroll down to the **Alternate Contacts** section and choose **Edit**\.

1. For the fields to change, enter your updated information and choose **Update**\.

### Examples for alternate contacts<a name="manage-account-payment-alternate-contacts-example"></a>

We would reach out to each contact type in the following scenarios:
+ **Billing** \- When your monthly invoice is available, or your payment method needs to be updated\. If your **Receive PDF Invoice By Email** is turned on in your **Billing preferences**, your alternate billing contact will receive the PDF invoices as well\.
+ **Operations** \- When your service is, or will be, temporarily unavailable in one of more Regions\. Any notification related to operations\.
+ **Security** \- When you have notifications from the AWS Abuse team for potentially fraudulent activity on your AWS account\. Any notification related to security\.

## Enabling and disabling regions<a name="manage-account-payment-enable-disable-regions"></a>

AWS originally enabled all new Regions by default, which enabled your users to create resources in any Region\. Now when AWS adds a Region, the new Region is disabled by default\. If you want your users to be able to create resources in a new Region, you enable the Region\.

Note the following about enabling and disabling Regions:

**You can use IAM permissions to control access to Regions**  
IAM added three new permissions, which let you control which users can enable, disable, and list Regions\. For more information, see [Billing and Cost Management actions policies](billing-permissions-ref.md#user-permissions)\.

**Enabling a Region is free**  
There is no charge to enable a Region\. You're only charged for resources that you create in the new Region\.

**Disabling a Region disables access to resources in the Region**  
If you disable a Region that still includes AWS resources, such as Amazon EC2 instances, you can't access the resources in that Region\. For example, you can't use the AWS Management Console or any programmatic method to view or change the configuration of any EC2 instances in that Region\.

**Charges continue if you disable a Region**  
If you disable a Region that still includes AWS resources, charges for those resources \(if any\) continue to accrue at the standard rate\. For example, if you disable a Region that contains Amazon EC2 instances, you still have to pay the charges for those instances even though the instances are inaccessible\.

**Disabling a Region isn't always immediately visible**  
If you disable a Region, the change takes time to become visible in all possible endpoints\. Disabling a Region can take between a few seconds to minutes to take effect\. 

**Existing Regions are enabled by default**  
The original Regions \(the Regions that existed before we added the ability to enable and disable Regions\) are all enabled by default and can't be disabled\.

**Enabling a Region takes a few minutes for most accounts**  
Enabling a Region generally takes effect in a few minutes, although it can take longer for some accounts\. If enabling a Region takes longer than nine hours, sign in to the AWS Support Center and open a case with AWS Support\.

Perform the applicable procedure:
+ [To enable a Region](#enable-region)
+ [To disable a Region](#disable-region)<a name="enable-region"></a>

**To enable a Region**



1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Under **AWS Regions**, next to the Region to enable, choose **Enable**\.

   Older Regions are enabled by default\.

1. In the dialog box, choose **Enable region**\.

For more information about enabling a Region, including the permissions required, see [Managing AWS Regions](https://docs.aws.amazon.com/general/latest/gr/rande-manage.html)\.<a name="disable-region"></a>

**To disable a Region**

You can disable some Regions on your **My Account** page\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation bar, choose your account name, and then choose [https://console.aws.amazon.com/billing/home#/account](https://console.aws.amazon.com/billing/home#/account)\.

1. Under **AWS Regions**, next to the Region to disable, choose **Disable**\.

   Not all Regions can be disabled\.

1. In the dialog box, for **To confirm disabling in this region, ** enter **disable** and choose **Disable region**\.

## Updating and deleting tax registration numbers<a name="manage-account-payment-update-delete-tax-numbers"></a>

To update or delete one or more tax registration numbers, perform the applicable procedure:
+ [To update tax registration numbers](#edit-tax)
+ [To delete tax registration numbers](#remove-tax)<a name="edit-tax"></a>

**To update tax registration numbers**



1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Tax Settings**\.

1. Under **Manage Tax Registration Numbers**, select the numbers to edit\.

1. For **Manage Tax Registration**, choose **Edit**\.

1. Update the fields to change and choose **Update**\.<a name="remove-tax"></a>

**To delete tax registration numbers**

You can remove one or more tax registration numbers\. 

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Tax Settings**\.

1. Under **Manage Tax Registration Numbers**, select the tax registration numbers to delete\.

1. For **Manage Tax Registration**, choose **Delete**\.

1. In the **Delete tax registration** dialog box, choose **Delete**\.

## Enabling tax setting inheritance<a name="manage-account-tax-linked-accounts"></a>

You can use your tax registration information with your linked accounts by enabling your **Tax Settings Inheritance**\. After you enable it, your tax registration information is added to your other AWS Organizations accounts, saving you the effort of registering redundant information\. Tax invoices are processed with the consistent tax information, and your usage from member accounts will consolidate to a single tax invoice\.

**Note**  
Tax inheritance settings are only available to accounts after a member account is added\.

Tax registration information includes:
+ Business legal name
+ Tax address
+ Tax registration number
+ Special exemptions \(does not apply for US sales tax exemptions\)<a name="enable-tax-inheritance"></a>

**To enable tax setting inheritance**



1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Tax Settings**\.

1. Under **Manage Tax Registration Numbers**, select **Enable Tax Settings Inheritance**\.

1. Choose **Continue**\.