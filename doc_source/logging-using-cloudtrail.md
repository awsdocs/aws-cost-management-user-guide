# Logging Billing and Cost Management API calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

Billing and Cost Management is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in Billing and Cost Management\. CloudTrail captures API calls for Billing and Cost Management as events, including calls from the Billing and Cost Management console and from code calls to the Billing and Cost Management APIs\. For a full list of CloudTrail events related to Billing, see [Billing CloudTrail events](#billing-cloudtrail-events)\.

If you create a trail, you can enable continuous delivery of CloudTrail events to an Amazon S3 bucket, including events for Billing and Cost Management\. If you don't configure a trail, you can still view the most recent events in the CloudTrail console in **Event history**\. Using the information collected by CloudTrail, you can determine the request that was made to Billing and Cost Management, the IP address from which the request was made, who made the request, when it was made, and additional details\. 

To learn more about CloudTrail, including how to configure and enable it, see the [AWS CloudTrail User Guide](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

## Billing CloudTrail events<a name="billing-cloudtrail-events"></a>

This section shows a full list of the CloudTrail events related to Billing and Cost Management\.


****  

| Event name | Definition | 
| --- | --- | 
| AcceptFxPaymentCurrencyTermsAndConditions | Logs the acceptance of the terms and conditions of paying in a currency other than USD\. | 
| CloseAccount | Logs the closing of an account\. | 
| CreateOrigamiReportPreference | Logs the creation of the cost and usage report; management account only\. | 
| DeleteOrigamiReportPreferences | Logs the deletion of the cost and usage report; management account only\. | 
| DownloadCommercialInvoice | Logs the download of a commercial invoice\. | 
| DownloadECSVForBillingPeriod | Logs the download of the eCSV file \(monthly usage report\) for a specific billing period\. | 
| DownloadTaxInvoice | Logs the download of a tax invoice\. | 
| EnableBillingAlerts | Logs the opt\-in of receiving CloudWatch billing alerts for estimated charges\. | 
| GetBillsForBillingPeriod | Logs the access of the account's usage and charges for a specific billing period\. | 
| GetBillsForLinkedAccount | Logs the access of a management account retrieving the usage and charges of one of the membr accounts in the consolidated billing family for a specific billing period\. | 
| GetCommercialInvoicesForBillingPeriod | Logs the access to the account's commercial invoices metadata for the specific billing period\. | 
| GetConsolidatedBillingFamilySummary | Logs the access of the management account retrieving the summary of the entire consolidated billing family\. | 
| GetLinkedAccountNames | Logs the retrieval from a management account of the member account names belonging to its consolidated billing family for a specific billing period\. | 
| GetTaxInvoicesMetadata | Logs the retrieval of tax invoices metadata\. | 
| GetTotalAmountForForecast | Logs the access to the forecasted charges for the specific billing period\. | 
| RedeemPromoCode | Logs the redemption of promotional credits for an account\. | 
| SetAccountContractMetadata | Logs the creation, deletion, or update of the necessary contract information for public sector customers\. | 
| SetAccountPreferences | Logs the updates of the account name, email, and password\. | 
| SetAdditionalContacts | Logs the creation, deletion, or update of the alternate contacts for billing, operations, and security communications\. | 
| SetContactAddress | Logs the creation, deletion, or update of the account owner address\. | 
| SetCostExplorerPreferences | Logs the opt\-in history of AWS Cost Explorer for the account\. | 
| SetCreatedByOptIn | Logs the opt\-in of the awscreatedby cost allocation tag preference\. | 
| SetCreditSharing | Logs the history of the credit sharing preference for the management account\. | 
| SetFreetierBudgetsPreference | Logs the preference \(opt\-in or opt\-out\) of receiving Free Tier usage alerts\. | 
| SetFxPaymentCurrency | Logs the creation, deletion, or update of the preferred currency used to pay your invoice\. | 
| SetIAMAccessPreference | Logs the creation, deletion, or update of the IAM user's ability to access to the billing console\. This setting is only for customers with root access\. | 
| SetPayInformation | Logs the payment method history \(invoice or credit/debit card\) for the account\. | 
| SetRISharing | Logs the history of the RI/Savings Plans sharing preference for the management account\. | 
| SetSecurityQuestions | Logs the creation, deletion, or update of the security challenge questions to help AWS identify you as the owner of the account\. | 
| SetTagKeysState | Logs the active or inactive state of a particular cost allocation tag\. | 
| SetTaxRegistration | Logs the creation, deletion, or update of the tax registration number for an account\. | 
| UpdateOrigamiReportPreference | Logs the update of the cost and usage report; management account only\. | 

## Billing and Cost Management information in CloudTrail<a name="service-name-info-in-cloudtrail"></a>

CloudTrail is enabled on your AWS account when you create the account\. When supported event activity occurs in Billing and Cost Management, that activity is recorded in a CloudTrail event along with other AWS service events in **Event history**\. You can view, search, and download recent events in your AWS account\. For more information, see [Viewing Events with CloudTrail Event History](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html) in the *AWS CloudTrail User Guide*\. 

For an ongoing record of events in your AWS account, including events for Billing and Cost Management, create a trail\. A trail enables CloudTrail to deliver log files to an Amazon S3 bucket\. By default, when you create a trail in the console, the trail applies to all AWS Regions\. The trail logs events from all Regions in the AWS partition and delivers the log files to the Amazon S3 bucket that you specify\. Additionally, you can configure other AWS services to further analyze and act upon the event data collected in CloudTrail logs\. 

For more information, see the following: 
+ [Overview for Creating a Trail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-and-update-a-trail.html)
+ [CloudTrail Supported Services and Integrations](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html#cloudtrail-aws-service-specific-topics-integrations)
+ [Configuring Amazon SNS Notifications for CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)
+ [Receiving CloudTrail Log Files from Multiple Regions](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html) and [Receiving CloudTrail Log Files from Multiple Accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)

Every event or log entry contains information about who generated the request\. The identity information helps you determine the following: 
+ Whether the request was made with root or IAM user credentials\.
+ Whether the request was made with temporary security credentials for a role or federated user\.
+ Whether the request was made by another AWS service\.

For more information, see the [CloudTrail userIdentity Element](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html) in the *AWS CloudTrail User Guide*\.

## Example: Billing and Cost Management log file entries<a name="understanding-service-name-entries"></a>

 A *trail* is a configuration that enables delivery of events as log files to an Amazon S3 bucket that you specify\. CloudTrail log files contain one or more log entries\. An event represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. CloudTrail log files are not an ordered stack trace of the public API calls, so they don't appear in any specific order\.

The following example shows a CloudTrail log entry that demonstrates the `SetContactAddress` action\.

```
{
        "eventVersion": "1.05",
        "userIdentity": {
            "accountId": "111122223333",
            "accessKeyId": "AIDACKCEVSQ6C2EXAMPLE"
        },
        "eventTime": "2018-05-30T16:44:04Z",
        "eventSource": "billingconsole.amazonaws.com",
        "eventName": "SetContactAddress",
        "awsRegion": "us-east-1",
        "sourceIPAddress": "100.100.10.10",
        "requestParameters": {
            "website": "https://amazon.com",
            "city": "Seattle",
            "postalCode": "98108",
            "fullName": "Jane Doe",
            "districtOrCounty": null,
            "phoneNumber": "206-555-0100",
            "countryCode": "US",
            "addressLine1": "Nowhere Estates",
            "addressLine2": "100 Main Street",
            "company": "AnyCompany",
            "state": "Washington",
            "addressLine3": "Anytown, USA",
            "secondaryPhone": "206-555-0101"
        },
        "responseElements": null,
        "eventID": "5923c499-063e-44ac-80fb-b40example9f",
        "readOnly": false,
        "eventType": "AwsConsoleAction",
        "recipientAccountId": "1111-2222-3333"
    }
```