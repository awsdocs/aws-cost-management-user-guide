# Configuring AWS Budgets controls<a name="budgets-controls"></a>

You can use AWS Budgets to configure cost savings controls, or actions, that run either automatically on your behalf or by using a workflow approval process\. You can use actions to define an explicit response that you want to take when a budget exceeds its action threshold\. You can trigger these alerts on actual or forecasted cost and usage budgets\.

Your available actions include applying an IAM policy or a service control policy \(SCP\), or targeting specific Amazon EC2 or Amazon RDS instances in your account\. You can use SCPs so that you can no longer provision any new resources during the budgeted period\.

**Note**  
From the management account, you can apply an SCP to another account\. However, you can't target Amazon EC2 or Amazon RDS running resources in another account\.

You can also configure multiple actions to trigger at the same notification threshold\. For example, you can configure actions to trigger automatically when you reach 90 percent of your forecasted costs for the month\. To do so, perform the following actions:
+ Apply a custom `Deny IAM` policy that limits the ability for a user, group, or role to provision additional Amazon EC2 resources\.
+ Target specific Amazon EC2 instances in `US East (N. Virginia) us-east-1`\.

To configure a budget action, first follow the process for [Creating a cost budget](budgets-create.md#create-cost-budget) or [Editing a budget](budgets-edit.md), and select **Configure thresholds**\.

**To configure a budget action**

1. Under **Configure thresholds**, choose the one of the following options:
   + **Actual** \- This creates a notification for your actual spend\.
   + **Forecast** \- This creates a notification for your forecasted spend\.

1. Under **Alert threshold**, enter the amount \(absolute value or percentage\) you want to be notified at\.

   For example, your budget is $200 and you want to be notified at $160\. Enter `160` as your absolute value, or `80` as your percentage\.

1. Choose either **Absolute amount** or **% of budgeted amount**:
   + **Absolute amount** \- You are notified when the threshold amount has passed\.
   + **% of budgeted amount** \- You are notified when the threshold percentage of the budget has passed\.

1. \(Optional\) For **SNS topic ARN**, enter the Amazon Resource Name \(ARN\) for your Amazon SNS topic, and then choose **Verify**\. If you want to use an Amazon SNS topic for your notification but don't have one, see [Creating an Amazon SNS topic](https://docs.aws.amazon.com/sns/latest/dg/CreateTopic.html) in the *Amazon Simple Notification Service Developer Guide*\.

   AWS verifies that your budget has permission to send notifications to your Amazon SNS topic by sending a test email to your Amazon SNS topic\. If the Amazon SNS topic ARN is valid but the **Verify** step fails, check the Amazon SNS topic policy to make sure that it allows your budget to publish to that topic\. 

   For a sample policy and instructions on granting your budget permissions, see [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)\. A notification can be subscribed to only one Amazon SNS topic\.

   To receive a notification, you must specify an email address\. You can also specify an Amazon SNS topic\.

1. \(Optional\) Choose **Add a budget action**\.

   1. Configure your notification settings for your action\. This defaults to the same notification settings created in [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)\.

   1. In the **Choose your budget action** section, choose an IAM role to allow AWS Budgets to perform an action on your behalf\.
**Note**  
If you don't have proper permissions configured and assigned for the user and for AWS Budgets, AWS Budgets can't execute your configured actions\. To ensure proper configuration and execution, we've provided managed policies so your AWS Budgets actions work as intended\. We recommend you use these IAM policies to be sure you don't have to update your existing IAM policy for AWS Budgets when a new functionality is included\. We will add new capabilities to the managed policy by default\. For details about managed policies, see [Managed policies](billing-permissions-ref.md#managed-policies)\.

      For more information and examples for IAM role permissions, see [Billing and Cost Management actions policies](billing-permissions-ref.md#user-permissions)\.

   1. Choose the action type you want AWS Budgets to apply on your behalf\.

      You can choose from applying an IAM policy, a service control policy \(SCP\), or targeting specific Amazon EC2 or Amazon RDS instances\. You can apply multiple budget actions to a single threshold\. Only a management account can apply SCPs\.

   1. Choose whether you want to run these actions automatically or through a workflow approval process\. The workflow approval is set as your default experience\.

1. Choose **Confirm budget**\.

1. Review your budget settings, and choose **Create**\.

After you create an action, you can view the status of your actions from the **Budgets dashboard** using the **Actions** column\. This column shows your configured actions count, actions waiting for your approval \(*pending actions*\), and your successfully completed actions\.

## Reviewing and approving your budget action<a name="budgets-action-review"></a>

You receive a notification to inform that an action is pending or has already run on your behalf, regardless of your action preferences\. The notification includes a link to the **Budget details** page of the action in question\. You can also navigate to the **Budget details** page by choosing the budget name on the **Budget dashboard**\.

On the **Budget details** page, you can review and approve your budget action\.

**To review and approve your budget action**

1. Choose **More info** on a threshold with an associated action\.

1. Review the notification details on the **Action** page\.
   + **Pending actions** \- This lists actions waiting on your approval\. This appears only if you have pending actions\.
   + **Expand** \- Expand the action to see the action details \(for example, action type or tasks\)\.

1. Choose **Execute action**\.

1. Choose **Yes**\.

Your pending actions move from the `pending` status in **Action history**, listing the newest actions at the top\. AWS Budgets shows actions configured and run in the last 60 days\. For a full actions history, you can view the information using AWS CloudTrail, or by calling the `DescribeBudgetActionHistories` API\.

### Reversing a previous action<a name="budgets-action-undo"></a>

You can review and undo previously completed actions from the **Action history** table\. Each status is defined as follows:
+ **Standby** \- AWS Budgets is actively evaluating the action\.
+ **Pending** \- The action is triggered, and is waiting for your approval\.
+ **Execution success** \- The action successfully completed\.
+ **Reverse success** \- You chose to undo the action\. AWS Budgets will no longer evaluate the action for the remaining budgeted period\.

If you want AWS Budgets to reevaluate the reversed action during the same period, you can choose **reset action**\. For example, you triggered a read\-only policy but then got approval from your manager to increase your budget and adjust your budgeted amount during the current period\.