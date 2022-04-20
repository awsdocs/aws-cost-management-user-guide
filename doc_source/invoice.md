# Viewing your monthly charges<a name="invoice"></a>

At the end of a billing cycle or at the time you choose to incur a one\-time fee, AWS charges the credit card you have on file and issues your invoice as a PDF file\. You can download the PDF from the **Account Activity** page in the [Billing and Cost Management console](https://console.aws.amazon.com/billing/home?#/account) using the following steps\. 

**Note**  
IAM users need explicit permission to see some of the pages in the Billing and Cost Management console\. 

**To view your monthly charges**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose [Bills](https://console.aws.amazon.com/billing/home#/bill)\.

1. For **Date**, choose a month\.

   The **Summary** section displays a summary and details of your charges for that month\. It is not an invoice, however, until the month's activity closes and AWS calculates final charges\. 

   If you use the consolidated billing feature in AWS Organizations, the **Bills** page lists totals for all accounts on the **Consolidated Bill Details** tab\. Choose the **Bill Details by Account** tab to see the activity for each account in the organization\. For more information about consolidated billing, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.

**To view your charges for a different month**
+ On the **Bills** page, select the month you want from the **Date** list\.

**To download a copy of your charges as a PDF document**

1. On the **Bills** page, select a month from the **Date** list for which all activity is closed\.

1. Under **Total**, choose **Amazon Web Services, Inc\. \- Service Charges**\.

1. Choose **Invoice <invoiceID>**\.

1. \(For entities other than AWS EMEA SARL\) To download a copy of a particular tax invoice, choose the **Invoice <invoiceID>** in the **Tax Invoices** section\.

1. \(For AWS EMEA SARL\) To download a copy of a particular tax invoice, choose the **Invoice <invoiceID>** in the **Amazon Web Services EMEA SARL – Service Charges** section\.

**To download a monthly report**

Once you turn on the reports, you can download CSV files for any future billing periods\.

1. Turn on monthly reports by choosing **Billing preferences** in the navigation pane\.

1. Under **Detailed Billing Reports**, select **Turn on the legacy Detailed Billing Reports feature to receive ongoing reports of your AWS charges**\.

1. Choose **Configure** to specify where your reports will be delivered to\.
   + Under **Select existing bucket**, choose an existing Amazon S3 bucket name as your report destination\.
   + If you prefer to create a new Amazon S3 bucket to deliver reports to, enter an **Amazon S3 bucket name** and **Region** under **Create a bucket**\.

     1. Choose **Next**\.

     1. Verify your IAM policy and select **I have confirmed that this policy is correct**\.

     1. Choose **Save**\.

1. Choose **Save preferences**\.

1. On the **Bills** page, choose **Download CSV**\.