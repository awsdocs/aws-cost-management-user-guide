# Managing your payment profiles<a name="manage-paymentprofiles"></a>


|  | 
| --- |
| The payment profiles feature is in public preview for AWS Billing and Cost Management and is subject to change\. This feature is available for a select group of customers\. Your use of payment profiles is subject to the Betas and Previews terms of the [AWS Service Terms](http://aws.amazon.com/service-terms/) \(Section 2\)\. | 

You can use *payment profiles* to assign payment methods that are different than your default payment method to pay your invoices automatically\. If you receive invoices from more than one AWS service provider \("seller of record"\), use payment profiles to assign a unique payment method for each one\. After you create a payment profile for a service provider, your payment profile pays your AWS bills automatically\. It does so using the currency and payment method that you specify\.

Payment profiles are useful in avoiding situations such as incomplete payments, failed subscription orders, or unprocessed contract renewals despite having a valid default payment method\. By using payment profiles, you can do the following:
+ Use different payment methods for different AWS service providers\.
+ Customize your payment preferences for your AWS Organizations member accounts that use different service providers\.
+ Always have valid payment methods for your automatic bill payments\.
+ Avoid service interruptions and incomplete balances\.

**Note**  
Due to some country and technological limitations, not all payment methods are available for all providers\. If your default payment method isn't valid for different service providers, create payment profiles using payment methods accepted by your service provider\. For more information, see [Creating your payment profiles](manage-paymentprofiles-setup.md)\.

**Topics**
+ [Creating your payment profiles](manage-paymentprofiles-setup.md)
+ [Editing your payment profiles](manage-paymentprofiles-edit.md)
+ [Deleting your payment profiles](manage-paymentprofiles-delete.md)