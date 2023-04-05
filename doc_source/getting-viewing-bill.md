# Viewing your bill<a name="getting-viewing-bill"></a>


|  | 
| --- |
| For questions about your AWS bills or to appeal your charges, contact AWS Support to address your inquiries immediately\. To get help, see [Getting help with AWS Billing](billing-get-answers.md)\. To understand your bills page contents, see [Viewing your monthly charges](invoice.md)\. | 

You receive AWS invoices monthly for usage charges and recurring fees\. For one\-time fees, such as fees for purchasing an All Upfront Reserved Instance, you are charged immediately\.

At any time, you can view estimated charges for the current month and final charges for previous months\. This section describes how to view your monthly bill and past bills and how to receive and read billing reports\.

## <a name="bill-process"></a>

**To access your monthly charges**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Bills**\.

1. Choose **Select billing period** on the top right to specify the billing period month\.

### Viewing your monthly charges \(old console\)<a name="collapsible-oldconsole-view"></a>

**To view your monthly charges**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose [Bills](https://console.aws.amazon.com/billing/home#/bill)\.

1. For **Date**, choose a month\.

   The **Summary** section displays a summary and details of your charges for that month\. It is not an invoice, however, until the month's activity closes and AWS calculates final charges\. 

   If you use the consolidated billing feature in AWS Organizations, the **Bills** page lists totals for all accounts on the **Consolidated Bill Details** tab\. Choose the **Bill Details by Account** tab to see the activity for each account in the organization\. For more information about consolidated billing, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.

**To download a copy of your charges as a PDF document**

1. Open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. On the **Bills** page, select a month from the **Select billing period**\.

1. Under the **AWS bill summary** section, confirm that the **bill status** is showing as **Issued**\.

1. Choose the **Invoiced charges** tab\.

1. Choose the **Invoice ID** of the document you want to download\.

1. \(For service providers other than AWS EMEA SARL\) To download a copy of a particular tax invoice, choose the **Document ID** in the **Tax Invoices** section\.

1. \(For AWS EMEA SARL\) To download a copy of a particular tax invoice, choose the **Document ID** in the **AWS EMEA SARL charges** section\.

### Downloading a copy of your charges as a PDF document \(old console\)<a name="collapsible-oldconsole-PDF"></a>

**To download a copy of your charges as a PDF document**

1. On the **Bills** page, select a month from the **Date** list for which all activity is closed\.

1. Under **Total**, choose **Amazon Web Services, Inc\. \- Service Charges**\.

1. Choose **Invoice <invoiceID>**\.

1. \(For entities other than AWS EMEA SARL\) To download a copy of a particular tax invoice, choose the **Invoice <invoiceID>** in the **Tax Invoices** section\.

1. \(For AWS EMEA SARL\) To download a copy of a particular tax invoice, choose the **Invoice <invoiceID>** in the **Amazon Web Services EMEA SARL – Service Charges** section\.

You can download CSV files for any future billing once you turn on reports\.

**To download a monthly report**

1. Turn on monthly reports by choosing **Billing preferences** in the navigation pane\.

1. Under **Detailed Billing Reports**, select **Turn on the legacy Detailed Billing Reports feature to receive ongoing reports of your AWS charges**\.

1. Choose **Configure** to specify where your reports will be delivered to\.
   + Under **Select existing bucket**, choose an existing Amazon S3 bucket name as your report destination\.
   + If you prefer to create a new Amazon S3 bucket to deliver reports to, enter an **Amazon S3 bucket name** and **Region** under **Create a bucket**\.

     1. Choose **Next**\.

     1. Verify your IAM policy and select **I have confirmed that this policy is correct**\.

     1. Choose **Save**\.

1. Choose **Save preferences**\.

1. On the **Bills** page, choose **Download all to CSV**\.