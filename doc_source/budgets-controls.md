# Configuring AWS Budgets actions<a name="budgets-controls"></a>

You can use AWS Budgets to run an action on your behalf when a budget exceeds a certain cost or usage threshold\. To do this, after you set a threshold, configure a budget action to run either automatically or after your manual approval\.

Your available actions include applying an IAM policy or a service control policy \(SCP\)\. They also include targeting specific Amazon EC2 or Amazon RDS instances in your account\. You can use SCPs so that you don't need to provision any new resources during the budget period\.

**Note**  
From the management account, you can apply an SCP to another account\. However, you can't target Amazon EC2 or Amazon RDS instances in another account\. 

You can also configure multiple actions to initiate at the same notification threshold\. For example, you can configure actions to initiate automatically when you reach 90 percent of your forecasted costs for the month\. To do so, perform the following actions:
+ Apply a custom `Deny IAM` policy that restricts the ability for a user, group, or role to provision additional Amazon EC2 resources\.
+ Target specific Amazon EC2 instances in `US East (N. Virginia) us-east-1`\.

## Setting up a role for AWS Budgets to run budget actions<a name="budgets-action-role"></a>

To use budget actions, you must create a service role for AWS Budgets\.  A service role is an [IAM role](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html) that a service assumes to perform actions on your behalf\. An IAM administrator can create, modify, and delete a service role from within IAM\. For more information, see [Creating a role to delegate permissions to an AWS service](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create_for-service.html) in the *IAM User Guide*\. 

To allow AWS Budgets to perform actions on your behalf, you must grant the necessary permissions to the service role\. The following table lists the permissions that you can grant the service role\.


