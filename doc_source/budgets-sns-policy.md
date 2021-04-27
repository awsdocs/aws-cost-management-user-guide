# Creating an Amazon SNS topic for budget notifications<a name="budgets-sns-policy"></a>

When you create a budget that sends notifications to an Amazon Simple Notification Service \(Amazon SNS\) topic, you need to either have a preexisting Amazon SNS topic or create one\. Amazon SNS topics allow you to send notifications over SNS in addition to email\. Your budget must have permissions to send a notification to your topic\. 

To create an Amazon SNS topic and grant permissions to your budget, use the Amazon SNS console\.

**To create an Amazon SNS notification topic and grant permissions**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v3/home](https://console.aws.amazon.com/sns/v3/home)\.

1. On the navigation pane, choose **Topics**\.

1. Choose **Create topic**\.

1. For **Name**, enter the name for your notification topic\.

1. \(Optional\) For **Display name**, enter the name that you want displayed when you receive a notification\.

1. In **Access policy**, choose **Advanced**\.

1. In the policy text field, after ** "Statement": \[**, add the following text:

   ```
       
   {
     "Sid": "E.g., AWSBudgetsSNSPublishingPermissions",
     "Effect": "Allow",
     "Principal": {
       "Service": "budgets.amazonaws.com"
     },
     "Action": "SNS:Publish",
     "Resource": "your topic ARN"
   },
   ```

1. Replace **E\.g\., AWSBudgetsSNSPublishingPermissions** with a string\. The `Sid` must be unique within the policy\.

1. Choose **Create topic**\.

1. Under **Details**, save your ARN\.

1. Choose **Edit**\.

1. Under **Access policy**, replace *your topic ARN* with the Amazon SNS topic ARN from step 10\.

1. Choose **Save changes**\.

   Your topic now appears in the list of topics on the **Topics** page\.

## Troubleshooting<a name="budgets-sns-troubleshoot"></a>

You might encounter the following error messages when you’re creating your Amazon SNS topic for budget notifications\.

**Please comply with SNS ARN format**  
There’s a syntax error in the ARN you replaced \(step 9\)\. Confirm the ARN for proper syntax and formatting\.

**Invalid SNS topic**  
AWS Budgets doesn’t have access to the SNS topic\. Confirm that you’ve allowed budgets\.amazonaws\.com the ability to publish messages to this SNS topic, in the SNS topic’s resource based policy\.

**The SNS topic is encrypted**  
You have **encryption** enabled on the SNS topic\. The SNS topic won’t work without additional permissions\. Disable encryption on the topic, and refresh the **Budget edit** page\. 

## Checking or resending notification confirmation emails<a name="budgets-confirm-subscription"></a>

When you create a budget with notifications, you also create Amazon SNS notifications\. For notifications to be sent, you must accept the subscription to the Amazon SNS notification topic\.

To confirm that your notification subscriptions have been accepted or to resend a subscription confirmation email, use the Amazon SNS console\.

**To check your notification status or to resend a notification confirmation email**

1. Sign in to the AWS Management Console and open the Amazon SNS console at [https://console\.aws\.amazon\.com/sns/v3/home](https://console.aws.amazon.com/sns/v3/home)\.

1. On the navigation pane, choose **Subscriptions**\.

1. On the **Subscriptions** page, for **Filter**, enter `budget`\. A list of your budget notifications appears\.

1. Check the status of your notification\. Under **Status**, `PendingConfirmation` appears if a subscription hasn't been accepted and confirmed\.

1. \(Optional\) To resend a confirmation request, select the subscription with a pending confirmation and choose **Request confirmation**\. Amazon SNS sends a confirmation request to the endpoints that are subscribed to the notification\.

   When each owner of an endpoint receives the email, they must choose the **Confirm subscription** link to activate the notification\.

## Protecting your Amazon SNS budget alerts data with SSE and AWS KMS<a name="protect-sns-sse"></a>

You can use server\-side encryption \(SSE\) to transfer sensitive data in encrypted topics\. SSE protects Amazon SNS messages by using keys managed in AWS Key Management Service \(AWS KMS\)\.

To manage SSE using AWS Management Console or the AWS Service Development Kit \(SDK\), see [Enabling Server\-Side Encryption \(SSE\) for an Amazon SNS Topic](https://docs.aws.amazon.com/sns/latest/dg/sns-tutorial-enable-encryption-for-topic.html) in the *Amazon Simple Notification Service Getting Started Guide*\.

To create encrypted topics using AWS CloudFormation, see the [AWS CloudFormation User Guide](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html)\.

SSE encrypts messages as soon as Amazon SNS receives them\. The messages are stored encrypted and are decrypted using Amazon SNS only when they're sent\.

### Configuring AWS KMS permissions<a name="configure-kms-perm"></a>

You must configure your AWS KMS key policies before you can use SSE\. The configuration enables you to encrypt topics, as well as encrypt and decrypt messages\. For details about AWS KMS permissions, see [AWS KMS API Permissions: Actions and Resources Reference](https://docs.aws.amazon.com/kms/latest/developerguide/kms-api-permissions-reference.html) in the *AWS Key Management Service Developer Guide*\.

You can also use IAM policies to manage AWS KMS key permissions\. For more information, see [Using IAM Policies with AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/iam-policies.html)\.

**Note**  
Although you can configure global permissions to send and receive message from Amazon SNS, AWS KMS requires you to name the full ARN of AWS KMS keys \(KMS key\) in the specific Regions\. You can find this in the **Resource** section of an IAM policy\.  
You must ensure that the key policies of the KMS keys allow the necessary permissions\. To do this, name the principals that produce and consume encrypted messages in Amazon SNS as users in the KMS key policy\.<a name="enable-compatiblility"></a>

**To enable compatibility between AWS Budgets and encrypted Amazon SNS topics**

1. [Create a KMS key](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html#create-keys-console)\.

1. Add the following text to the KMS key policy\.

   ```
       
       {
       "Version": "2012-10-17",
       "Statement": [{
           "Effect": "Allow",
           "Principal": {
               "Service": "budgets.amazonaws.com"
           },
       "Action": [
           "kms:GenerateDataKey*",
           "kms:Decrypt"
           ],
       "Resource": "*"
       }]
       }
   ```

1. [Enable SSE for your SNS topic](https://docs.aws.amazon.com/sns/latest/dg/sns-tutorial-enable-encryption-for-topic.html)\.
**Note**  
Be sure that you're using the same KMS key that grants AWS Budgets the permissions to publish to encrypted Amazon SNS topics\.

1. Choose **Save Changes**\.