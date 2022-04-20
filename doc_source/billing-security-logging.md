# Logging and monitoring in AWS Billing and Cost Management<a name="billing-security-logging"></a>

Monitoring is an important part of maintaining the reliability, availability, and performance of your AWS account\. There are several tools available to monitor your Billing and Cost Management usage\.

## AWS Cost and Usage Reports<a name="billing-security-logging-cur"></a>

AWS Cost and Usage Reports tracks your AWS usage and provides estimated charges associated with your account\. Each report contains line items for each unique combination of AWS products, usage type, and operation that you use in your AWS account\. You can customize the AWS Cost and Usage Reports to aggregate the information either by the hour or by the day\.

For more information about AWS Cost and Usage Reports, see the [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.

## AWS CloudTrail<a name="billing-security-logging-cloudtrail"></a>

Billing and Cost Management is integrated with AWS CloudTrail, a service that provides a record of actions taken by a user, role, or an AWS service in Billing and Cost Management\. CloudTrail captures all write and modify API calls for Billing and Cost Management as events, including calls from the Billing and Cost Management console and from code calls to the Billing and Cost Management APIs\.

For more information about AWS CloudTrail, see the [Logging Billing and Cost Management API calls with AWS CloudTrail](logging-using-cloudtrail.md)\.