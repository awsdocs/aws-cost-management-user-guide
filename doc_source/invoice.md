# Viewing your monthly charges<a name="invoice"></a>

At the end of a monthly billing period, or when you incur a one\-time fee, AWS issues an invoice as a PDF file\. If you're paying by credit card, AWS also charges the credit card you have on file at this time\. This section shows how you can use the **Bills** page in your AWS Billing console to download invoices and view your monthly charge details\.

**Note**  
IAM users need explicit permission to see some of the pages in the Billing and Cost Management console\. For more information, see [Overview of managing access permissions](control-access-billing.md)\.

## Understanding your bills page<a name="understanding-billing-details"></a>

**Bills page**  
You can use the **Bills** page in your AWS Billing console to see your monthly chargeable costs, along with details of your AWS services and purchases made through AWS Marketplace\. Invoices are generated when a monthly billing period closes \(marked as **Issued** billing status\), or when subscriptions or one\-time purchases are made\. For monthly billing periods that haven't closed \(marked as **Pending** billing status\), this page shows the most recent estimated charges based on your AWS services metered to date\.   
If you're logged in as the management account of your AWS Organizations, you can see the consolidated charges for all of your member accounts\. By using the **charges by account** tab, you can also view account level details\.  
If you're an AWS Billing Conductor user, logged in as a management account, you can turn on a [pro forma](https://docs.aws.amazon.com/billingconductor/latest/userguide/understanding-abc.html) view by choosing the gear icon on the top of the page\. Choose **View billing period** to specify your billing period\.  
To customize the visible sections, choose the gear icon at the top of the page\. These preferences will be stored for ongoing visits to the **Bills** page\.

**AWS bill summary**  
The **AWS bill summary** section shows an overview of your monthly charges\. The information shows your invoice totals for the closed billing periods, marked as **Issued** status\.  
Billing periods that haven't closed are marked as **Pending** status\. The totals show the most recent estimated charges based on your AWS services metered to date\. Totals are shown in US dollars \(USD\)\. If your invoices are issued in another currency, the total in the other currency is also shown\.

**Payment information**  
The **Payment information** section lists invoices for the selected billing period that AWS received payments for\. The section lists the service provider, charge types, document types, invoice IDs, payment status, the date AWS received the payments, and the total amount in USD\. If your invoices are issued in another currency, the total in the other currency is also shown\. For more information, see [Managing your payments](manage-payments.md)\.

**Highest cost**  
The **highest cost** section identifies your account's service and Region with the highest cost for the billing period, and shows the month\-over\-month trends for each\. For pending billing periods, the month\-over\-month trend compares the month\-to\-date spend in the current billing period with the equivalent portion of the previous billing period\.

**Invoiced charges**  
The **invoiced charges** section lists the invoices for each service provider you transacted with during the selected billing period\. This section includes details such as charge type, invoice date, and total in USD\. If your invoices are issued in another currency, the total in the other currency is also shown\. Choose the **Invoice ID** to view and download a PDF format for individual invoices\.  
The **tax invoices** section lists tax invoices and other supplemental documents for the selected billing period\. Not all service providers issue tax invoices\. The **invoice ID** column shows the associated commercial invoice associated with that tax invoice\. Choose **document ID** to view and download a PDF format for individual invoices\.

**Savings**  
The **Savings** section summarizes your savings during the billing period as the outcome of Savings Plans, credits, or other discount programs\. These savings are also reflected in the **charges by service**, **charges by account**, and **invoiced charges** section\. Choose each savings type to see the details by service\.

**Charges by services**  
The **Charges by services** section shows your spend in each AWS service\. You can sort by **service name** or **amount in USD**, and filter by **service name**\. Choose the `+` icon next to each service to see the charges for that service by **Region**\. Choose a **Region** to see charge details\.

**Charges by account**  
If you use AWS Organizations and logged into your management account, the **Charges by account** section shows the spend of each of your member accounts\. You can sort by **account ID**, **account name**, or **amount in USD**, and filter by account ID or account name\. Choose the `+` icon next to each account to see charges for that account by service provider\. Choose the `+` icon next to each line item to see charges by service and Region\. Choose a **Region** to see charge details\.

**Taxes by service**  
The **taxes by service** section shows the pre\-tax, tax, and post\-tax charges for each service that was charged taxes\. You can sort by **service name**, **post\-tax charge**, **pre\-tax charge**, or **tax in USD**, and filter by service name\.