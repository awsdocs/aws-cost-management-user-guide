# Logging Billing and Cost Management API Calls with AWS CloudTrail<a name="logging-using-cloudtrail"></a>

Billing and Cost Management is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in Billing and Cost Management\. CloudTrail captures a subset of API calls for Billing and Cost Management as events, including calls from the Billing and Cost Management console and from code calls to the Billing and Cost Management APIs\. If you create a trail, you can enable continuous delivery of CloudTrail events to an Amazon S3 bucket, including events for Billing and Cost Management\. If you don't configure a trail, you can still view the most recent events in the CloudTrail console in **Event history**\. Using the information collected by CloudTrail, you can determine the request that was made to Billing and Cost Management, the IP address from which the request was made, who made the request, when it was made, and additional details\. 

To learn more about CloudTrail, including how to configure and enable it, see the [AWS CloudTrail User Guide](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/)\.

## Billing and Cost Management Information in CloudTrail<a name="service-name-info-in-cloudtrail"></a>

CloudTrail is enabled on your AWS account when you create the account\. When supported event activity occurs in Billing and Cost Management, that activity is recorded in a CloudTrail event along with other AWS service events in **Event history**\. You can view, search, and download recent events in your AWS account\. For more information, see [Viewing Events with CloudTrail Event History](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/view-cloudtrail-events.html)\. 

For an ongoing record of events in your AWS account, including events for Billing and Cost Management, create a trail\. A trail enables CloudTrail to deliver log files to an Amazon S3 bucket\. By default, when you create a trail in the console, the trail applies to all regions\. The trail logs events from all regions in the AWS partition and delivers the log files to the Amazon S3 bucket that you specify\. Additionally, you can configure other AWS services to further analyze and act upon the event data collected in CloudTrail logs\. For more information, see: 
+ [Overview for Creating a Trail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-and-update-a-trail.html)
+ [CloudTrail Supported Services and Integrations](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html#cloudtrail-aws-service-specific-topics-integrations)
+ [Configuring Amazon SNS Notifications for CloudTrail](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/getting_notifications_top_level.html)
+ [Receiving CloudTrail Log Files from Multiple Regions](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html) and [Receiving CloudTrail Log Files from Multiple Accounts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-receive-logs-from-multiple-accounts.html)

Billing and Cost Management supports logging the following actions as events in CloudTrail log files:
+  `AcceptFxPaymentCurrencyTermsAndConditions` 
+  `AcceptTermsAndConditions` 
+  `CancelPayment` 
+  `CloseAccount` 
+  `CreateOrigamiReportPreference` 
+  `CreatePaymentMethod` 
+  `DeleteOrigamiReportPreferences` 
+  `DeletePaymentMethod` 
+  `EnableBillingAlerts` 
+  `MakePayment` 
+  `RetryPayment` 
+  `SetAccountContractMetadata` 
+  `SetAccountPreferences` 
+  `SetAdditionalContacts` 
+  `SetBillingAddress` 
+  `SetContactAddress` 
+  `SetCostExplorerPreferences` 
+  `SetCreatedByOptIn` 
+  `SetCreditSharing` 
+  `SetDefaultPaymentMethod` 
+  `SetFreetierBudgetsPreference` 
+  `SetFxPaymentCurrency` 
+  `SetIAMAccessPreference` 
+  `SetPanInformation` 
+  `SetRISharing` 
+  `SetSecurityQuestions` 
+  `SetTagKeysState` 
+  `SetTaxRegistration` 
+  `UpdateOrigamiReportPreference` 
+  `UpdatePaymentMethod` 

Every event or log entry contains information about who generated the request\. The identity information helps you determine the following: 
+ Whether the request was made with root or IAM user credentials\.
+ Whether the request was made with temporary security credentials for a role or federated user\.
+ Whether the request was made by another AWS service\.

For more information, see the [CloudTrail userIdentity Element](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-event-reference-user-identity.html)\.

## Example: Billing and Cost Management Log File Entries<a name="understanding-service-name-entries"></a>

 A trail is a configuration that enables delivery of events as log files to an Amazon S3 bucket that you specify\. CloudTrail log files contain one or more log entries\. An event represents a single request from any source and includes information about the requested action, the date and time of the action, request parameters, and so on\. CloudTrail log files are not an ordered stack trace of the public API calls, so they don't appear in any specific order\.

The following example shows a CloudTrail log entry that demonstrates the `SetContactAddress` action\.

```
{
        "eventVersion": "1.05",
        "userIdentity": {
            "accountId": "444455556666",
            "accessKeyId": "AKIAIOSFODNN7EXAMPLE"
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
        "recipientAccountId": "111122223333"
    }
```