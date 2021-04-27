# Getting started with AWS Cost Anomaly Detection<a name="getting-started-ad"></a>

When you start using AWS Cost Anomaly Detection in AWS Billing and Cost Management, you have several options for configuring your cost monitors and alert subscriptions\.

**Topics**
+ [Creating your cost monitors and alert subscriptions](#create-ad-alerts)
+ [Detection history values](#detector-history-values)
+ [Viewing your detected anomalies and root causes](#view-ad-monitor)
+ [Monitor types](#monitor-type-def)

## Creating your cost monitors and alert subscriptions<a name="create-ad-alerts"></a>

You can configure AWS Cost Anomaly Detection so that it detects anomalies at a lower granularity and spend patterns, in context to your monitor type\.

For example, your spend patterns for Amazon EC2 usage might be different from your AWS Lambda or Amazon S3 spend patterns\. By segmenting spends by AWS services, AWS Cost Anomaly Detection can detect separate spend patterns that help decrease false positive alerts\. You can also create cost monitors that evaluate specific cost allocation tags, member accounts, and cost categories based on your AWS account structure\.

As you create your cost monitors, you can configure your alert subscriptions specific to each monitor\.<a name="ad-alert-process"></a>

**To create a cost monitor**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the navigation pane, choose **Cost Anomaly Detection**\.

1. Choose the **Cost monitors** tab\.

1. Choose **Create monitor**\.

1. In **Step 1**, choose a monitor type and name your monitor\.

   For more information about each monitor type and best practices, see [Monitor types](#monitor-type-def)\.

   For **Monitor name**, enter a name for your anomaly monitor\. We recommend that the name is a short description so that you know what the monitor represents when you view your monitors on the **Cost monitors** tab\. 

1. Choose **Next**\.

1. In **Step 2**, configure your alert subscriptions\.

   For **Alert subscription**, if you do not have an existing subscription, choose **Create a new subscription**\. If you have existing subscriptions, select **Choose an existing subscription**\.
**Note**  
An alert subscription notifies you when a cost monitor detects an anomaly\. Depending on the alert frequency, you can notify designated individuals by email or Amazon SNS\. For example, you can create a subscription for the Finance team in your organization\.

   For **Subscription name**, enter a name that describes your use case\. For example, if the subscription is meant for leadership, then the subscription name might be “Leadership report\.” 

   For **Threshold**, enter the dollar amount threshold to receive alerts\.
**Note**  
An alert threshold is the dollar value above which you want to be notified\. It does not impact anomaly detection because that is done by machine learning models looking at historical spend\. Alert recipients will receive notifications of events greater than the threshold amount\. For example, if you set a $10 threshold, alert receipts will receive notifications of events greater than $10\. All anomalies detected by machine learning models \(both greater and less than $10\) will be available in the **Detection history** tab\.

   Under **Alerting frequency**, choose your preferred notification frequency\.
   + **Individual alerts** \- The alert notifies you as soon as an anomaly is detected\. You might receive multiple alerts throughout a day\. These notifications require an Amazon SNS topic\.
   + **Daily summary** \- The alert notifies you with a daily summary when anomalies are detected\. You receive one email containing information for multiple anomalies that occurred that day\. These notifications require at least one email recipient\.
   + **Weekly summary** \- The alert notifies you with a weekly summary when anomalies are detected\. You receive one email containing information for multiple anomalies that occurred that week\. These notifications require at least one email recipient\.

   Under **Alert recipients**, enter email addresses for this subscription\. 

1. \(Optional\) Choose **Add alert subscriptions** to create another alert subscription\. With this option, you can create a new subscription using the same monitor\. 

1. Choose **Create monitor**\.<a name="ad-create-a-subscription"></a>

**To create an alert subscription**

You must create at least one alert subscription per monitor\. The "create cost monitor steps" described earlier already include the alert subscription creation process\. If you want to create additional subscriptions, perform the following steps\.

1. Go to the **Alert subscriptions tab**\.

1. Choose **Create a subscription**\.

1. For **Subscription name**, enter a name that describes your use case\. For example, if the subscription is meant for leadership, then the subscription name might be “Leadership report\.” 

1. For **Threshold**, enter the dollar amount threshold to receive alerts\.
**Note**  
An alert threshold is the dollar value above which you want to be notified\. It does not impact anomaly detection because that is done by machine learning models looking at historical spend\. Alert recipients will receive notifications of events greater than the threshold amount\. For example, if you set a $10 threshold, alert receipts will receive notifications of events greater than $10\. All anomalies detected by machine learning models \(both greater and less than $10\) will be available in the **Detection history** tab\.

1. Under **Alerting frequency**, choose your preferred notification frequency\.
   + **Individual alerts** \- The alert notifies you as soon as an anomaly is detected\. You might receive multiple alerts throughout a day\. These notifications require an Amazon SNS topic\.
   + **Daily summary** \- The alert notifies you with a daily summary when anomalies are detected\. You receive one email containing information for multiple anomalies that occurred that day\. These notifications require at least one email recipient\.
   + **Weekly summary** \- The alert notifies you with a weekly summary when anomalies are detected\. You receive one email containing information for multiple anomalies that occurred that week\. These notifications require at least one email recipient\.

   Under **Alert recipients**, enter email addresses for this subscription\. 

1. In the **Cost monitors** section, select the monitors you would like to be associated with the alert subscription\. 

1. Choose **Create subscription**\.

**Note**  
You can only access cost monitors and alert subscriptions under the account that created them\. For example, if the cost monitor was created under a member/linked account, the payer account will not be able to view or edit the cost monitors, alert subscriptions or detected anomalies\.

## Detection history values<a name="detector-history-values"></a>

On the **Detection history** tab, you can view a list of all the anomalies detected over the time frame that you have selected\. By default, you can see the anomalies detected in the last 90 days\. You can search by **Severity**, **Assessment**, **Service**, **Account ID**, **Usage type**, **Region**, or **Monitor type**\.

The following information is included on the **Detection History** page:

**Time frame**  
 The options are **Last 30 days**, **Last 60 days**, and **Last 90 days**\. 

**Detection date**  
 The day the anomaly was detected\. 

**Severity**  
 Represents how abnormal a certain anomaly is, accounting for historical spending patterns\. A low severity generally suggests a small spike compared to historical spend and a high severity suggests a big spike\. However, a small spike with historically consistent spend is categorized as a high severity and a big spike with irregular historical spend is categorized as a low severity\. 

**Duration**  
 The duration that the anomaly lasted\. An anomaly can be on\-going\. 

**Service**  
 The service that caused the anomaly\. If the service field is empty, AWS has detected an anomaly, but the root cause is unclear\. 

**Account ID**  
 The account id that caused the anomaly\. If the account id is empty, AWS has detected an anomaly, but the root cause is unclear\. 

**Total cost impact**  
 The spend increase detected compared to your normal historical spend\. The calculation is anomaly spend \- normal spend\. For example, a cost impact of $20 on a service monitor means that we detected a $20 increase in a particular service with a total duration of the specified days\. 

**Assessment**  
 For each detected anomaly, you can submit an assessment to help improve our anomaly detection systems\. The possible values are **Not submitted**, **Not an issue**, or **Accurate anomaly**\. 

## Viewing your detected anomalies and root causes<a name="view-ad-monitor"></a>

After you create your monitors, AWS Cost Anomaly Detection evaluates your future spend\. Based on your defined alerting preferences, you might start receiving alerts within 24 hours\.<a name="view-email-process"></a>

**To view your anomalies from an email alert**

1. Choose the provided **View in Anomaly Detection** link\.

1. On the **Anomaly details** page, you can view the root cause analysis and cost impact of the anomaly\.

1. \(Optional\) Choose **View in Cost Explorer** to view a graph of the time series, automatically filtered by root causes\.

1. \(Optional\) Choose **Did you find this detected anomaly to be helpful?** to provide feedback and help improve our detection accuracy\.<a name="view-console-process"></a>

**To view your anomalies from the AWS Cost Management console**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the navigation pane, choose **Cost Anomaly Detection**\.

1. \(Optional\) On the **Detection history** tab, use the search area to narrow the list of detected anomalies for a particular Severity, Assessment, Service, Account ID, Usage Type, Region, or Monitor Type\.

1. \(Optional\)Choose **Detection date** to view the details for a particular anomaly\.

1. On the **Anomaly details** page, you can view the root cause analysis and cost impact of the anomaly\.

1. \(Optional\) Choose **View in Cost Explorer** to view a graph of the time series, automatically filtered by root causes\.

1. \(Optional\) Choose **Did you find this detected anomaly to be helpful?** to provide feedback and help improve our detection accuracy\.

## Monitor types<a name="monitor-type-def"></a>

You can choose the monitor type that suits your account structure\. Currently we offer the following monitor types:
+ **AWS services** \- We recommend this monitor if you don't need to segment your spend by internal organizations or environments\. This single monitor evaluates all AWS services used by your individual AWS account for anomalies\. When you add new AWS services, the monitor automatically begins to evaluate the new service for anomalies, so you don't have to manually configure your settings\.
**Note**  
Only the AWS services monitor is available within member accounts\.
+ **Linked account** \- This monitor evaluates the total spend of an individual, or group of, member accounts\. This monitor is useful if your Organizations needs to segment spend by team, product, services, or environment, that you define as individual or groups of accounts\. The maximum number of linked accounts you can select per monitor is 10\. 
+ **Cost category** \- This monitor is recommended if you use cost categories to organize and manage your spend\. This monitor type is restricted to one `key:value` pair\.
+ **Cost allocation tag** \- This monitor is similar to **Linked account** because it is useful if you to need to segment your spend by team, product, services, or environment, defined by cost allocation tags\. This monitor type is restricted to one key, but accepts multiple values\. The maximum number of values you can select per monitor is 10\.

We recommend that you do not create monitors that span multiple monitor types\. This might lead to evaluating overlapping spends that generate duplicate alerts\.

For more information about creating your Amazon SNS topic, see [Creating an Amazon SNS topic for anomaly detection](ad-SNS.md)\.