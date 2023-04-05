# Migrating access control for AWS Billing<a name="migrate-granularaccess-whatis"></a>


|  | 
| --- |
| ***The following AWS Identity and Access Management \(IAM\) actions will reach the end of standard support on July 2023: `aws-portal` namespace, `purchase-orders:ViewPurchaseOrders`, and `purchase-orders:ModifyPurchaseOrders`\. See the [Using fine\-grained AWS Billing actions ](#migrate-user-permissions) to replace these actions with fine\-grained actions so you have access to AWS Billing, AWS Cost Management, and AWS accounts consoles\.*** ***If you created your AWS account, or are a part of an AWS Organizations created before March 6, 2023, 11:00 \(PDT\), the fine\-grained actions will be effective starting July 2023\. We recommend you to add the fine\-grained actions, but not remove your existing permissions with `aws-portal` or `purchase-orders` prefixes\.*** ***If you created your AWS account, or are a part of an AWS Organizations created on or after March 6, 2023, 11:00 \(PDT\), the fine\-grained actions are effective immediately\.***  | 

You can use fine\-grained access controls to provide individuals in your organization access to AWS Billing and Cost Management services\. For example, you can provide access to Cost Explorer without providing access to the AWS Billing console\.

To use the fine\-grained access controls, you'll need to migrate your policies from under `aws-portal` to the new IAM actions\.

The following IAM actions in your permission policies or service control policies \(SCP\) require updating with this migration:
+ `aws-portal:ViewAccount`
+ `aws-portal:ViewBilling`
+ `aws-portal:ViewPaymentMethods`
+ `aws-portal:ViewUsage`
+ `aws-portal:ModifyAccount`
+ `aws-portal:ModifyBilling`
+ `aws-portal:ModifyPaymentMethods`
+ `purchase-orders:ViewPurchaseOrders`
+ `purchase-orders:ModifyPurchaseOrders`

To learn how to use the **Affected policies** tool to identify your impacted IAM policies, see [How to use the affected policies tool](migrate-security-iam-tool.md)\.

**Note**  
API access to AWS Cost Explorer, AWS Cost and Usage Reports, and AWS Budgets remains unaffected\.  
[Activating access to the AWS Billing console](control-access-billing.md#ControllingAccessWebsite-Activate) remain unchanged\.

**Topics**
+ [Managing access permissions](#migrate-control-access-billing)
+ [How to use the affected policies tool](migrate-security-iam-tool.md)

## Managing access permissions<a name="migrate-control-access-billing"></a>

AWS Billing integrates with the AWS Identity and Access Management \(IAM\) service so that you can control who in your organization can access specific pages on the [AWS Billing console](https://console.aws.amazon.com/billing/)\. This includes features like Payments, Billing, Credits, Free Tier, Payment preferences, Consolidated billing, Tax settings, and Account pages\.

Use the following IAM permissions for granular control for the Billing console\.

To provide fine\-grained access, replace the `aws-portal` policy with `account`, `billing`, `payments`, `freetier`, `invoicing`, `tax`, and `consolidatedbilling`\.

Additionally, replace `purchase-orders:ViewPurchaseOrders` and `purchase-orders:ModifyPurchaseOrders` with the fine\-grained actions under `purchase-orders`, `account`, and `payments`\.

### Using fine\-grained AWS Billing actions<a name="migrate-user-permissions"></a>

This table summarizes the permissions that allow or deny IAM users and roles access to your billing information\. For examples of policies that use these permissions, see [AWS Billing policy examples](billing-example-policies.md)\. 

For a list of actions for the AWS Cost Management console, see [AWS Cost Management actions policies](https://docs.aws.amazon.com/cost-management/latest/userguide/billing-permissions-ref.html#user-permissions) in the *AWS Cost Management user guide*\.

[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/migrate-granularaccess-whatis.html)