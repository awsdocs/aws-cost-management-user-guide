# Getting started with anomaly detection<a name="getting-started-ad"></a>


|  | 
| --- |
| Anomaly detection is in public preview for AWS Billing and Cost Management and is subject to change\. Your use of anomaly detection is subject to the Preview Service Participation terms of the [AWS Service Terms](https://aws.amazon.com/service-terms/) \(Section 1\.10\)\. | 

When you start using anomaly detection in AWS Billing and Cost Management, you have several options for configuring your monitor and alert preferences\.

**Topics**
+ [Creating your anomaly monitors and alert preferences](#create-ad-alerts)
+ [Viewing your detected anomalies and root causes](#view-ad-monitor)

## Creating your anomaly monitors and alert preferences<a name="create-ad-alerts"></a>

You can configure your anomaly detection so that it detects anomalies at a lower granularity and spend patterns, in context to your monitor type\.

For example, your spend patterns for Amazon EC2 usage might be different from your AWS Lambda or Amazon S3 spend patterns\. By segmenting spends by AWS services, anomaly detection can detect separate spend patterns that help decrease false positive alerts\. You can also create monitors that evaluate specific cost allocation tags, member accounts, and cost categories based on your AWS account structure\.

As you create your monitors, you can configure your alerting preferences specific to each monitor\.<a name="ad-alert-process"></a>

**To create a monitor**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the navigation pane, choose **Anomaly Detection**\.

1. On the **Cost Explorer** page, choose **Anomaly Detection**\.

1. Choose **Create monitor**\.

1. Under **How to monitor your spend**, choose a monitor type\.

   For more information about each monitor type and best practices, see [Monitor types](#monitor-type-def)\.

1. For **Alert threshold**, enter the dollar amount threshold to receive alerts\.

   A threshold is not the same as an anomaly\. Anomalies are detected using machine learning\. For example, you can set a $0 threshold alert of every anomaly, even if the cost impact is $1\.

1. Under **Alerting frequency**, choose your preferred notification frequency\.
   + **Individual alerts** \- The alert notifies you as soon as an anomaly is detected\. You might receive multiple alerts throughout a day\. These notifications require an Amazon SNS topic\.
   + **Daily summary** \- The alert notifies you with a daily summary when anomalies are detected\. You receive one email containing information for multiple anomalies that occurred that day\. These notifications require at least one email recipient\.
   + **Weekly summary** \- The alert notifies you with a weekly summary when anomalies are detected\. You receive one email containing information for multiple anomalies that occurred that week\. These notifications require at least one email recipient\.

1. For **Monitor name**, enter a name for your anomaly monitor\.

   We recommend the name to be a short description so that you know what the monitor represents when you view your monitors on the **Overview** page\.

1. Choose **Create monitor**\.

### Monitor types<a name="monitor-type-def"></a>

You can choose the monitor type that suits your account structure\. Currently we offer the following monitor types:
+ **AWS services** \- We recommend this monitor if you don't need to segment your spend by internal organizations or environments\. This single monitor evaluates all AWS services used by your individual AWS account for anomalies\. When you add new AWS services, the monitor automatically begins to evaluate the new service for anomalies, so you don't have to manually configure your settings\.
**Note**  
Only the AWS services monitor is available within member accounts\.
+ **Linked account** \- This monitor evaluates the total spend of an individual, or group of, member accounts\. This monitor is useful if your Organizations needs to segment spend by team, product, services, or environment, that you define as individual or groups of accounts\.
+ **Cost category** \- This monitor is recommended if you use cost categories to organize and manage your spend\. This monitor type is restricted to one `key:value` pair\.
+ **Cost allocation tag** \- This monitor is similar to **Linked account** because it is useful if you to need to segment your spend by team, product, services, or environment, defined by cost allocation tags\. This monitor type is restricted to one key, but accepts multiple values\.

We recommend that you do not create monitors that span multiple monitor types\. This might lead to evaluating overlapping spends that generate duplicate alerts\.

For more information about creating your Amazon SNS topic, see [Creating an Amazon SNS topic for anomaly detection](ad-SNS.md)\.

## Viewing your detected anomalies and root causes<a name="view-ad-monitor"></a>

After you create your monitors, anomaly detection evaluates your future spend\. Based on your defined alerting preferences, you might start receiving alerts within 24 hours\.<a name="view-email-process"></a>

**To view your anomalies from an email alert**

1. Choose the provided **View in Anomaly Detection** link\.

1. On the **Anomaly details** page, you can view the root cause analysis and cost impact of the anomaly\.

1. \(Optional\) Choose **View in Cost Explorer** to view a graph of the time series, automatically filtered by root causes\.

1. \(Optional\) Choose **Did you find this detected anomaly to be helpful?** to provide feedback and help improve our detection accuracy\.<a name="view-console-process"></a>

**To view your anomalies from the AWS Cost Management console**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the navigation pane, choose **Anomaly Detection**\.

1. \(Optional\) In the **Cost monitors** section, choose **Monitor name** to narrow any detected anomalies for a particular monitor\.

1. \(Optional\) Choose **View in Cost Explorer** to view a graph of the time series, automatically filtered by root causes\.

1. \(Optional\) Choose **Did you find this detected anomaly to be helpful?** to provide feedback and help improve our detection accuracy\.