# Detecting unusual spend with anomaly detection<a name="manage-ad"></a>


|  | 
| --- |
| Anomaly detection is in public preview for AWS Billing and Cost Management and is subject to change\. Your use of anomaly detection is subject to the Preview Service Participation terms of the [AWS Service Terms](https://aws.amazon.com/service-terms/) \(Section 1\.10\)\. | 

Anomaly detection is an AWS Cost Management feature that uses machine learning to continuously monitor your cost and usage to detect unusual spends\. Using anomaly detection includes the following benefits: 
+ Receive alerts individually in aggregated reports\. You can receive alerts in an email or an Amazon SNS topic\.
+ Evaluate your spend patterns using machine learning methods to minimize false positive alerts\. For example, you can evaluate weekly or monthly seasonality and organic growth\.
+ Analyze and determine the root cause of the anomaly, such as account, service, Region, or usage type that is driving the cost increase\.
+ Configure how you need to evaluate your costs\. You can choose whether you want to analyze all of your AWS services independently, or by member accounts, cost allocation tags, or cost categories\.

**Note**  
Anomaly detection runs approximately three times a day after your billing data is processed\. You might experience a slight delay in receiving alerts\. As a result, you might accumulate additional costs over the notified amount by the time you receive the alert\.

**Topics**
+ [Setting up your anomaly detection](settingup-ad.md)
+ [Getting started with anomaly detection](getting-started-ad.md)
+ [Editing your alerting preferences](edit-alert-pref.md)
+ [Creating an Amazon SNS topic for anomaly detection](ad-SNS.md)