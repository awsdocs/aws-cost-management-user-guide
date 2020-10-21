# Best practices for AWS Budgets<a name="budgets-best-practices"></a>

Note the following best practices when you're working with budgets\.

**Topics**
+ [Best practices for controlling access to AWS Budgets](#budgets-best-practices-access)
+ [Best practices for budget actions](#budgets-best-practices-actions)
+ [Best practices for setting budgets](#budgets-best-practices-setting-budgets)
+ [Best practices for using the advanced options when setting cost budgets](#budgets-best-practices-cost-budgets)
+ [Understanding the AWS Budgets update frequency](#budgets-best-practices-updates)
+ [Best practices for setting budget alerts](#budgets-best-practices-alerts)
+ [Best practices for setting budget alerts using Amazon SNS topics](#budgets-best-practices-alerts-sns-topics)

## Best practices for controlling access to AWS Budgets<a name="budgets-best-practices-access"></a>

To allow IAM users to create budgets in the AWS Billing and Cost Management console, you must also allow IAM users to do the following:
+ View your billing information
+ Create Amazon CloudWatch alarms
+ Create Amazon Simple Notification Service \(Amazon SNS\) notifications

To learn more about giving users the ability to create budgets on the AWS Budgets console, see [Allow IAM users to create budgets](billing-example-policies.md#example-billing-allow-createbudgets)\.

You can also create budgets programmatically using the Budgets API\. When configuring access to the Budgets API, we recommend creating a unique IAM user for allowing programmatic access\. This helps you define more precise access controls between who in your organization has access to the AWS Budgets console and the API\. To give multiple IAM users query access to the Budgets API, we recommend creating a programmatic access IAM role for each of them\.

## Best practices for budget actions<a name="budgets-best-practices-actions"></a>

### Using managed policies<a name="budgets-best-practices-actions-policies"></a>

There are two AWS managed policies to help get you started with budget actions\. One for the user, and the other for budgets\. These policies are related\. The first policy ensures a user can pass a role to the budgets service, and the second allows budgets to execute the action\.

If you don't have proper permissions configured and assigned for the user and for AWS Budgets, AWS Budgets can't execute your configured actions\. To ensure proper configuration and execution, we've configured these managed policies so your AWS Budgets actions work as intended\. We recommend you use these IAM policies to be sure you don't have to update your existing IAM policy for AWS Budgets when a new functionality is included\. We will add new capabilities to the managed policy by default\.

For details about managed policies, see [Managed policies](billing-permissions-ref.md#managed-policies)\.

To learn more about AWS Budgets actions, see the [Configuring AWS Budgets controls](budgets-controls.md) section\.

### Using Amazon EC2 Auto Scaling<a name="budgets-best-practices-actions-auto"></a>

If a budget action is used to stop an Amazon EC2 instance in an Auto Scaling group, Amazon EC2 Auto Scaling restarts the instance, or launches new instances to replace the stopped instance\. Therefore, budget actions is not effective to control cost in this use case\.

## Best practices for setting budgets<a name="budgets-best-practices-setting-budgets"></a>

Use AWS Budgets to set custom budgets based on your costs, usage, reservation utilization, and reservation coverage\.

With AWS Budgets, you can set budgets on a recurring basis or for a specific time frame\. However, we recommend setting your budget on a recurring basis so that you don't unexpectedly stop receiving budget alerts\.

## Best practices for using the advanced options when setting cost budgets<a name="budgets-best-practices-cost-budgets"></a>

Cost budgets can be aggregated by unblended costs, amortized costs, or blended costs\. Cost budgets can also either include or exclude refunds, credits, upfront reservation fees, recurring reservation charges, non\-reservation subscription costs, taxes, and support charges\.

## Understanding the AWS Budgets update frequency<a name="budgets-best-practices-updates"></a>

AWS billing data, which Budgets uses to monitor resources, is updated at least once per day\. Keep in mind that budget information and associated alerts are updated and sent according to this data refresh cadence\.

## Best practices for setting budget alerts<a name="budgets-best-practices-alerts"></a>

Budget alerts can be sent to up to 10 email addresses and one Amazon SNS topic per alert\. You can set budgets to alert against either actual values or forecasted values\.

Actual alerts are only sent out once per budget, per budget period, when a budget first reached the actual alert threshold\.

Forecast\-based budget alerts are sent out on a per\-budget, per\-budget period basis\. They might alert more than once in a budgeted period if the forecasted values exceed, dip below, and then exceed the alert threshold again during the budgeted period\.

AWS requires approximately 5 weeks of usage data to generate budget forecasts\. If you set a budget to alert based on a forecasted amount, this budget alert isn't triggered until you have enough historical usage information\.

## Best practices for setting budget alerts using Amazon SNS topics<a name="budgets-best-practices-alerts-sns-topics"></a>

When you create a budget that sends notifications to an Amazon SNS topic, you must either have a preexisting Amazon SNS topic or create an Amazon SNS topic\. Amazon SNS topics enable you to send notifications over SMS in addition to email\.

For budget notifications to be sent successfully, your budget must have permissions to send a notification to your topic, and you must accept the subscription to the Amazon SNS notification topic\. For more information, see [Creating an Amazon SNS topic for budget notifications](budgets-sns-policy.md)\.