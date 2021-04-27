# Receiving budget alerts in Amazon Chime and Slack<a name="sns-alert-chime"></a>

You can receive your AWS Budgets alerts in Amazon Chime and Slack by using AWS Chatbot\.

AWS Chatbot enables you to receive AWS Budgets alerts directly into your designated Slack channel or Amazon Chime chat room\.<a name="receive-alerts-chime"></a>

**To begin receiving your budget alerts in Slack and Amazon Chime**

1. Follow [Creating a budget](budgets-create.md) or [Editing a budget](budgets-edit.md) and select **Configure alerts**\.

1. Add an Amazon SNS topic as an alert recipient to a specific alert or alerts\. To ensure that AWS Budgets has permissions to publish to your Amazon SNS topics, see [Creating an Amazon SNS Topic for Budget Notifications](budgets-sns-policy.md)\.

1. Select **Confirm Budget**\.

1. Select **Done**\.

1. Open the [AWS Chatbot console](https://us-east-2.console.aws.amazon.com/chatbot/home?region=us-east-2#/chat-clients)\.

1. Select your chat client\.

1. Choose **Configure**\.

   There are specific authorization processes for each endpoint: for example, Slack channel, Amazon Chime rooms, AWS Chatbot IAM permissions, and SNS topics receiving the budget alerts\.

1. Choose **Slack workspace**\.

1. Choose a **channel type**\.
   + **Public**: Everyone in your workspace can see or join the channel
   + **Private**: The channel is viewable only by invitation

1. Either select an existing IAM role for AWS Chatbot to assign or create a new IAM role\.

1. Choose a **role name**\.

1. Select the Amazon SNS Region\.

1. Select the **SNS topic**\.
**Note**  
You can send AWS Budgets alerts to multiple Amazon SNS topics and Regions\.  
At least one of the Amazon SNS topics must match the Amazon SNS topic or topics of your budget or budgets\.

1. Select **Configure**\.
