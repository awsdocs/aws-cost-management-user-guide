# How to use the affected policies tool<a name="migrate-security-iam-tool"></a>


|  | 
| --- |
| ***The following AWS Identity and Access Management \(IAM\) actions will reach the end of standard support on July 2023: `aws-portal` namespace, `purchase-orders:ViewPurchaseOrders`, and `purchase-orders:ModifyPurchaseOrders`\. See the [Using fine\-grained AWS Billing actions ](migrate-granularaccess-whatis.md#migrate-user-permissions) to replace these actions with fine\-grained actions so you have access to AWS Billing, AWS Cost Management, and AWS accounts consoles\.*** ***If you created your AWS account, or are a part of an AWS Organizations created before March 6, 2023, 11:00 \(PDT\), the fine\-grained actions will be effective starting July 2023\. We recommend you to add the fine\-grained actions, but not remove your existing permissions with `aws-portal` or `purchase-orders` prefixes\.*** ***If you created your AWS account, or are a part of an AWS Organizations created on or after March 6, 2023, 11:00 \(PDT\), the fine\-grained actions are effective immediately\.***  | 

You can use the **Affected policies** tool in the Billing console to identify IAM policies \(excluding SCPs\), and reference the IAM actions impacted by this migration\. This tool operates within the boundaries of the AWS account you're logged into, and information regarding other AWS Organizations accounts are not disclosed\.

**To use the Affected policies tool**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Paste the following URL into your browser to access the **Affected policies** tool: [https://us-east-1.console.aws.amazon.com/poliden/home?region=us-east-1#/](https://us-east-1.console.aws.amazon.com/poliden/home?region=us-east-1#/)\.

   Note that you require iam:GetAccountAuthorizationDetails permission to view this page\.

1. Review the table that lists the IAM policies impacted\. Use the **Deprecated IAM actions** column to review specific IAM actions referenced in a policy\.

1. Choose an IAM policy name you wish to edit\.

1. Once you're redirected to the IAM console, update the impacted IAM action with the new action\. Don't remove any existing `aws-portal` or `purchase-orders` action if you have any\.

   For a list of new actions, see [Using fine\-grained AWS Billing actions ](migrate-granularaccess-whatis.md#migrate-user-permissions)\.

1. Repeat steps 3 to 5 for all listed policies\.

1. Once all of the policies are resolved, access the **Affected policies** tool to confirm there are no policies listed\.