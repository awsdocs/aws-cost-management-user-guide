# Setting up notifications<a name="price-notification"></a>

You can sign up to receive notifications when AWS prices change, such as when AWS cuts prices, when new instance types are launched, or when new services are introduced\. You can sign up to be notified every time a price changes or once a day\. If you sign up to be notified once a day, the notification includes all price changes applied during that day\.

You can use the console to sign up for Amazon SNS notifications\.<a name="price-change-notification-1"></a>

**To sign up for price update notifications**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v3/home](https://console.aws.amazon.com/sns/v3/home)\.

1. If you are new to Amazon SNS, choose **Get Started**\.

1. If necessary, change the Region on the navigation bar to **US East \(N\. Virginia\)**\.

1. On the navigation pane, choose **Subscriptions**\.

1. Choose **Create Subscription**\.

1. For **Topic ARN**, do the following as appropriate:
   + For service pricing – If you want to be notified every time a price changes, enter `arn:aws:sns:us-east-1:278350005181:price-list-api`\. If you want to be notified about price changes once a day, enter `arn:aws:sns:us-east-1:278350005181:daily-aggregated-price-list-api` instead\.
   + For Savings Plans prices – Enter `arn:aws:sns:us-east-1:626627529009:SavingsPlanPublishNotifications`\.

1. For **Protocol**, use the default `HTTP` setting\.

1. For **Endpoint**, choose the format that you want to receive the notification in, such as Amazon SQS, Lambda, or email\.

1. Choose **Create Subscription**\.

**Important**  
If you get an error message Couldn't create subscription\. Error code: InvalidParameter \- Error message: Invalid parameter: TopicArn, it's likely that your Region is not set to **US East \(N\. Virginia\)**\. The billing metric data is stored in this Region, even for resources in other Regions\. Repeat the process with close attention to step 3\.