# Tracking your AWS Free Tier usage<a name="tracking-free-tier-usage"></a>

You can track your AWS Free Tier usage in the following ways:
+ Set up Free Tier alerts using AWS Budgets\. By default, AWS Budgets automatically notifies you over email when you exceed 85 percent of the Free Tier limit for each service\. You can also configure AWS Budgets to track your usage to 100 percent of the Free Tier limit\.
+ Review your AWS Free Tier usage using the **Top Free Tier Services by Usage** table in the Billing console\.

**Topics**
+ [AWS Free Tier usage alerts using AWS Budgets](#free-budget)
+ [Top AWS Free Tier services table](#free-tier-table)
+ [Trackable AWS Free Tier services](#free-tier-services)

## AWS Free Tier usage alerts using AWS Budgets<a name="free-budget"></a>

AWS Budgets allows you to track and take action on your cost and usage\. For more information about this feature, see [Managing your costs with AWS Budgets](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-managing-costs.html)\.

AWS Budgets automatically notifies you over email when you exceed 85 percent of your Free Tier limit for each service\. For additional tracking, you can set up AWS Budgets to track your usage to 100 percent of the Free Tier limit for each service\. For example, you can set up a budget to send you an alert when you’re forecasted to exceed 100 percent of the Free Tier limit for Amazon Elastic Block Store\. For instructions on how to set up a usage budget, see [Creating a usage budget](https://docs.aws.amazon.com/cost-management/latest/userguide/budgets-create.html#create-usage-budget)\.

AWS Free Tier usage alerts cover non\-expiring Free Tier offerings, such as the first 25 GB of Amazon DynamoDB storage or the first 10 custom Amazon CloudWatch metrics\. The alerts also cover AWS Free Tier offerings that expire after 12 months, such as the 750 hours per month of Amazon EC2 Windows t2\.micro instance usage and the first 5 GB of standard Amazon S3 storage\. The alerts don’t cover Free Tier offerings that expire in less than 12 months, such as the first 30 days of using Amazon Lightsail\.

When you exceed the Free Tier limit for a service, AWS sends an email to the email address that you used to create your account\. Use the following procedure to change the email address for AWS Free Tier usage alerts\.<a name="customize-email"></a>

**To change the email address for AWS Free Tier usage alerts**

1. Sign in to the AWS Management Console and open the Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Under **Preferences** in the navigation pane, choose ** Billing preferences**\.

1. Under **Cost Management Preferences**, under **Receive AWS Free Tier Usage Alerts** in the **Email Address** dialog box, enter the email address where you want to receive the usage alerts\.

1. Scroll to the end of the page and choose **Save preferences**\.

AWS Budgets usage alerts for 85 percent of the Free Tier limit are automatically activated for all individual AWS accounts, but not for a management account in an AWS Organizations\. If you own a management account, you must opt in to get AWS Free Tier usage alerts\. Use the following procedure to opt in or out of Free Tier usage alerts\.<a name="opt-in-out"></a>

**To opt in or out of AWS Free Tier usage alerts**

1. Sign in to the AWS Management Console and open the Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Under **Preferences** in the navigation pane, choose ** Billing preferences**\.

1. Under **Cost Management Preferences**, select **Receive AWS Free Tier Usage Alerts** to opt in to Free Tier usage alerts\. To opt out, clear the **Receive AWS Free Tier Usage Alerts** check box\.

## Top AWS Free Tier services table<a name="free-tier-table"></a>

If you're eligible for the AWS Free Tier and you use an AWS Free Tier offering, you can track your usage with the **Top AWS Free Tier Services by Usage** table on the dashboard of the [AWS Billing console](https://console.aws.amazon.com/billing/home)\. The dashboard shows your account's top five AWS Free Tier service measurements\.

To see more details about your AWS Free Tier usage, including all of your active Free Tier services, choose **View all** in the **Top AWS Free Tier Services by Usage** table\. The detailed table includes additional information about your forecasted usage for each Free Tier service measurement\.

The **Top AWS Free Tier Service by Usage** table is grouped by service limit\. A service might have multiple lines, enabling you to track each AWS Free Tier limit closely\. For example, each month you get 2,000 Amazon S3 `Put` operations and 5 GB of Amazon S3 storage\. The AWS Free Tier usage table has two lines, one for `S3 - Puts` and one for `S3 - Storage`\.

The following conditions might limit whether you see the Free Tier table data:
+ You use an AWS service that doesn't offer a AWS Free Tier\.
+ Your AWS Free Tier has expired\.
+ You access AWS through an AWS Organizations member account\.
+ You use an AWS service in the AWS GovCloud \(US\-West\) or AWS GovCloud \(US\-East\) Regions\.

## Trackable AWS Free Tier services<a name="free-tier-services"></a>

With AWS, you can track how much you used AWS Free Tier services and what service usage types you used\. Usage types are the specific type of usage that AWS tracks\. For example, the usage type `Global-BoxUsage:freetier.micro` means that you used an Amazon EC2 micro instance\.

The AWS Free Tier usage alerts and the **Top AWS Free Tier Services by Usage** table cover both expiring and non\-expiring AWS Free Tier offerings\. You can track the following services and usage types\.


| Service | Usage type | 
| --- | --- | 
|  Alexa Web Information Service   |  `AlexaWebInfoService::request` `AlexaWebInfoService::Requests`  | 
|  Amazon API Gateway   |  `Global-ApiGatewayRequest`  | 
|  Amazon AppStream  |  `Global-stream-hrs:720p:g2` `Global-stream.standard.large-ib`  | 
|  Amazon Cloud Directory  |  `Global-Requests-Tier1` `Global-Requests-Tier2` `Global-TimedStorage-ByteHrs`  | 
|  Amazon CloudFront  |  `Global-DataTransfer-Out-Bytes` `Global-Requests-Tier1` `Invalidations` `Execution:Executions-CloudFrontFunctions`  | 
|  Amazon CloudWatch  |  `Global-CW:Requests` `Global-TimedStorage-ByteHrs` `PutLogEvents:Global-DataProcessing-Bytes`  | 
| Amazon Cognito | Global\-CognitoUserPoolMAU | 
| Amazon Cognito Sync |  `Global-CognitoSyncOperation` `Global-TimedStorage-ByteHrs`  | 
|  Amazon Connect   |  `USE1-end-customer-mins`  | 
|  AWS CodeBuild   |  `Global-Build-Min:Linux:g1.small`  | 
|  Amazon GameLift   |  `Global-BoxUsage:c5.large`  | 
|  AWS Storage Gateway   |  `Global-Uploaded-Bytes`  | 
|  Amazon DynamoDB   |  `TimedStorage-ByteHrs` `GetRecords:AFS1-Streams-Requests`  | 
|  Amazon Elastic Compute Cloud \(Amazon EC2\)  |  `Global-BoxUsage:freetier.micro` `Global-BoxUsage:freetier.micro` `Global-DataProcessing-Bytes` `Global-EBS:SnapshotUsage` `Global-EBS:VolumeIOUsage` `Global-EBS:VolumeUsage` `Global-LCUUsage` `Global-LoadBalancerUsage`  | 
|  Amazon Elastic Container Registry \(Amazon ECR\)  |  `Global-TimedStorage-ByteHrs`  | 
|  Amazon Elastic File System   |  `Global-TimedStorage-ByteHrs`  | 
|  Amazon OpenSearch Service   |  `Global-ES:freetier-Storage` `Global-ESInstance:freetier.micro`  | 
|  Amazon Elastic Transcoder   |  `global-ets-audio-success` `Global-ets-hd-success` `Global-ets-sd-success`  | 
|  Amazon Forecast  |  `Global-DataInjection` `Global-TrainingHours`  | 
|  Amazon Fraud Detector  |  `Global-BoxUsage:c3.large` `Global-FlexMatchMatchmakingHrs` `Global-FlexMatchPlayerPackages` `Global-DailyActiveUser`  | 
|  Amazon GameLift   |  `Global-CW:Requests` `Global-DataProcessing-Bytes` `Global-TimedStorage-ByteHrs`  | 
|  Amazon GameOn  |  `API-Score-Free-Tier`  | 
|  Amazon GameSparks  |  `Global-ExecutionTime-Code` `Global-APIRequest-Blocks` `Global-APIRequest-Code` `Global-APIRequest-CodeRead` `Global-APIRequest-CodeWrite` `Global-APIRequest-Tune` `Global-Storage-Code` `Global-Storage-Content`  | 
|  Amazon IVS  |  `SUM-Global-Input-Basic-Hours` `SUM-Global-Output-SD-Hours`  | 
|  Amazon Lex  |  `Lex-Global-Speech-Requests` `Lex-Global-Text-Requests`  | 
|  Amazon LookoutVision  |  `Free-Inference` `Free-Training`  | 
|  Amazon Macie  |  `SensitiveDataDiscovery`  | 
|  Amazon MCS  |  `Global-TimedStorage-ByteHrs` `Global-ReadRequestUnits` `Global-WriteRequestUnits`  | 
|  Amazon Neptune  |  `DataTransfer-Out-Bytes`  | 
|  Amazon Pinpoint  |  `Domain-Inboxplacement` `MonthlyTargetedAudience` `Predictive-Tests`  | 
|  Amazon Personalize  |  `Global-DataIngestion` `Global-TPS-hours` `Global-TrainingHour` `Predictive-Tests` `EventsRecorded`  | 
| Amazon Polly  | Global\-SynthesizeSpeech\-Chars | 
|  Amazon Relational Database Service   |  `Global-InstanceUsage:db.t1.micro` `Global-RDS:StorageIOUsage`  | 
|  Amazon Rekognition   |  `Global-FaceVectorsStored` `Global-ImagesProcessed` `Global-inferenceminutes` `Global-MinutesOfVideoProcessed` `Global-minutestrained`  | 
|  Amazon Route 53  |  `Health-Check-AWS`  | 
|  Amazon Simple Storage Service \(Amazon S3\)  |  `Global-Requests-Tier1` `Global-Requests-Tier2` `Global-TimedStorage-ByteHrs`  | 
|  Amazon Simple Email Service   |  `Global-Message` `Global-Recipients-MailboxSim-EC2`  | 
|  Amazon Simple Notification Service \(Amazon SNS\)  |  `DeliveryAttempts-HTTP` `DeliveryAttempts-SMTP` `Requests-Tier1` `Notifications-Mobile`  | 
|  Amazon States  |  `Global-StateTransition`  | 
|  Amazon Simple Workflow Service  |  `Global-AggregateInitiatedActions` `Global-AggregateInitiatedWorkflows` `Global-AggregateWorkflowDays`  | 
|  Amazon Textract  |  `Global-PagesforAnalyzeDocTables` `Global-PagesforDocumentText`  | 
|  Amazon WorkLink  |  `WorkLink-MAU`  | 
|  Amazon TTS  |  `Global-SynthesizeSpeech-Chars`  | 
|  Amazon WorkSpaces  |  `AutoStop-Usage` `AutoStop-User`  | 
|  AWS Amplify  | `Global-BuildDuration` `Global-DataStorage`' `Global-DataTransferOut` | 
|  AWS Budgets  |  `ActionEnabledBudgetsUsage`  | 
|  AWS CodeArtifact  |  `Global-Requests` `Global-TimedStorage-ByteHrs`  | 
|  AWS CodeCommit  |  `User-Month`  | 
|    |  `Global-activePipeline`  | 
|  AWS Database Migration Service   |  `Global-InstanceUsg:dms.t2.micro` `Global-SynthesizeSpeechNeural-Characters`  | 
|  AWS DataTransfer  |  `Global-DataTransfer-Out-Bytes`  | 
|  AWS DeepRacer  |  `TimedStorage-GigabyteHrs`  | 
|  AWS Glue  |  `Global-Catalog-Request` `Global-Catalog-Storage`  | 
|  AWS IoT   |  `AWSIoT-messages`  | 
|  AWS KMS  |  `Global-KMS-Requests`  | 
|  AWS Lambda   |  `Global-Lambda-GB-Second` `Global-Request`  | 
|  Amazon SQS  |  `Global-Requests`  | 
|  AWS X\-Ray   |  `Global-XRay-TracesAccessed` `Global-XRay-TracesStored`  | 
|  AWS Storage Gateway  |  `Global-Uploaded-Bytes`  | 
|  AWS CodeBuild  |  `Global-Build-Min:Linux:g1.small`  | 
|  Amazon Comprehend  |  `Global-Comprehend-DC-Custom` `Global-Comprehend` `Global-Comprehend-Syntax` `Global-DetectEvents` `Global-DetectPiiEntities` `Global-DetectTopics`  | 
|  Amazon Comprehend Medical  |  `Global-CompMed-DetectEntities` `Global-CompMed-DetectPHI`  | 
|  ContactCenterTelecomm   |  `USE1-US-did-inbound-mins` `USE1-US-outbound-mins` `USE1-US-tollfree-inbound-mins`  | 
| ContactLensAmazonConnect | `ChatAnalytics:Global-ChatAnalytics` `VoiceAnalytics:Global-VoiceAnalytics` | 
|  AWS IoT Device Defender  |  `global-Detect`  | 
| AWS IoT Device Management |  `global-JobExecutions`  | 
|  Amazon Mobile Analytics  |  `EventsRecorded`  | 
|  AWS OpsWorks   |  `OpsWorks-Chef-Automate`  | 