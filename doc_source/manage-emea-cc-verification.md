# Managing your AWS Europe credit card payment verifications<a name="manage-emea-cc-verification"></a>

To comply with the recent EU regulation, your bank might ask you for verification whenever you use a credit card to pay AWS online, add or update a credit card, or register a new AWS account\. Banks typically verify by sending unique security codes to credit card holders before online purchases are completed\. If your bank needs to verify your payment, you will receive an email from AWS\. After verification, you're redirected to the AWS website\. 

If you prefer not to verify payments, register a bank account as your payment method\. For more information about direct debit payment eligibility, see [Managing your SEPA direct debit payment methods](manage-debit-emea.md)\.

To learn more about the EU regulation, see the [European Commission’s website](https://ec.europa.eu/info/law/payment-services-psd-2-directive-eu-2015-2366_en)\.
+ [Best practices for verification](#emea-cc-mfa-bp)
+ [Payment verification](#emea-payment-verification)
+ [Troubleshooting payment verification](#emea-cc-bp)
+ [AWS Organizations](#emea-cc-awsorg)
+ [Subscription purchases](#emea-bulk-purchases)

## Best practices for verification<a name="emea-cc-mfa-bp"></a>
+ Confirm that your credit card information is up to date\. Banks send verification codes only to the registered card owner\.
+ Enter the newest code\. If you close the authentication portal or request a new code, you might experience a delay in receiving your newest code\.
+ Enter the code as prompted\. Don't enter the phone number that the code is sent from\.

## Payment verification<a name="emea-payment-verification"></a>

You can use the Billing and Cost Management console to confirm that you payment requires verification or to reattempt any failed payments\.<a name="emea-payment-verification-process"></a>

**To verify your payment**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Orders and invoices**\.

1. Under **Payments due**, locate the invoice that you want to pay and choose **Verify and pay**\.

1. On the choose [Payment Methods](https://console.aws.amazon.com/billing/home#/paymentmethods) page, select the preferred payment method\.

1. Choose **Complete payment**\.

1. If your payment requires verification, you're redirected to your bank's website\. To complete verification, follow the provided prompts\.

After your bank has processed our payment, you're redirected to the **Orders and invoices** page\.

**Note**  
Your invoice appears with the status of **Payment processing** until your bank completes the payment process\. 

## Troubleshooting payment verification<a name="emea-cc-bp"></a>

If you can't successfully complete your verification, we recommend that you take any of the following actions:
+ Contact your bank to confirm that your contact information is up to date
+ Contact your bank for details about why your verification has failed
+ Clear your cache and cookies or use a different browser
+ Navigate to the [Payment Methods](https://console.aws.amazon.com/billing/home#/paymentmethods) page of the Billing and Cost Management console and update your billing contact information

## AWS Organizations<a name="emea-cc-awsorg"></a>

If you're a member account in AWS Organizations, your purchased services that require upfront payments might not activate until the Management account user verifies the payment\. If verification is required, AWS notifies the billing contact of the Management account by email\.

Establish a communication process between your Management account and member accounts\. To change your payment method, see [Managing your AWS Europe credit card payment methods](manage-cc-emea.md)\.

## Subscription purchases<a name="emea-bulk-purchases"></a>

If you purchase multiple subscriptions at a time \(or in bulk\) and your bank requests verification, the bank might ask you to verify each individual purchase\.

Subscriptions can include immediate purchases such as Reserved Instances, Business support plan, and Route 53 domains\. Subscriptions don't include AWS Marketplace charges\.

Be sure to complete validation for all purchases or register a bank account as your payment method\. For more information about eligibility for direct debit payment, see [Managing your SEPA direct debit payment methods](manage-debit-emea.md)\.