# Adding a purchase order<a name="adding-po"></a>

You can use the Billing and Cost Management console to add purchase orders to use in your invoices\. Adding a purchase order is a two\-step process involving purchase orders and line item configurations\. First, you enter your purchase order details \(for example, purchase order ID, shipping address, effective and expiration month\)\. Then, you define the purchase order line item configurations that are used to match the purchase order with an invoice\. If you add multiple purchase orders, we use the purchase order that has the line item best matching the invoice being generated\.<a name="add-po-steps"></a>

**To add a purchase order**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Purchase orders**\.

1. Choose **Add purchase order**\.

1. For **Purchase order ID**, enter a unique identifier for your purchase order ID\. Purchase order IDs must be unique within your account\. For details about character restrictions for your purchase ID, see [Purchase orders](billing-limits.md#limits-po)\.

1. \(Optional\) For **Description**, describe your purchase order, including any notes for your reference\.

1. For **Ship to**, enter your shipping address\.

   \(Optional\) Select **Copy Bill to address** to copy and edit the address populated from your **Bill to** field\.

1. For **Bill from**, choose the AWS billing entity that you are invoiced from\.
**Note**  
Remittance details are different for each **Bill from** location\. Be sure to verify your **Bill from** selection\. You must make your payments to the legal entity that you're billed from\. We don't recommend configuring more than one **Bill from** location for a purchase order\.

1. For **Effective month**, choose the month you want your purchase order to start from\. Your purchase order is eligible for invoice associations starting from this month\.

1. For **Expiration month**, choose the month you want your purchase order to end\. Your purchase order expires at the end of this month, and is not used for invoice associations going forward\.

1. \(Optional\) For **Purchase order contacts**, enter the contact name, email address, and phone number\. You can add up to 10 contacts\.

1. Choose **Configure line items**\.

1. For **Line item number**, enter a unique identifier for your line item number\.

1. \(Optional\) For **Description**, enter a description for your line item\.

1. For **Line item type**, choose your preferred line item type\. For a detailed description for each line item type, see [Managing your purchase orders](manage-purchaseorders.md)\.

1. For **Start month**, choose the month you want your line item to start from\. This date cannot be earlier than your purchase order **Effective month**\.

1. For **End month**, choose the month you want your line item to end\. This date cannot be later than your purchase order **Expiration month**\.

1. \(Optional\) Choose **Enable balance tracking** to track the balance of your line item\.

1. For **Amount**, enter the total amount of your purchase order line item\.

1. For **Quantity**, enter the quantity amount\.

1. \(Optional\) For **Tax**, enter the tax amount\. This can be an absolute value or a percentage of the line item amount\.

   For **Tax type**, choose **% of amount** to enter a percentage, or **amount in $** to enter an absolute tax amount\.

1. To add other line items, choose **Add new line item**\. You can add up to 100 line items\.

1. Choose **Submit purchase order**\.

Some fields are automatically filled and cannot be edited\. Here is a list of where the automated fields are referenced from\.
+ **Bill to** – The **Bill to** address for your invoice\. This field is included as a reference, because your purchase order billing address should match your invoice billing address\. 
+ **Payment terms** – Your negotiated payment terms\.
+ **Currency** – Your preferred invoice currency\.