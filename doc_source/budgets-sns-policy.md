# Creating an Amazon SNS Topic for Budget Notifications<a name="budgets-sns-policy"></a>

When you create a budget that sends notifications to an Amazon Simple Notification Service \(Amazon SNS\) topic, you need to either have a pre\-existing Amazon SNS topic or create an Amazon SNS topic\. Amazon SNS topics allow you to send notifications over SMS in addition to email\. Your budget must have permissions to send a notification to your topic\. 

To create an Amazon SNS topic and grant permissions to your budget, use the Amazon SNS console\.

**To create an Amazon SNS notification topic and grant permissions**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v2/home](https://console.aws.amazon.com/sns/v2/home)\.

1. On the navigation pane, choose **Topics**\.

1. On the **Topics** page, choose **Create new topic**\.

1. In the dialog box, for **Topic name**, type the name for your notification topic\.

1. In the dialog box, for **Display name**, type the name that you want displayed when you receive a notification\.

1. Choose **Create topic**\. Your topic appears in the list of topics on the **Topics** page\.

1. Select your topic, and copy the ARN next to your topic name\.  
![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

1. For **Actions**, choose **Edit topic policy**\.

1. In the dialog box, choose **Advanced view**\.

1. In the policy text field, after ** "Statement": \[**, add the following text:

   ```
       
   {
     "Sid": "ExampleSid123456789012",
     "Effect": "Allow",
     "Principal": {
       "Service": "budgets.amazonaws.com"
     },
     "Action": "SNS:Publish",
     "Resource": "your topic ARN"
   }
   ```

1. Replace **ExampleSid123456789012** with a string\. The Sid must be unique within the policy\.

1. Replace *your topic ARN* with the Amazon SNS topic ARN from step seven\.

1. Choose **Update policy**\. This grants your budget permissions to publish to your topic\.

You can now use the Amazon SNS topic ARN to set up Amazon SNS notifications for a budget\.

## Checking or Resending Notification Confirmation Emails<a name="budgets-confirm-subscription"></a>

When you create a budget with notifications, you also create Amazon Simple Notification Service \(Amazon SNS\) notifications\. In order for notifications to be sent, you must accept the subscription to the Amazon SNS notification topic\.

To confirm that your notification subscriptions have been accepted or to resend a subscription confirmation email, use the Amazon SNS console\.

**To check your notification status or to resend a notification confirmation email**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v2/home](https://console.aws.amazon.com/sns/v2/home)\.

1. On the navigation pane, choose **Subscriptions**\.

1. On the **Subscriptions** page, for **Filter**, enter `budget`\. A list of your budget notifications appears\.

1. Under **Subscription ARN**, you will see `PendingConfirmation` if a subscription has not been accepted\. If you do not see a `PendingConfirmation`, all of your budget notifications have been activated\.

1. \(Optional\) To resend a confirmation request, select the subscription with a pending confirmation, and choose **Request confirmations**\. Amazon SNS will send a confirmation request to the email addresses that are subscribed to the notification\.

   1. When each owner of an email address receives the email, they must choose the **Confirm subscription** link to activate the notification\.