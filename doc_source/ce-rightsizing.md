# Optimizing Your Cost with Rightsizing Recommendations<a name="ce-rightsizing"></a>

Rightsizing recommendations helps you identify cost saving opportunities in Cost Explorer, downsizing or terminating instances in your Amazon Elastic Compute Cloud \(Amazon EC2\)\. Rightsizing recommendations analyzes your Amazon EC2 resources and usage to show opportunities on how you can lower your spendings\. You can see all of your underutilized Amazon EC2 instances in every Region and linked account in a single view to immediately identify how much you can save\. After you’ve identified your recommendations, you can take action on the Amazon EC2 console\. 

**Note**  
GPU instances aren't supported in this feature, and rightsizing recommendations aren't provided for those instances\. 

**Topics**
+ [Getting Started with Rightsizing Recommendations](#rr-getting-started)
+ [Using Your Rightsizing Recommendations](#rr-use)
+ [CSV Details](#csv-details)
+ [Understanding Your Rightsizing Recommendations Calculations](#understanding-rr-calc)

## Getting Started with Rightsizing Recommendations<a name="rr-getting-started"></a>

You can access your reservation recommendations and resource\-based recommendations on the Cost Explorer console\. After you enable rightsizing recommendations, it can take up to 24 hours for it to generate\.

**To access rightsizing recommendations**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the Cost Explorer page, choose **Launch Cost Explorer**\.

1. In the navigation pane, choose **Recommendations**\.

**To enable rightsizing recommendations**

1. Choose **Launch Cost Explorer**\.

1. In the navigation pane, choose **Recommendations**\.

1. In the **Resource optimization recommendations** section, choose **Enable rightsizing recommendations**\.

**Note**  
Only regular or payer accounts can enable rightsizing recommendations\. After you enable rightsizing recommendations, both linked and payer accounts can access rightsizing recommendations unless the payer account specifically prohibits linked account access on the **settings** page\.   
To improve the recommendation quality, AWS might use your published utilization metrics, such as disk or memory utilization, to improve our recommendation models and algorithms\. All metrics are anonymized and aggregated before AWS use them for model training\. If you want to opt out of this experience and request that your metrics not be stored and used for model improvement, contact AWS Support\. For more information, see [AWS Service Terms](https://aws.amazon.com/service-terms/)\.

## Using Your Rightsizing Recommendations<a name="rr-use"></a>

You can see the following top\-level key performance indicators \(KPIs\) in your rightsizing recommendations:
+ **Optimization opportunities** – The number of recommendations available based on your resources and usage
+ **Estimated monthly savings** – The sum of the projected monthly savings associated with each of the recommendations provided
+ **Estimated savings \(%\)** – The available savings relative to the direct instance costs \(On\-Demand\) associated with the instances in the recommendation list

**To filter your rightsizing recommendations**

1. Choose **Launch Cost Explorer**\.

1. In the left navigation pane, choose **Recommendations**\.

1. In the **Resource optimization recommendations** section, choose **Enable rightsizing recommendations**\.

1. In the menu on the right side, filter your recommendations by selecting any or all of the following check boxes:
+ Over provisioned instances \(modification recommendations\)
+ Idle instances \(termination recommendations\)
+ Underutilized instances
+ Account ID \(option available from the payer account\)
+ Region
+ Cost allocation tag

**To view your rightsizing recommendations details**

1. Choose **Launch Cost Explorer**\.

1. In the left navigation pane, choose **Recommendations**\.

1. Choose **View**\.

   The view button on the right of each recommendation opens a window\. This provides details on the instances and recommended actions\. 

**To download your recommendations in CSV format**

1. Choose **Launch Cost Explorer**\.

1. In the left navigation pane, choose **Recommendations**\.

1. Select **Download CSV**\.

For definitions for the CSV file fields, see [CSV Details](#csv-details)\.

### Enhancing your recommendations using CloudWatch metrics<a name="enhance-recommendation-cw"></a>

We can examine your memory utilization if you've enabled your CloudWatch agent\.

To enable memory utilization, see [Installing the CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance.html)\.

**Important**  
When you're creating a CloudWatch configuration file, use the default namespace and default names for the collected metrics\.  
For **InstanceID**, choose `append_Dimension`\. Do not add additional dimensions for individual memory or disk metrics\. Disk utilization is currently not examined\.  
For Linux instances, choose `mem_used_percent` as your metric for your CloudWatch agent to collect\. For Windows instances, choose `"% Committed Bytes In Use"`\.

For more information about the CloudWatch agent, see [Collecting Metrics and Logs from Amazon EC2 Instances and On\-Premises Servers with the CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html) in the *Amazon CloudWatch User Guide*\.

## CSV Details<a name="csv-details"></a>

The following is a list of fields in the downloadable CSV form from the **Rightsizing Recommendations** page\. The fields are repeated if there are multiple rightsizing options available\. The file also contains all of your relevant cost allocation tags\.
+ **Account ID** – The AWS account ID that owns the instance that the recommendation is based off of\.
+ **Account Name** – The name of the account that owns the instance that the recommendation is based off of\.
+ **Instance ID** – The unique instance identifier\.
+ **Instance Type** – The instance family and size of the original instance\.
+ **OS** – The operating system or platform of the current instance\.
+ **Region** – The AWS Region that the instance is running in\.
+ **Running Hours** – The total number of running hours of the instance over the last 14 days\.
+ **RI Hours** – The subset of the total running hours that are covered by an AWS reservation over the look\-back period\.
+ **OD Hours** – The subset of the total running hours that are On\-Demand over the look\-back period\.
+ **CPU Utilization** – The maximum CPU utilization of the instance over the look\-back period\.
+ **Memory Utilization** – The maximum memory utilization of the instance over the look\-back period \(if available from the Amazon CloudWatch agent\)\.
+ **Disk Utilization** – The maximum disk utilization of the instance over the look\-back period \(if available from the CloudWatch agent \- currently not supported\)\.
+ **Network Capacity** – The maximum network input/output operations per second capacity of the current instance\. This isn't a measure of actual instance use or performance, only capacity\. It's not considered in the recommendation\.
+ **Recommended Action** – The recommended action, either modify or terminate the instance\.
+ **Recommended Instance Type 1** – The instance family and size of the recommended instance type\. For termination recommendations, this field is empty\.
+ **Recommended Instance Type 1 Estimated Saving** – The projected savings based on the recommended action, instance type, associated rates, as well as your current Reserved Instance \(RI\) portfolio\.
+ **Recommended Instance Type 1 Projected CPU** – The projected value of the CPU utilization based on utilization of current instance disk and recommended instance specifications\.
+ **Recommended Instance Type 1 Projected Memory** – The projected value of the memory utilization based on utilization of current instance memory and recommended instance specifications\.
+ **Recommended Instance Type 1 Projected Disk** – The projected value of the disk utilization based on utilization of current instance disk and recommended instance specifications\.
+ **Recommended Instance Type 1 Network Capacity** – The maximum network input/output operations per second capacity of the recommended instance\. This isn't a measure of actual instance use or performance, only capacity\. It's not considered in the recommendation\.

## Understanding Your Rightsizing Recommendations Calculations<a name="understanding-rr-calc"></a>

This document provides an overview of the savings calculations used in your rightsizing recommendations algorithms\.

### Consolidated Billing Family<a name="consolidated-fam"></a>

To identify all instances for all accounts in the consolidated billing family, rightsizing recommendations looks at the usage for the last 14 days for each account\. If the instance wasn't run in the last 3 days, we consider it terminated and remove it from consideration\. For all remaining instances, we call CloudWatch to get maximum CPU utilization data for the last 14 days\. This is to produce conservative recommendations, not to recommend instance modifications that could be detrimental to application performance or that could unexpectedly impact your performance\.

### Determining If an Instance Is Idle, Underutilized, or Neither<a name="determine-status"></a>

We look at the maximum CPU utilization of the instance for the last 14 days to make one of the following assessments:
+ **Idle** – If the maximum CPU utilization is at or below 1%\. A termination recommendation is generated, and savings are calculated\. For more information, see [Savings Calculation](#savings-calc)\.
+ **Underutilized** – If the maximum CPU utilization is between 1% and 40%\. A modification recommendation is generated\. For more information, see [Generating Modification Recommendations](#generating-mod)\.

If the instance isn't idle or underutilized, we don't generate any recommendations\.

### Generating Modification Recommendations<a name="generating-mod"></a>

To determine replacement instances, we identify smaller instance sizes in the instance family and calculate a projected maximum CPU utilization\. We include this as a recommendation if the projected value is below 80%\. For each recommendation, we calculate the estimated savings and remove any recommendations with a savings below $0\. 

### Savings Calculation<a name="savings-calc"></a>

We first examine the instance running in the last 14 days to identify if it was partially or fully covered by an RI or running On\-Demand\. Another factor is whether the RI is size\-flexible\. The cost to run the instance is calculated based on the On\-Demand hours and the rate of the instance type\.

For each recommendation, we calculate the cost to operate a new instance\. We assume that a size\-flexible RI will cover the new instance in the same way as the previous instance\. Savings are calculated based on the number of On\-Demand running hours and the difference in On\-Demand rates\. If the RI isn't size\-flexible, the savings calculation is based on if the instance hours during the last 14 days are operated as On\-Demand\. We provide only recommendations with estimated savings greater than or equal to $0\. 

**Note**  
Rightsizing recommendations doesn't capture second\-order effects of rightsizing, such as the resulting RI hour’s availability and how they will apply to other instances\. Potential savings based on reallocation of the RI hours aren't included in the calculation\.