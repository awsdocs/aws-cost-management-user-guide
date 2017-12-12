# Monitoring Charges with Alerts and Notifications<a name="monitor-charges"></a>

You can monitor your AWS costs by using CloudWatch\. With CloudWatch, you can create billing alerts that notify you when your usage of your services exceeds thresholds that you define\. You specify these threshold amounts when you create the billing alerts\. When your usage exceeds these amounts, AWS sends you an email notification\. You can also sign up to receive notifications when AWS prices change\.

 To create billing alerts and register for notifications, you must first enable them in the Billing and Cost Management console by using the following procedure\. 

**Note**  
If your account is linked to a reseller account, billing alerts are not available for your account\.

**To enable billing alerts**

Before you create a billing alarm, you must enable billing alerts\. You need to do this only once\. After you enable billing alerts, you can't turn them off\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. On the navigation pane, choose **Preferences**\.

1. Select the **Receive Billing Alerts** check box\.

1. Choose **Save preferences**\.

After you enable billing alerts, you can set them up and subscribe to notifications by using the following procedure\. 

**To create a billing alarm**

1. \(Optional\) If you want to send your alert to an AWS\-managed distribution list instead of a single email address, follow these steps to set up an Amazon Simple Notification Service \(Amazon SNS\) notification list\. If you want to send your alert to a single email address, go to step 2\.

   To create an Amazon SNS notification list:

   1. Open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v2/home](https://console.aws.amazon.com/sns/v2/home)\.

   1. On the navigation pane, choose **SNS Home**\.

   1. In the **Common actions** section, choose **Create topic**\.

   1. In the dialog box, for **Topic name**, enter the name for your notification list\.

   1. \(Optional\) If you want to use this notification list to send SMS messages, for **Display name**, enter the name you want to appear on your SMS messages\.

   1. Choose **Create topic**\.

1. Open the CloudWatch console at [https://console\.aws\.amazon\.com/cloudwatch/](https://console.aws.amazon.com/cloudwatch/)\.

1. If necessary, change the region on the navigation bar to US East \(N\. Virginia\)\. The billing metric data is stored in this region, even for resources in other regions\.

1. On the navigation pane, under **Metrics**, choose **Billing**\.

1. In the list of billing metrics, select the check box next to **Currency** `USD`, for the metric named **EstimatedCharges**\.

1. Choose **Create Alarm**\.

1. Define the alarm as follows\.

   1. If you want the alarm to trigger as soon as you go over the free tier, set **When my total AWS charges for the month exceed** to $\.01\. This means that you'll receive a notification as soon as you incur a charge\. Otherwise, set it to the amount you want to trigger the alarm, and you will be notified when you go over that amount\. 

   1. Choose the **New list** link next to the **send a notification to** box\.

   1. When prompted, enter your email address or choose your Amazon SNS notification from the drop down\.

   1. Choose **Create Alarm**\.

1. In the **Confirm new email addresses** dialog box, confirm the email address or choose **I will do it later**\. If you don't confirm the email address now, the alarm remains in the `Pending confirmation` status until you do so, and does not send an alert\. To view the status of your alarm, choose **Alarms** in the navigation pane\.

**To sign up for price update notifications**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v2/home](https://console.aws.amazon.com/sns/v2/home)\.

1. If you are new to Amazon SNS, choose **Get Started**\.

1. If necessary, change the region on the navigation bar to US East \(N\. Virginia\)\. The billing metric data is stored in this region, even for resources in other regions\.

1. On the navigation pane, choose **Subscriptions**\.

1. Choose **Create Subscription**\.

1. For **Topic ARN**, if you want to be notified every time a price changes, enter `arn:aws:sns:us-east-1:278350005181:price-list-api`\. If you want to be notified about price changes once a day, enter `arn:aws:sns:us-east-1:278350005181:daily-aggregated-price-list-api` instead\.

1. For **Protocol**, use the default `HTTP` setting\.

1. For **Endpoint**, choose the format that you want to receive the notification in, such as SQS, Lambda, or email\.

1. Choose **Create Subscription**\.