# Creating and Saving Custom Reports<a name="cost-explorer-new-report"></a>

To create a custom report, choose the **New report** dropdown list, and then choose one of the following report types\. 


+ [Cost and Usage Report](#ce-cost-reports)
+ [RI Utilization Reports](#ce-utilization-views)
+ [RI Coverage Reports](#ce-coverage-views)
+ [Saving a Report](#edit-save-reports)

## Cost and Usage Report<a name="ce-cost-reports"></a>

The Cost and Usage reports show how you use services, and how your costs are distributed by service\. To create your custom report, you can use all the features discussed in [Analyzing Your Costs with Cost Explorer](cost-explorer-what-is.md)\. 

## RI Utilization Reports<a name="ce-utilization-views"></a>

The RI Utilization reports show how much of your Amazon EC2, Amazon Redshift, Amazon RDS, and ElastiCache Reserved Instance \(RIs\) that you use\. The reports also help you to see if you have purchased too many RIs\. 

The RI utilization charts display the number of Reserved Instance \(RI\) hours that your account uses, helping you to understand and monitor your combined usage \(utilization\) across all of your RIs\. The reports allow you to define a utilization threshold, known as a *utilization target*, and identify RIs that meet your utilization target and RIs that are underutilized\. The chart shows RI utilization as the percentage of purchased RI hours that are used by matching instances, rounded to the nearest percentage\. 

Target utilization is shown on the chart as a dotted line in the chart and in the table under the chart as a colored RI utilization status bar\. RIs with a red status bar are RIs with no hours used, RIs with a yellow status bar are under your utilization target, and RIs with a green status bar have met your utilization target\. You can change the utilization target in the **Display Options** section\. To remove the utilization target line from the chart, clear **Show target line on chart**\.

You can filter the chart to analyze the purchasing accounts, instance types, and more\. The RI reports use a combination of RI\-specific filters and regular Cost Explorer filters\. The RI\-specific filters are available only for the Daily RI Utilization and Monthly RI Utilization reports, and are not available anywhere else that AWS uses Cost Explorer filters\. The following filters are available: 

+ **Availability Zone** – Filter your RI usage by specific Availability Zones \(AZs\)\.

+ **Instance Type** – Filter your RI usage by specific instance types, such as **t2\.micro** or **m3\.medium**\.

+ **Linked Account** – Filter your RI usage by specific linked accounts\.

+ **Platform** – Filter your RI usage by platform, such as **Linux** or **Windows**\.

+ **Region** – Filter your RI usage by specific regions, such as **US East \(N\. Virginia\)** or **Asia Pacific \(Singapore\)**\.

+ **Scope \(Amazon EC2\-specific\)** – Filter your Amazon EC2 usage to show RIs that are purchased for use in specific AZs or regions\.

+ **Tenancy \(Amazon EC2\-specific\)** – Filter your Amazon EC2 usage by tenancy, such as **Dedicated** or **Default**\. A **Dedicated** RI is reserved for a single tenant, while a **Default** RI might share hardware with another RI\.

In addition to changing your utilization target and filtering your RIs with the available filters, you can select a single RI or a group of RIs to show in the chart\. To choose a single RI or a selection of RIs to see in the chart, select the check box next to the RIs in the table under the chart\. 

Cost Explorer shows the combined utilization across all of your RIs in the chart and shows utilization for individual RI subscriptions in the table under the chart\. The table also includes the following information for each RI subscription: 

+ **Account Name** – The name of the account that owns the RI subscription\.

+ **Subscription ID** – The unique subscription ID for the RI subscription\.

+ **Instance Type** – The RI instance type, such as **t2\.micro**\.

+ **RI Utilization** – The percentage of purchased RI hours that were used by matching instances\.

+ **RI Hours Purchased** – The number of purchased hours for the RI subscription\.

+ **RI Hours Used** – The number of purchased hours used by matching instances\.

+ **RI Hours Unused** – The number of purchased hours not used by matching instances\.

You can use this information to track how many RI usage hours you used and how many RI hours you reserved but didn't use\. 

The Daily RI Utilization chart displays your RI utilization for the previous three months on a daily basis\. The Monthly RI Utilization chart displays your RI utilization for the previous 12 months on a monthly basis\. 

## RI Coverage Reports<a name="ce-coverage-views"></a>

The Reserved Instance coverage chart shows how many of your instance hours are covered by RIs\. This allows you to see if you have under\-purchased RIs\. You can define a threshold for how much coverage you want from RIs, known as a *coverage target*, which allows you to see where you can reserve more RIs\. 

Target coverage is shown on the chart as a dotted line, and the average coverage is shown in the table under the chart as a colored status bar\. Instances with a red status bar are instances with no RI coverage, instances with a yellow status bar are under your coverage target, and instances with a green status bar have met your coverage target\. You can change the coverage target in the **Display Options** section\. To remove the coverage target line from the chart, clear **Show target line on chart**\. The RI coverage reports use the Cost Explorer filters instead of the RI Utilization filters\. 

Cost Explorer shows the combined coverage across all of your instances in the chart and shows coverage for individual instances in the table under the chart\. The table also includes the following information for each instance: 

+ **Instance Type** – The instance type, such as **t2\.micro**\.

+ **Platform** – The instance operating system, such as **Linux/UNIX**\.

+ **Tenancy** – The instance tenancy, such as **Default** or **Dedicated**\.

+ **Region** – The region in which the instance is located\.

+ **Average coverage** – The percentage of running hours that were covered by matching RIs\.

+ **RI covered hours** – The number of running hours that were covered by matching RIs\.

+ **On\-demand hours** – The number of running hours for On\-Demand Instances\.

+ **Total running hours** – The total number of running hours\.

You can use this information to track how many hours you use, and how many of those hours are covered by RIs\.

The daily chart displays the number of RI hours that your account used on a daily basis for the last three months\. It uses the same filters and options as the Cost and Usage reports\. The monthly chart displays your RI coverage for the previous 12 months, listed by month\. It uses the same filters and options as the Cost and Usage reports\. 

## Saving a Report<a name="edit-save-reports"></a>

After you finish editing the Cost Explorer settings for your new report, choose **Save as\.\.\.**\. Enter a name for your report, and then choose **Save Report**\. 