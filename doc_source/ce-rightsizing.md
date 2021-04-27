# Optimizing your cost with Rightsizing Recommendations<a name="ce-rightsizing"></a>

The rightsizing recommendations feature in Cost Explorer helps you identify cost\-saving opportunities by downsizing or terminating instances in Amazon Elastic Compute Cloud \(Amazon EC2\)\. Rightsizing recommendations analyze your Amazon EC2 resources and usage to show opportunities for how you can lower your spending\. You can see all of your underutilized Amazon EC2 instances across member accounts in a single view to immediately identify how much you can save\. After you identify your recommendations, you can take action on the Amazon EC2 console\. 

**Topics**
+ [Getting started with rightsizing recommendations](#rr-getting-started)
+ [Using your rightsizing recommendations](#rr-use)
+ [CSV details](#csv-details)
+ [Understanding your rightsizing recommendations calculations](#understanding-rr-calc)

## Getting started with rightsizing recommendations<a name="rr-getting-started"></a>

You can access your reservation recommendations and resource\-based recommendations on the Cost Explorer console\. After you enable the feature, it can take up to 30 hours to generate your recommendations\.

**To access rightsizing recommendations**

1. Sign in to the AWS Management Console and open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the navigation pane, choose **Rightsizing recommendations**\.

**To enable rightsizing recommendations**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the navigation pane, choose **Preferences**\.

1. In the **Recommendations** section, choose **Receive Amazon EC2 resource recommendations**\.

**Note**  
Only regular or a management account can enable rightsizing recommendations\. After you enable the feature, both member and management account can access rightsizing recommendations unless the management account specifically prohibits member account access on the **settings** page\.   
To improve the recommendation quality, AWS might use your published utilization metrics, such as disk or memory utilization, to improve our recommendation models and algorithms\. All metrics are anonymized and aggregated before AWS uses them for model training\. If you want to opt out of this experience and request that your metrics not be stored and used for model improvement, contact AWS Support\. For more information, see [AWS Service Terms](https://aws.amazon.com/service-terms/)\.

## Using your rightsizing recommendations<a name="rr-use"></a>

You can see the following top\-level key performance indicators \(KPIs\) in your rightsizing recommendations:
+ **Optimization opportunities** – The number of recommendations available based on your resources and usage
+ **Estimated monthly savings** – The sum of the projected monthly savings associated with each of the recommendations provided
+ **Estimated savings \(%\)** – The available savings relative to the direct instance costs \(On\-Demand\) associated with the instances in the recommendation list

**To filter your rightsizing recommendations**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the left navigation pane, choose **Rightsizing recommendations**\.

1. At the top of the **Rightsizing Recommendations** page, filter your recommendations by selecting any or all of the following check boxes:
   + Idle instances \(termination recommendations\)
   + Underutilized instances
   + Include Savings Plans and Reserved Instances \(option to consider existing Savings Plans or RI coverage in recommendation savings calculations\)
   + Generate recommendations \(option to generate recommendations within the instance family, or across multiple instance families\)

1. Above the **Findings** table, use the search bar to filter by the following parameters:
   + Account ID \(option available from the management account\)
   + Region
   + Cost allocation tag

**To view your rightsizing recommendations details**

1. Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. In the left navigation pane, choose **Rightsizing recommendations**\.

1. Choose **View**\.

   The **View** button on the right of each recommendation opens a window that provides details on the instances and recommended actions\. 

**To download your recommendations in CSV format**

1. Choose **Launch Cost Explorer**\.

1. In the left navigation pane, choose **Recommendations**\.

1. Select **Download CSV**\.

For definitions for the CSV file fields, see [CSV details](#csv-details)\.

### Enhancing your recommendations using CloudWatch metrics<a name="enhance-recommendation-cw"></a>

We can examine your memory utilization if you enable your Amazon CloudWatch agent\.

To enable memory utilization, see [Installing the CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance.html)\.

**Important**  
When you create a CloudWatch configuration file, use the default namespace and default names for the collected metrics\.  
For **InstanceID**, choose `append_Dimension`\. Do not add additional dimensions for individual memory or disk metrics\. Disk utilization is currently not examined\.  
For Linux instances, choose `mem_used_percent` as your metric for your CloudWatch agent to collect\. For Windows instances, choose `"% Committed Bytes In Use"`\.

For more information about the CloudWatch agent, see [Collecting Metrics and Logs from Amazon EC2 Instances and On\-Premises Servers with the CloudWatch Agent](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html) in the *Amazon CloudWatch User Guide*\.

## CSV details<a name="csv-details"></a>

The following is a list of fields in the downloadable CSV form from the **Rightsizing Recommendations** page\. The fields are repeated if there are multiple rightsizing options available\. The file also contains all of your relevant cost allocation tags\.
+ **Account ID** – The AWS account ID that owns the instance that the recommendation is based off of\.
+ **Account Name** – The name of the account that owns the instance that the recommendation is based off of\.
+ **Instance ID** – The unique instance identifier\.
+ **Instance Name** – The name you've given to the instance\.
+ **Instance Type** – The instance family and size of the original instance\.
+ **Instance Name** – The name you've given an instance\. This field will show as blank if you haven't given the instance a name\.
+ **OS** – The operating system or platform of the current instance\.
+ **Region** – The AWS Region that the instance is running in\.
+ **Running Hours** – The total number of running hours of the instance over the last 14 days\.
+ **RI Hours** – The subset of the total running hours that are covered by an AWS reservation over the look\-back period\.
+ **OD Hours** – The subset of the total running hours that are On\-Demand over the look\-back period\.
+ **SP Hours** – The subset of the total running hours that are covered by Savings Plans over the look\-back period\.
+ **CPU Utilization** – The maximum CPU utilization of the instance over the look\-back period\.
+ **Memory Utilization** – The maximum memory utilization of the instance over the look\-back period \(if available from the Amazon CloudWatch agent\)\.
+ **Disk Utilization** – The maximum disk utilization of the instance over the look\-back period \(if available from the CloudWatch agent \- currently not supported\)\.
+ **Network Capacity** – The maximum network input/output operations per second capacity of the current instance\. This isn't a measure of actual instance use or performance, only capacity\. It's not considered in the recommendation\.
+ **EBS Read Throughput** – The maximum number of read operations per second\.
+ **EBS Write Throughput** – The maximum number of write operations per second\.
+ **EBS Read Bandwidth** – The maximum volume of read KiB per second\.
+ **EBS Write Bandwidth** – The maximum volume of write KiB per second\.
+ **Recommended Action** – The recommended action, either modify or terminate the instance\.
+ **Recommended Instance Type 1** – The instance family and size of the recommended instance type\. For termination recommendations, this field is empty\.
+ **Recommended Instance Type 1 Estimated Saving** – The projected savings based on the recommended action, instance type, associated rates, and your current Reserved Instance \(RI\) portfolio\.
+ **Recommended Instance Type 1 Projected CPU** – The projected value of the CPU utilization based on utilization of current instance disk and recommended instance specifications\.
+ **Recommended Instance Type 1 Projected Memory** – The projected value of the memory utilization based on utilization of current instance memory and recommended instance specifications\.
+ **Recommended Instance Type 1 Projected Disk** – The projected value of the disk utilization based on utilization of current instance disk and recommended instance specifications\.
+ **Recommended Instance Type 1 Network Capacity** – The maximum network input/output operations per second capacity of the recommended instance\. This isn't a measure of actual instance use or performance, only capacity\. It's not considered in the recommendation\.

## Understanding your rightsizing recommendations calculations<a name="understanding-rr-calc"></a>

This section provides an overview of the savings calculations that are used in your rightsizing recommendations algorithms\.

### Consolidated billing family<a name="consolidated-fam"></a>

To identify all instances for all accounts in the consolidated billing family, rightsizing recommendations look at the usage for the last 14 days for each account\. If the instance was stopped or terminated, we remove it from consideration\. For all remaining instances, we call CloudWatch to get maximum CPU utilization data, memory utilization \(if enabled\), network in/out, local disk input/ output \(I/O\), and performance of attached EBS volumes for the last 14 days\. This is to produce conservative recommendations, not to recommend instance modifications that could be detrimental to application performance or that could unexpectedly impact your performance\.

### Determining if an instance is idle, underutilized, or neither<a name="determine-status"></a>

We look at the maximum CPU utilization of the instance for the last 14 days to make one of the following assessments:
+ **Idle** – If the maximum CPU utilization is at or below 1%\. A termination recommendation is generated, and savings are calculated\. For more information, see [Savings calculation](#savings-calc)\.
+ **Underutilized** – If the maximum CPU utilization is above 1% and cost savings are available in modifying the instance type, a modification recommendation is generated\.

If the instance isn't idle or underutilized, we don't generate any recommendations\.

### Generating modification recommendations<a name="generating-mod"></a>

Recommendations use a machine learning engine to identify the optimal Amazon EC2 instance types for a particular workload\. Instance types include those that are a part of AWS Auto Scaling groups\.

The recommendations engine analyzes the configuration and resource usage of a workload to identify dozens of defining characteristics\. For example, it can determine whether a workload is CPU\-intensive or whether it exhibits a daily pattern\. The recommendations engine analyzes these characteristics and identifies the hardware resources that the workload requires\.

Finally, it concludes how the workload would perform on various Amazon EC2 instances to make recommendations for the optimal AWS compute resources that the specific workload\.

### Savings calculation<a name="savings-calc"></a>

We first examine the instance running in the last 14 days to identify whether it was partially or fully covered by an RI or Savings Plans, or running On\-Demand\. Another factor is whether the RI is size\-flexible\. The cost to run the instance is calculated based on the On\-Demand hours and the rate of the instance type\.

For each recommendation, we calculate the cost to operate a new instance\. We assume that a size\-flexible RI covers the new instance in the same way as the previous instance if the new instance is within the same instance family\. Estimated savings are calculated based on the number of On\-Demand running hours and the difference in On\-Demand rates\. If the RI isn't size\-flexible, or if the new instance is in a different instance family, the estimated savings calculation is based on whether the new instance had been running during the last 14 days as On\-Demand\.

Cost Explorer only provides recommendations with an estimated savings greater than or equal to $0\. These recommendations are a subset of Compute Optimizer results\. For more performance\-based recommendations that might result in a cost increase, see [Compute Optimizer](http://aws.amazon.com/compute-optimizer/)\.

You can choose to view saving with or without consideration for RI or Savings Plans discounts\. Recommendations consider both discounts by default\. Considering RI or Savings Plans discounts might result in some recommendations showing a savings value of $0\. To change this option, see [Using your rightsizing recommendations](#rr-use)\.

**Note**  
Rightsizing recommendations doesn't capture second\-order effects of rightsizing, such as the resulting RI hour’s availability and how they will apply to other instances\. Potential savings based on reallocation of the RI hours aren't included in the calculation\.