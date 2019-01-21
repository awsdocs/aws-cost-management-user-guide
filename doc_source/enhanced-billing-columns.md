# Billing Details<a name="enhanced-billing-columns"></a>

Columns under the **bill** header are static fields that appear in every AWS Cost and Usage report\. You can use the billing line items in the AWS Cost and Usage report to find details about the specific bill covered by the report, such as the charge type and the beginning and end of the billing period\. This includes the following columns: 

** bill/BillingEntity**  
The AWS seller that your account is with\. Possible values are the following:   
+ **AWS** – Amazon Web Services, Inc\. The entity that sells AWS services\.
+ **AISPL** – Amazon Internet Services Pvt\. Ltd\. The local Indian entity that acts as a reseller for AWS services in India\.
+ **AWS Marketplace** – The entity that supports the sale of solutions built on top of the AWS platform by third\-party software providers\.

** bill/BillingPeriodEndDate**  
The end date of the billing period that is covered by this report, in UTC\. The format is `YYYY-MM-DDTHH:mm:ssZ`\. 

** bill/BillingPeriodStartDate**  
The start date of the billing period that is covered by this report, in UTC\. The format is `YYYY-MM-DDTHH:mm:ssZ`\. 

** bill/BillType**  
The type of bill that this report covers\. There are three bill types:  
+ **Anniversary** – Line items for services that you used during the month
+ **Purchase** – Line items for upfront service fees
+ **Refund** – Line items for refunds

** bill/InvoiceId**  
The ID associated with a specific line item\. Until the report is final, the **InvoiceId** is blank\.

** bill/PayerAccountId**  
The account ID of the paying account\. For an organization in AWS Organizations, this is the account ID of the master account\.