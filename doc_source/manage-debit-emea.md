# Managing your SEPA direct debit payment methods<a name="manage-debit-emea"></a>

If you meet the eligibility requirements, you can add an EU bank account as a SEPA direct debit payment method to your payment methods\. To meet these requirements, your AWS account must:
+ Be an AWS Europe customer 
+ Have accepted SEPA terms and conditions
+ Have paid at least one invoice in full in the previous 12 months
+ Have paid at least $100 cumulative over the previous 12 months
+ Use euro as the preferred currency

If you pay by SEPA direct debit, AWS provides you with your invoice and initiates the charge to your payment method either the following day or the invoice due date, whichever is latest\. It can take up to 5 business days for the payment to complete successfully, even if the payment shows as **Succeeded** in the AWS Billing console\.

You can use the [Payment preferences](https://console.aws.amazon.com/billing/home#/paymentpreferences) page of the AWS Billing console to perform the following SEPA direct debit tasks:
+ [Add a direct debit account to your AWS Europe payment methods](#add-debit-emea)
+ [Update your linked debit account](#update-debit-emea)<a name="add-debit-emea"></a>

**To add a direct debit account to your AWS Europe payment methods**

You can use the AWS Billing console to add a direct debit account to your AWS Europe payment methods\. You can use any personal or business bank account, provided that the account is located at a branch in a SEPA\-supported country\. 

To add a SEPA direct debit account, you must have the following information ready:
+ Bank Identifier Code \(BIC\)
+ International Bank Account Number \(IBAN\)
+ The address that the bank associates with the account

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose [Payment preferences](https://console.aws.amazon.com/billing/home#/paymentpreferences)\.

1. Choose **Add payment method**\.

1. Choose **Bank account \(SEPA\)**\.

1. For **Account Holder Name**, enter the name of the principal account holder\.

1. For **BIC \(Swift Code\)**, enter the 8 or 11 digit number\.

   Routing numbers are always either 8 or 11 digits long\. 

1. For **Confirm BIC \(Swift Code\)**, reenter the BIC\. Don't copy and paste\.

1. For **IBAN**, enter the digits for the IBAN\.

1. For **Reenter IBAN**, reenter the IBAN digits\. Don't copy and paste\.

1. For **Make Default**, select whether you want this direct debit account to be your default payment method\.

1. For **Billing Address information**, enter the billing address of the primary account holder\.

1. Choose **Add bank account** to agree to the **Terms and Conditions** and add your direct debit account\.<a name="update-debit-emea"></a>

**To update your direct debit account**

You can update the name, address, or phone number associated with your direct debit account\.

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Payment preferences**\.

   Payment methods associated with your AWS account are listed in the **Payment method** section\.

1. Select the direct debit account that you want to edit, and choose **Edit**\.

1. Update the fields that you want to change\.

1. At the bottom of the dialog box, choose **Save changes**\.