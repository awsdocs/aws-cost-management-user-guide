# Managing your credit card and ACH payment methods<a name="manage-cc"></a>

You can use the [Payment preferences](https://console.aws.amazon.com/billing/home#/paymentpreferences) page of the AWS Billing console to perform the following credit card tasks:
+ [Add a credit card](#Add-cc)
+ [Update your credit card](#update-your-cc)
+ [Confirm credit card information](#confirm-cc)
+ [Use a Chinese yuan credit card](manage-payment-cny.md#yuan-cc)

## Add a credit card<a name="Add-cc"></a>

You can use the console to add a credit card to your account\.<a name="add-credit"></a>

**To add a credit card to your AWS account**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose [Payment preferences](https://console.aws.amazon.com/billing/home#/paymentpreferences)\.

1. Choose **Add payment method**\.

1. Enter the credit card information\.

   To designate this card as the default payment method, choose **Set as default payment method**\.

1. Enter your card billing address\.

1. Choose **Add card**\.

## Update your credit card<a name="update-your-cc"></a>

You can update the name, address, or phone number that is associated with your credit card\.

**Note**  
When you add or update your credit card, AWS charges any unpaid invoices from the previous month to the new card\.<a name="update-cc"></a>

**To update your credit card**

1. Open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payment preferences**\.

   Payment methods associated with your AWS account are listed in the **Payment methods** section\.

1. Select the credit card that you want to edit, and choose **Edit**\.

1. Update the information that you want to change\.

1. At the bottom on the page, choose **Update**\.

## Confirm credit card information<a name="confirm-cc"></a>

To make a payment, you must have a valid, unexpired credit card on file\.<a name="check-credit-card-expiration-date"></a>

**To confirm that your credit card is up to date**

1. Open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payment preferences**\.

1. Ensure that the **Expires On** date for your card is in the future\. If your card has expired, add a new card or update your current card\.

## Managing your ACH direct debit payment methods<a name="manage-debit"></a>

If you meet the eligibility requirements, you can add a US bank account as an ACH direct debit payment method to your payment methods\. 

To be eligible, your AWS account must meet the following requirements:
+ It is an Amazon Web Services customer\. 
+ It is at least 60 days old\.
+ It has paid at least one invoice in full in the previous 12 months\.
+ It has paid at least $100 cumulative over the previous 12 months\.
+ It uses USD as the preferred currency\.

If you pay by ACH direct debit, AWS provides you with your invoice and initiates the charge to your payment method within 10 days of the start of the month\. It can take up to 20 days for the payment to complete successfully, even if the payment shows as **Succeeded** on the AWS Billing console\.

You can use the [Payment Methods](https://console.aws.amazon.com/billing/home#/paymentpreferences) page of the AWS Billing console to add or update a direct debit account\.<a name="add-debit"></a>

**To add a direct debit account to your AWS payment methods**

You can use the AWS Billing console to add a direct debit account to your AWS payment methods\. You can use any personal or business bank account, provided that the account is located at a branch in the US\. 

To add an ACH direct debit account, you must have the following information ready:
+ A US bank account number
+ A US bank account routing number
+ The address that the bank associates with the account
+ \(For a personal bank account\) A US driver's license number or state\-issued ID number
+ \(For a business bank account\) A Federal tax ID number

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose [Payment preferences](https://console.aws.amazon.com/billing/home#/paymentpreferences)\.

1. Choose **Add payment method**\.

1. Choose **Bank account \(ACH\)**\.

1. For **Bank account type**, choose either **Personal** or **Business**\.

1. For **Name on account**, enter the name of the principal account holder\.

1. For **Bank Routing Number**, enter the nine\-digit routing number\.

   Routing numbers are always nine digits long\. Some banks list the routing number first on a check, and other banks list the account number first\. 

1. For **Bank Account Number**, enter the account number\. Account numbers might have up to 17 digits\. The account must be an ACH\-enabled checking account at a bank located in the US\.

1. \(Personal\) For **Driver's License Number**, enter the primary account holder's valid US driver's license or state\-issued ID number\.

   For **State**, enter the name of the state where the ID was issued\.

1. \(Business\) For **Tax ID**, enter the Federal tax ID for the business\.

1. For **Set as default payment method**, select whether you want this direct debit account to be your default payment method\.

1. For **Billing Address information**, enter the valid US billing address of the primary account holder\.

1. Choose **Add bank account** to agree to the **Terms and Conditions** and add your direct debit account\.<a name="update-debit"></a>

**To update your direct debit account**

You can update the name, address, or phone number associated with your direct debit account\.

1. Open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payment preferences**\.

   Payment methods associated with your AWS account are listed in the **Payment method** section\.

1. Select the direct debit account that you want to edit, and choose **Edit**\.

1. Update the information that you want to change\.

1. At the bottom of the dialog box, choose **Save changes**\.