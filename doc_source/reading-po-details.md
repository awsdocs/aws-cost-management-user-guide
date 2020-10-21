# Reading your purchase order details page<a name="reading-po-details"></a>

You can review the contents of your individual purchase orders on the **Purchase order details** page of the Billing and Cost Management console\.

To change your purchase order or line items, see [Editing your purchase orders](edit-po.md)\.
+ **Bill to **– The address reflected on your invoice\. To change your billing address, update the information from your [Payment methods](https://console.aws.amazon.com/billing/home#/paymentmethods)\.
+ **Ship to **– Your purchase order's shipping address\.
+ **Bill from **– The AWS legal entity you're billed from\.
+ **Payment terms **– Your negotiated AWS payment terms\.
+ **Currency **– Your preferred invoice payment currency\.
+ **Effective month**– The month your purchase order is effective from\. Your purchase order is used for generated invoices starting this month\.
+ **Expiration month**– The month your purchase order expires\. Your purchase order is not used for any invoices that are generated past this month\.
+ **Contacts **– A list of all contacts for this purchase order\. Choose **Manage contacts** to see all listed\.
+ **Status **– The current status of your purchase order\.
  + **Active **– Eligible for invoice association\.
  + **Suspended **– Not eligible for invoice association\. You can suspend an active or expired purchase order\.
  + **Expired **– A purchase order that is past its expiration date, and is no longer eligible for invoice association\.
  + **Suspended\-expired **– A suspended purchase order that is also past its expiration date\.
+ **Balance amount **– The balance remaining on your purchase order\. This is the total balance amount of all line items configured on your purchase order\.
+ **Total amount **– The sum of your total values for all line items configured in your purchase order\.
+ **Line items **– The line item details you used when adding the purchase order\.
  + **Number **– The unique identifier for your line item\.
  + **Type **– Your line item type\.
  + **Start month **– The month that your line is effective from\. The line item is eligible for invoice association from this month\.
  + **End month **– The month your line item expires\. The line item is not eligible for invoice association at the end of this month\.
  + **Amount **– The unit price amount\.
  + **Quantity **– The number of units\.
  + **Tax **– The tax amount\.
  + **Total value **– The total value of amount for the particular line item\.
  + **Current balance **– The remaining balance after subtracting the total amount of all invoices matched with this line item\. To see details for all invoices matching this line item, see the invoices table\.
+ **Invoices **– All invoices associated with your purchase order\.
  + **Date issued **– The date when the invoice was issued\.
  + **Type **– The type of invoice\. For example, invoice and credit memo\.
  + **ID **– The unique identifier of the invoice\.
  + **Line item number **– The line item number of your purchase order, associated with the invoice\.
  + **Amount **– The invoice amount\.
  + **Due date **– Your payment due date for the invoice\.