| Permissions policy for budget actions | Instructions | 
| --- | --- | 
|  [Allows AWS Budgets broad permission to control AWS resources](https://docs.aws.amazon.com/cost-management/latest/userguide/billing-permissions-ref.html#budget-managedIAM-SSM) in the *AWS Cost Management user guide*  |  This is an AWS managed policy\. For instructions on how to attach a managed policy, see [To use a managed policy as a permissions policy for an identity \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#access_policies_manage-attach-detach-console) in the *IAM User Guide*  | 
|  [Managed policies](https://docs.aws.amazon.com/cost-management/latest/userguide/billing-permissions-ref.html#managed-policies) in the *AWS Cost Management user guide*  |  You can use this example policy as an inline policy or a customer managed policy\. For instructions on how to embed an inline policy, see [To embed an inline policy for a user or role \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#embed-inline-policy-console) in the *IAM User Guide*\. For instructions on how to create a customer managed policy, see [Creating IAM policies \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html) in the *IAM User Guide*\.  | 
|  [Managed policies](https://docs.aws.amazon.com/cost-management/latest/userguide/billing-permissions-ref.html#managed-policies) in the *AWS Cost Management user guide*  |  You can use this example policy as an inline policy or a customer managed policy\. For instructions on how to embed an inline policy, see [To embed an inline policy for a user or role \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_manage-attach-detach.html#embed-inline-policy-console) in the *IAM User Guide*\. For instructions on how to create a customer managed policy, see [Creating IAM policies \(console\)](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create-console.html) in the *IAM User Guide*\.  | 

## Configuring a budget action<a name="budgets-action-configure"></a>

You can attach budget actions to an alert for either a cost budget or a usage budget\. To configure a budget action on a new budget, first follow the steps for [Creating a cost budget](budgets-create.md#create-cost-budget) or [Creating a usage budget](budgets-create.md#create-usage-budget)\. To configure a budget action on an existing cost or usage budget, first follow the steps for [Editing a budget](budgets-edit.md)\. Then, after you reach the **Configure alerts** step of creating or editing the budget, use the following procedure\.<a name="create-budget-action"></a>

**To configure a budget action**

1. To configure a budget action on a new alert, choose **Add an alert threshold**\. To configure a budget action on an existing alert, skip to step 7\.

1. Under **Set alert threshold**, for **Threshold**, enter the amount that needs to be reached for you to be notified\. This can be either an absolute value or a percentage\. For example, say you have a budget of 200 dollars\. To be notiﬁed at 160 dollars \(80% of your budget\), enter **160** for an absolute budget or **80** for a percentage budget\.

   Next to the amount, choose **Absolute value** to be notiﬁed when your costs exceed the threshold amount\. Or, choose **% of budgeted amount** to be notiﬁed when your costs exceed the threshold percentage\.

   Next to the threshold, choose **Actual** to create an alert for actual spend\. Or, choose **Forecasted** to create an alert for forecasted spend\.

1. \(Optional\) Under **Notification preferences \- Optional**, for **Email recipients**, enter the email addresses that you want the alert to notify\. Separate multiple email addresses with commas\. A notification can have up to 10 email addresses\.

1. \(Optional\) Under **Notification preferences \- Optional**, for **Amazon SNS Alerts**, enter the Amazon Resource Name \(ARN\) for your Amazon SNS topic\. For instructions on how to create a topic, see [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)\.
**Important**  
After you create a budget with Amazon SNS notifications, Amazon SNS sends a confirmation email to the email addresses that you specified\. The subject line is **AWS Notification \- Subscription Confirmation**\. The recipient must choose **Confirm subscription** in the confirmation email to receive future notifications\.

1. \(Optional\) Under **Notification preferences \- Optional**, for **AWS Chatbot Alerts**, you can configure AWS Chatbot to send budget alerts to an Amazon Chime or Slack chat room\. You configure these alerts through the AWS Chatbot console\.

1. Choose **Next**\.

1. For **Attach actions \- Optional**, choose **Add Action**\.

   1. For **Select IAM role**, choose an IAM role to allow AWS Budgets to perform an action on your behalf\.
**Note**  
If you didn't configure and assign the appropriate permissions for the IAM role and for AWS Budgets, then AWS Budgets can't run your configured actions\. For simplified permissions management, we recommend that you use the managed policy\. This ensures that your AWS Budgets actions work as intended and eliminates the need to update your existing IAM policy for AWS Budgets whenever any new functionality is added\. This is because new functions and capabilities are added to the managed policy by default\. For more information about managed policies, see [Managed policies](billing-permissions-ref.md#managed-policies)\.

       For more information and examples of IAM role permissions, see [Managed policies](https://docs.aws.amazon.com/cost-management/latest/userguide/billing-permissions-ref.html#managed-policies) in the *AWS Cost Management user guide*\.

   1. For **Which action type should be applied when the budget threshold has been exceeded**, select the action that you want AWS Budgets to take on your behalf\.

      You can choose from applying an IAM policy, attaching a service control policy \(SCP\), or targeting speciﬁc Amazon EC2 or Amazon RDS instances\. You can apply multiple budget actions to a single alert\. Only a management account can apply SCPs\.

   1. Depending on the action that you chose, complete the fields related to the resources that you want to apply the action to\.

   1. For **Do you want to automatically run this action when this threshold is exceeded**, choose **Yes** or **No**\. If you choose **No**, then you run the action manually on the **Alert details** page\. For instructions, see [Reviewing and approving your budget action](#budgets-action-review)\.

   1. For **How do you want to be alerted when this action is run**, choose **Use the same alert settings when you defined this threshold** or **Use different alert settings**\. To use different alert settings, complete the **Notification preferences** specific to this action\.

1. Choose **Next**\.
**Note**  
To proceed, you must configure at least one of the following for each alert:  
An email recipient for notifications
An Amazon SNS topic for notifications
A budget action

1. Review your budget settings, and then choose **Create budget** or **Save**\.

After you create an action, you can view its status from the AWS Budgets page on the **Actions** column\. This column shows your configured actions count, actions waiting for your approval \(**Requires approval**\), and your successfully completed actions\.

## Reviewing and approving your budget action<a name="budgets-action-review"></a>

You receive a notification to inform you that an action is pending or has already run on your behalf, regardless of your action preferences\. The notification includes a link to the **Budget details** page of the action\. You can also navigate to the **Budget details** page by choosing the budget name on the AWS Budgets page\.

On the **Budget details** page, you can review and approve your budget action\.<a name="approve-budget-action"></a>

**To review and approve your budget action**

1. On the **Budget details** page, in the **Alerts** section, choose **Requires approval**\.

1. In the **Actions** pop\-up, choose the name of the alert that requires an action\.

1. On the **Alert details** page, in the **Action** section, review the action that requires approval\.

1. Select the action that you want to run, and then choose **Run action**\.

1. Choose **Yes, I am sure**\.

Your pending actions move from the `pending` status in **Action history**, listing the newest actions at the top\. AWS Budgets shows actions configured and run in the last 60 days\. You can view the full history of actions by using AWS CloudTrail or by calling the `DescribeBudgetActionHistories` API\.

### Reversing a previous action<a name="budgets-action-undo"></a>

You can review and undo previously completed actions from the **Action history** table\. Each status is defined as follows:
+ **Standby** \- AWS Budgets is actively evaluating the action\.
+ **Requires approval** \- The action was initiated, and is waiting for your approval\.
+ **Completed** \- The action successfully completed\.
+ **Reversed** \- The action was undone, and AWS Budgets will no longer evaluate the action for the remaining budgeted period\.

If you want AWS Budgets to re\-evaluate the reversed action during the same period, you can choose **Reset**\. You can do this, for example, if you initiated a read\-only policy but then received approval from your manager to increase your budget and adjust your budgeted amount during the current period\.