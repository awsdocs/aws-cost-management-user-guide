# Setting up your anomaly detection<a name="settingup-ad"></a>

The overviews in this section help you get started with AWS Cost Anomaly Detection in AWS Billing and Cost Management\.

**Topics**
+ [Enabling Cost Explorer](#enable-ce-ad)
+ [Controlling access using IAM](#access-iam-ad)
+ [Accessing the console](#access-ad)
+ [Limits](#limits-ad-section)

## Enabling Cost Explorer<a name="enable-ce-ad"></a>

AWS Cost Anomaly Detection is a feature within Cost Explorer\. To access AWS Cost Anomaly Detection, enable Cost Explorer\. For information about how to enable Cost Explorer using the console, see [Enabling Cost Explorer](ce-enable.md)\.

## Controlling access using IAM<a name="access-iam-ad"></a>

After you enable Cost Explorer at the management account level, you can use AWS Identity and Access Management \(IAM\) to manage access to your billing data for individual IAM users\. You can then grant or revoke access on an individual level for each account, rather than granting access to all member accounts\.

An IAM user must be granted explicit permission to view pages in the Billing and Cost Management console\. With the appropriate permissions, the IAM user can view costs for the AWS account that the IAM user belongs to\. For the policy that grants the necessary permissions to an IAM user, see [Billing and Cost Management actions policies](billing-permissions-ref.md#user-permissions)\. 

## Accessing the console<a name="access-ad"></a>

When your setup is complete, access AWS Cost Anomaly Detection\.<a name="access-ad-process"></a>

**To access AWS Cost Anomaly Detection**

1. Sign in to the AWS Management Console and open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. On the navigation pane, choose **Cost Anomaly Detection**\.

## Limits<a name="limits-ad-section"></a>

For the default limit, see [AWS Cost Anomaly Detection](billing-limits.md#limits-ad)\.