# Making payments, checking unapplied funds, and viewing your payment history in AWS Europe<a name="manage-making-a-payment-emea"></a>

You can use the **Payments** page of the AWS Billing and Cost Management console to perform the following tasks for all payment types:
+ [Make a payment](#making-a-payment-emea)
+ [View outstanding invoices](#view-outstanding-invoices-procedure-emea)
+ [View unapplied funds](#view-unapplied-funds-procedure-emea)
+ [View payment history](#view-payment-history-procedure-emea)

## Make a payment<a name="make-a-payment-emea"></a>

AWS Europe charges your default payment method automatically at the beginning of each month\. If that charge doesn't process successfully, you can use the console to update your payment method and make a payment\.

**Note**  
If you pay by SEPA direct debit, AWS provides you with your invoice and initiates the charge to your payment method either the following day or the invoice due date, whichever is latest\. It can take up to 5 business days for your payment to succeed\. For more information, see [Managing your SEPA direct debit payment methods](manage-debit-emea.md)\.

Before making a payment, ensure that the payment method that you want automatically charged in the future is set as your default payment method\. If you are using a credit card, confirm that your credit card has not expired\. For more information, see [To designate a default payment method](edit-emea-payment-method.md#designate-default-emea) and [Managing your AWS Europe credit card payment methods](manage-cc-emea.md)\.<a name="making-a-payment-emea"></a>

**To make a payment**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payments**\.

   The **Payments due** table lists all outstanding invoices\. If there are no invoices listed, you don't need to take action at this time\.

1. If there are outstanding invoices, select the invoice you want to pay in the **Payments due** table, and then choose **Complete payment**\.

1. On the **Complete a payment** page, your default payment method is selected if it is eligible for you to use to pay the invoice\. If you want to use a different payment method or select an eligible payment method, choose **Change**\.

1. Confirm that the summary matches what you want to pay, and choose **Verify and pay**\.

   After your bank processes your payment, you're redirected to the **Payments** page\.

   If you pay by SEPA direct debit, and you receive an email from AWS Europe saying that AWS Europe can't charge your bank account and will try again, work with your bank to understand what went wrong\. 

   If you receive an email saying that AWS Europe failed the last attempt to charge your bank account, choose **Verify and pay** on the console to pay your invoice\. If you have questions about issues with charging your bank account or paying an overdue balance, create a case in the [Support Center](https://console.aws.amazon.com/support/home?#)\.

   If you pay by electronic funds transfer and your account payment is overdue, create a case in the [Support Center](https://console.aws.amazon.com/support/home?#)\.

## View outstanding invoices, unapplied funds, and payment history<a name="view-payment-info-emea"></a>

You can search and filter the **Payments due**, **Unapplied funds**, and **Payment history** tables described in the following procedures\. Choose the gear icon to change the default columns and customize other table settings\. Download items individually by choosing the appropriate ID, or choose **Download** and then ** Download CSV** to download a CSV file of the table for reporting purposes\.<a name="view-outstanding-invoices-procedure-emea"></a>

**To view outstanding invoices**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payments**\.

1. Choose the **Payments due** tab to view the **Payments due** table\. 

   The **Payments due** table lists all your outstanding invoices\. 

   The table includes the following statuses:
   + **Due** – Outstanding invoices with an approaching due date\.
   + **Past due** – Outstanding invoices where a payment has not been made by the due date\.
   + **Scheduled ** – Invoices with an upcoming scheduled payment\.
   + **Processing ** – Invoices for which we are currently scheduling a payment\.<a name="view-unapplied-funds-procedure-emea"></a>

**To view unapplied funds**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payments**\.

1. Choose the **Unapplied funds** tab to view the **Unapplied funds** table\. 

   The **Unapplied funds** table lists of all unapplied funds and credit memos\. <a name="view-payment-history-procedure-emea"></a>

**To view payment history**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Payments**\.

1. Choose the **Transactions** tab to view the **Transactions** table\. 

   The **Transactions** table lists all completed transactions with AWS\.