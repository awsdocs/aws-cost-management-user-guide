# Tracking Your Free Tier Usage<a name="tracking-free-tier-usage"></a>

You can track your AWS Free Tier usage to help you stay under the free tier limits\. AWS automatically provides alerts through AWS Budgets to notify you by email when you exceed the free tier limits or when you are forecast to go over the free tier limits\. You can also view the **Top Free Tier Services by Usage** table on the Billing and Cost Management dashboard to see which five services you have used the most and how much you have used them\.

**Topics**
+ [Free Tier Usage Alerts Using AWS Budgets](#free-budget)
+ [Top Free Tier Services Table](#free-tier-table)
+ [Trackable Free Tier Services](#free-tier-services)

## Free Tier Usage Alerts Using AWS Budgets<a name="free-budget"></a>

AWS automatically provides AWS Free Tier usage alerts using AWS Budgets to help you track your free tier usage\. These budgets allow AWS to notify you when you're close to exceeding the free tier limits or are forecast to exceed the free tier limits\. You can also use the budgets to plan how you use AWS resources to avoid exceeding the free tier limits\. Any usage over the free tier limits is charged at the regular rate\. 

When you exceed the free tier limits or are forecast to exceed them, AWS sends an alert to the email address that you used to create your account\. You can change which email address that AWS uses for the alerts on the Billing and Cost Management console\. AWS sends the notifications when you either go over 100% of your available free tier or are forecast to go over 101%\. The AWS Free Tier usage alert forecast does not use the Cost Explorer forecasting, and instead assumes that your usage remains steady throughout the month\. For example, if you use 50 Amazon EC2 hours over five days, the forecast assumes that you are using 50 EC2 hours every five days\. Only one notification per usage type is sent during a month\. Usage types are the units that each service uses to measure the usage of a specific type of resource\. For example, the `BoxUsage:t2.micro(Hrs)` usage type filters by the running hours of Amazon EC2 `t2.micro` instances\.

**Important**  
If you launch more AWS resources than the free tier covers in a short period of time, you can exceed the free tier limits before AWS can proactively notify you about exceeding the free tier usage limits\. If that happens, AWS still notifies you that your incurred usage exceeded the free tier limit\.

AWS Free Tier usage alerts cover non\-expiring free tier offerings, such as the first 25 GB of Amazon DynamoDB storage or the first 10 custom Amazon CloudWatch metrics\. The alerts also cover free tier offerings that expire after 12 months, such as the 750 hours per month of Amazon EC2 `Windows t2.micro` instance usage and the first five GB of standard Amazon S3 storage\. For the full list of services and usage types covered by the free tier usage alerts, see [Trackable Free Tier Services](#free-tier-services)\. 

AWS Free Tier usage alerts are enabled automatically for all individual accounts, but not for a master account in an organization in AWS Organizations\. If you're an owner of a master account in an organization, you can opt in to the usage alerts on the **Preferences** page on the Billing and Cost Management console\. The same free tier limit applies to all accounts in an organization \(both master and member accounts\), so the same budget also applies to all of the accounts\. For example, if Alejandro has a member account and uses 400 Amazon EC2 hours and Mary has a member account and uses 400 Amazon EC2 hours, for a total of 800 hours, the organization has exceeded the free tier limit by 50 Amazon EC2 hours\.<a name="opt-in-out"></a>

**To opt in or out of AWS Free Tier usage alerts**

You can opt in to or out of the AWS Free Tier usage alerts through the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. Under **Preferences** in the navigation pane, choose ** Billing preferences**\.

1. Under **Cost Management Preferences**, select **Receive Free Tier Usage Alerts** to opt in to free tier usage alerts\. To opt out, clear the **Receive Free Tier Usage Alerts** check box\.<a name="customize-email"></a>

**To change the email address for free tier usage alerts**

AWS sends free tier usage alerts to the email address that you used when you created your account\. You can change the email address on the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. Under **Preferences** in the navigation pane, choose ** Billing preferences**\.

1. Under **Cost Management Preferences**, under **Receive Free Tier Usage Alerts** in the **Email Address** dialog box, enter the email address where you want to receive the usage alerts\.

1. Scroll to the end of the page and choose the **Save preferences** button\.

## Top Free Tier Services Table<a name="free-tier-table"></a>

If you are eligible for the free tier and you use a free tier offering, you can track your usage with the **Top Free Tier Services by Usage** table on the dashboard of the [Billing and Cost Management console](https://console.aws.amazon.com/billing/home)\. The following conditions might limit whether you see the free tier table data: 
+ You use an AWS service that doesn't offer a free tier
+ Your free tier has expired
+ You access AWS through an AWS Organizations member account
+ You use an AWS service in the AWS GovCloud \(US\-West\) or AWS GovCloud \(US\-East\) regions

The **Top Free Tier Service by Usage** table is grouped by service limit and shows the free tier usage limit for your top five most\-used free tier service measurements, along with your current usage amount\. A service might have multiple lines, enabling you to track each free tier limit closely\. The table shows usage as both a percentage of the free tier limit and a ratio of the free tier limit\. 

For example, each month you get 2,000 Amazon S3 `Put` operations and 5 GB of Amazon S3 storage\. The free tier usage table has two lines, one for `S3 - Puts` and one for `S3 - Storage`\. If you use 2,000 of the free tier `S3 - Puts` operations, the table shows 2,000\.00/2,000 Requests and 100%, and if you use 0\.55 GB of the free tier `S3 - Storage`, the table shows `0.55/5 GB` and 11%, as shown in the following screenshot\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

To see more details about your free tier usage, including all of your active free tier services, choose **View All** in the **Top Free Tier Services by Usage** table\. The detailed table includes additional information such as the forecast of your usage for the month and a status icon to alert you if you have exceeded the limits or are predicted to exceed the limits\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

## Trackable Free Tier Services<a name="free-tier-services"></a>

AWS enables you to track how much you used free tier services and what service usage types you used\. Usage types are the specific type of usage that AWS tracks\. For example, the usage type `Global-BoxUsage:freetier.micro` means that you used an Amazon EC2 micro instance\.

The AWS Free Tier usage alerts and the **Top Free Tier Services by Usage** table cover both expiring and non\-expiring free tier offerings\. You can track the following services and usage types\.


| Service | Usage Type | 
| --- | --- | 
|  Amazon API Gateway   |  `Global-ApiGatewayRequest`  | 
|  AWS CodeBuild   |  `Global-Build-Min:Linux:g1.small`  | 
|  Amazon GameLift   |  `Global-BoxUsage:c3.large`  | 
|  AWS Storage Gateway   |  `Global-Uploaded-Bytes`  | 
|  Amazon Cloud Directory   |  `Global-Requests-Tier1` `Global-Requests-Tier2` `Global-TimedStorage-ByteHrs`  | 
|  Amazon CloudFront   |  `Global-DataTransfer-Out-Bytes` `Global-Requests-Tier1`  | 
|  Amazon Cognito Sync   |  `Global-CognitoSyncOperation` `Global-TimedStorage-ByteHrs`  | 
|  Amazon Cognito   |  `Global-CognitoUserPoolMAU`  | 
|  Amazon Connect   |  `USE1-end-customer-mins`  | 
|  Amazon CloudWatch   |  `Global-CW:Requests` `Global-DataProcessing-Bytes` `Global-TimedStorage-ByteHrs`  | 
|  Amazon DynamoDB   |  `TimedStorage-ByteHrs`  | 
|  AWS Database Migration Service   |  `Global-InstanceUsg:dms.t2.micro`  | 
|  Amazon Elastic Compute Cloud   |  `Global-BoxUsage:freetier.micro` `Global-BoxUsage:freetier.micro` `Global-DataProcessing-Bytes` `Global-EBS:SnapshotUsage` `Global-EBS:VolumeIOUsage` `Global-EBS:VolumeUsage` `Global-LCUUsage` `Global-LoadBalancerUsage`  | 
|  Amazon Elastic Container Registry   |  `Global-TimedStorage-ByteHrs`  | 
|  Amazon Elastic File System   |  `Global-TimedStorage-ByteHrs`  | 
|  Amazon ElastiCache   |  `Global-NodeUsage:cache.t1.micro`  | 
|  Amazon Elasticsearch Service   |  `Global-ES:freetier-Storage` `Global-ESInstance:freetier.micro`  | 
|  Amazon Elastic Transcoder   |  `Global-ets-hd-success` `Global-ets-sd-success` `Global-ets-audio-success`  | 
|  AWS IoT   |  `AWSIoT-messages`  | 
|  AWS Key Management Service   |  `Global-KMS-Requests`  | 
|  AWS Lambda   |  `Global-Lambda-GB-Second` `Global-Request`  | 
|  Amazon Lex   |  `Lex-Global-Speech-Requests` `Lex-Global-Text-Requests`  | 
|  Amazon Mobile Analytics   |  `EventsRecorded`  | 
|  AWS OpsWorks   |  `OpsWorks-Chef-Automate`  | 
|  Amazon Pinpoint   |  `Pinpoint_DeliveryAttempts` `Pinpoint_MonthlyTargetedAudience`  | 
|  Amazon Polly   |  `Global-SynthesizeSpeech-Chars`  | 
|  Amazon Relational Database Service   |  `Global-InstanceUsage:db.t1.micro` `Global-RDS:StorageIOUsage`  | 
|  Amazon Rekognition   |  `Global-FaceVectorsStored` `Global-ImagesProcessed`  | 
|  Amazon Simple Storage Service   |  `Global-Requests-Tier1` `Global-Requests-Tier2` `Global-TimedStorage-ByteHrs`  | 
|  Amazon Simple Email Service   |  `Global-Message`  | 
|  Amazon Simple Email Service   |  `Global-Recipients-EC2`  | 
|  Amazon Simple Notification Service   |  `DeliveryAttempts-HTTP` `DeliveryAttempts-SMTP` `Requests-Tier1`  | 
|  Amazon Simple Queue Service   |  `Global-Requests`  | 
|  Amazon Simple Workflow Service   |  `Global-AggregateInitiatedActions` `Global-AggregateInitiatedWorkflows` `Global-AggregateWorkflowDays`  | 
|  AWS X\-Ray   |  `Global-XRay-TracesAccessed` `Global-XRay-TracesStored`  | 
|  AWSDataTransfer   |  `Global-DataTransfer-Out-Bytes`  | 
|  Amazon States   |  `Global-StateTransition`  | 
|  ContactCenterTelecomm   |  `USE1-US-did-inbound-mins` `USE1-US-outbound-mins` `USE1-US-tollfree-inbound-mins`  | 