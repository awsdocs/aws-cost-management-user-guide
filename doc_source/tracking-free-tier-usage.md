# Tracking your AWS Free Tier usage<a name="tracking-free-tier-usage"></a>

You can track your AWS Free Tier usage to help you stay under the AWS Free Tier limits\. AWS automatically provides alerts through AWS Budgets to notify you by email when you exceed 85 percent of your AWS Free Tier limits for each service\. You can also view the **Top AWS Free Tier Services by Usage** table on the Billing and Cost Management dashboard to see which five services you have used the most and how much you have used them\.

**Topics**
+ [AWS Free Tier usage alerts using AWS Budgets](#free-budget)
+ [Top AWS Free Tier services table](#free-tier-table)
+ [Trackable AWS Free Tier services](#free-tier-services)

## AWS Free Tier usage alerts using AWS Budgets<a name="free-budget"></a>

AWS automatically provides AWS Free Tier usage alerts using AWS Budgets to help you track your AWS Free Tier usage\. These AWS Free Tier usage alerts allow AWS to notify you when you're exceeding 85 percent of your usage for the month\. For additional AWS Free Tier visibility, you can also use AWS Budgets to track 100 percent of your AWS Free Tier usage for a specific service\. AWS Budgets has the additional ability to select usage targets and alert thresholds that you can customize\. For example, receive alerts when you're forecasted to exceed 100 percent of your Free Tier usage for Amazon Elastic Block Store\. Any usage over the AWS Free Tier limits is charged at the public On\-Demand rate\.

When you exceed a service\-specific AWS Free Tier limit, AWS sends an alert to the email address that you used to create your account\. You can change which email address that AWS uses for the alerts on the Billing and Cost Management console\. Only one alert per service\-specific AWS Free Tier usage type is sent in a month\. Usage types are the units that each service uses to measure the usage of a specific type of resource\. For example, the `BoxUsage:t2.micro(Hrs)`usage type filters by the running hours of Amazon EC2 `t2.micro` instances\.

**Important**  
If you launch more AWS resources than the AWS Free Tier covers in a short period of time, you can exceed the AWS Free Tier limits before AWS can proactively notify you about exceeding the AWS Free Tier usage limits\. If that happens, AWS still notifies you that your incurred usage exceeded 85 percent of the AWS Free Tier limit\.

AWS Free Tier usage alerts cover non\-expiring AWS Free Tier offerings, such as the first 25 GB of Amazon DynamoDB storage or the first 10 custom Amazon CloudWatch metrics\. The alerts also cover AWS Free Tier offerings that expire after 12 months, such as the 750 hours per month of Amazon EC2 `Windows t2.micro` instance usage and the first 5 GB of standard Amazon S3 storage\. For the full list of services and usage types covered by the AWS Free Tier usage alerts, see [Trackable AWS Free Tier services](#free-tier-services)\. 



AWS Free Tier usage alerts are enabled automatically for all individual accounts, but not for a management account in an organization in AWS Organizations\. If you're an owner of a management account in an organization, or Consolidated Billing family, you can opt in to the usage alerts on the **Preferences** page on the Billing and Cost Management console\. The same AWS Free Tier limit applies to all accounts in an organization \(both management account and member accounts\), so the same budget also applies to all of the accounts\. For example, if Alejandro has a member account and uses 400 Amazon EC2 hours and Mary has a member account and uses 400 Amazon EC2 hours, for a total of 800 hours, the organization has exceeded the AWS Free Tier limit by 50 Amazon EC2 hours\.<a name="opt-in-out"></a>

**To opt in or out of AWS Free Tier usage alerts**

You can opt in to or out of the AWS Free Tier usage alerts through the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Under **Preferences** in the navigation pane, choose ** Billing preferences**\.

1. Under **Cost Management Preferences**, select **Receive AWS Free Tier Usage Alerts** to opt in to Free Tier usage alerts\. To opt out, clear the **Receive AWS Free Tier Usage Alerts** check box\.<a name="customize-email"></a>

**To change the email address for AWS Free Tier usage alerts**

AWS sends AWS Free Tier usage alerts to the email address that you used when you created your account\. You can change the email address on the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Under **Preferences** in the navigation pane, choose ** Billing preferences**\.

1. Under **Cost Management Preferences**, under **Receive AWS Free Tier Usage Alerts** in the **Email Address** dialog box, enter the email address where you want to receive the usage alerts\.

1. Scroll to the end of the page and choose **Save preferences**\.

## Top AWS Free Tier services table<a name="free-tier-table"></a>

If you are eligible for the AWS Free Tier and you use a AWS Free Tier offering, you can track your usage with the **Top AWS Free Tier Services by Usage** table on the dashboard of the [Billing and Cost Management console](https://console.aws.amazon.com/billing/home)\. The following conditions might limit whether you see the Free Tier table data: 
+ You use an AWS service that doesn't offer a AWS Free Tier\.
+ Your AWS Free Tier has expired\.
+ You access AWS through an AWS Organizations member account\.
+ You use an AWS service in the AWS GovCloud \(US\-West\) or AWS GovCloud \(US\-East\) Regions\.

The **Top AWS Free Tier Service by Usage** table is grouped by service limit and shows the AWS Free Tier usage limit for your top five most\-used Free Tier service measurements, along with your current usage amount\. A service might have multiple lines, enabling you to track each AWS Free Tier limit closely\. The table shows usage as both a percentage of the AWS Free Tier limit and a ratio of the AWS Free Tier limit\. 

For example, each month you get 2,000 Amazon S3 `Put` operations and 5 GB of Amazon S3 storage\. The AWS Free Tier usage table has two lines, one for `S3 - Puts` and one for `S3 - Storage`\. If you use 2,000 of the Free Tier `S3 - Puts` operations, the table shows 2,000\.00/2,000 Requests and 100 percent, and if you use 0\.55 GB of the AWS Free Tier `S3 - Storage`, the table shows `0.55/5 GB` and 11 percent, as shown in the following screenshot\.

![\[Screenshot of the top free tier services by usage table, with service, usage limit, and month-to-date usage columns appearing.\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Screenshot of the top free tier services by usage table, with service, usage limit, and month-to-date usage columns appearing.\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Screenshot of the top free tier services by usage table, with service, usage limit, and month-to-date usage columns appearing.\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

To see more details about your AWS Free Tier usage, including all of your active Free Tier services, choose **View All** in the **Top AWS Free Tier Services by Usage** table\. The detailed table includes additional information such as the forecast of your usage for the month and a status icon to alert you if you have exceeded the limits or are predicted to exceed the limits\. 

![\[Screenshot of the top free tier services by usage table with all columns showing.\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Screenshot of the top free tier services by usage table with all columns showing.\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Screenshot of the top free tier services by usage table with all columns showing.\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

## Trackable AWS Free Tier services<a name="free-tier-services"></a>

AWS enables you to track how much you used AWS Free Tier services and what service usage types you used\. Usage types are the specific type of usage that AWS tracks\. For example, the usage type `Global-BoxUsage:freetier.micro` means that you used an Amazon EC2 micro instance\.

The AWS Free Tier usage alerts and the **Top AWS Free Tier Services by Usage** table cover both expiring and non\-expiring AWS Free Tier offerings\. You can track the following services and usage types\.


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