# Managing your ACH direct debit payment methods<a name="manage-debit"></a>

If you meet the eligibility requirements, you can add a US bank account as an ACH direct debit payment method to your payment methods\. 

To be eligible, your account must meet the following requirements:
+ It is an Amazon Web Services, Inc\. customer\. 
+ It is at least 60 days old\.
+ It has paid at least one invoice in full in the previous 12 months\.
+ It has paid at least $100 cumulative over the previous 12 months\.
+ It uses USD as the preferred currency\.

If you pay by ACH direct debit, AWS provides you with your invoice and initiates the charge to your payment method within 10 days of the start of the month\. It can take up to 20 days for the payment to complete successfully, even if the payment shows as **Succeeded** on the Billing and Cost Management console\.

You can use the [Payment Methods](https://console.aws.amazon.com/billing/home#/paymentmethods) page of the Billing and Cost Management console to perform the following ACH direct debit tasks:
+ [Add a direct debit account to your AWS payment methods](#add-debit)
+ [Update your linked debit account](#update-debit)<a name="add-debit"></a>

**To add a direct debit account to your AWS payment methods**

You can use the Billing and Cost Management console to add a direct debit account to your AWS payment methods\. You can use any personal or business bank account, provided that the account is located at a branch in the US\. 

To add an ACH direct debit account, you must have the following information ready:
+ A US bank account number
+ A US bank account routing number
+ The address that the bank associates with the account
+ \(For a personal bank account\) A US driver's license number or state\-issued ID number
+ \(For a business bank account\) A Federal tax ID number

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose [Payment methods](https://console.aws.amazon.com/billing/home#/paymentmethods)\.

1. Choose **Add a bank account**\.

1. For **Account Holder Name**, enter the name of the principal account holder\.

1. For **Bank Routing Number**, enter the nine\-digit routing number\.

   Routing numbers are always nine digits long\. Some banks list the routing number first on a check, and other banks list the account number first\. 

1. For **Bank Account Number**, enter the account number\. Account numbers might have up to 17 digits\. The account must be an ACH\-enabled checking account at a bank located in the US\.

1. For **Bank Account Type**, choose **Personal** or **Business**\.

1. \(Personal\) For **Driver's License Number**, enter the primary account holder's valid US driver's license or state\-issued ID number\.

   For **State**, enter the name of the state where the ID was issued\.

1. \(Business\) For **Federal tax ID**, enter the Federal tax ID for the business\.

1. For **Make Default**, select whether you want this direct debit account to be your default payment method\.

1. For **Billing Address Information**, enter the billing address of the primary account holder\.

1. Choose **Create** to agree to the **Terms and Conditions** and add your direct debit account\.<a name="update-debit"></a>

**To update your direct debit account**

You can update the name, address, or phone number associated with your direct debit account\.

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payment methods**\.

1. Next to the direct debit account that you want to edit, choose **Edit**\.

1. Update the information that you want to change\.

1. At the bottom of the dialog box, choose **Update**\.