# Using the default Cost Explorer reports<a name="ce-default-reports"></a>

Cost Explorer provides you with a couple of default reports\. You can't modify these reports, but you can use them to create your own custom reports\.
+ [Cost and usage reports](#ce-cost-usage-reports)
+ [Reserved Instance reports](#ce-ri-reports)

## Cost and usage reports<a name="ce-cost-usage-reports"></a>

Cost Explorer provides you with the following reports for understanding your costs\.
+ [AWS Marketplace](#ce-marketplace)
+ [Daily costs](#ce-daily-costs)
+ [Monthly costs by linked account](#ce-linked-costs)
+ [Monthly costs by service](#ce-service-costs)
+ [Monthly EC2 running hours costs and usage](#ce-ec2-running-costs)

### AWS Marketplace<a name="ce-marketplace"></a>

The **AWS Marketplace** report shows how much you have spent through AWS Marketplace\.

### Daily costs<a name="ce-daily-costs"></a>

The **Daily costs** report shows how much you've spent in the last six months, along with how much you're forecasted to spend over the next month\.

### Monthly costs by linked account<a name="ce-linked-costs"></a>

The **Monthly costs by linked account** report shows your costs for the last six months, grouped by linked, or member account\. The top five member accounts are shown by themselves, and the rest are grouped into one bar\.

### Monthly costs by service<a name="ce-service-costs"></a>

The **Monthly costs by service** report shows your costs for the last six months, grouped by service\. The top five services are shown by themselves, and the rest are grouped into one bar\.

### Monthly EC2 running hours costs and usage<a name="ce-ec2-running-costs"></a>

The **Monthly EC2 running hours costs and usage** report shows how much you have spent on active Reserved Instances \(RIs\)\.

## Reserved Instance reports<a name="ce-ri-reports"></a>

Cost Explorer provides you with the following reports for understanding your reservations\.

The reservation reports show your Amazon EC2 coverage and utilization in either hours or normalized units\. Normalized units enable you to see your Amazon EC2 usage for multiple sizes of instances in a uniform way\. For example, suppose you run an `xlarge` instance and a `2xlarge` instance\. If you run both instances for the same amount of time, the `2xlarge` instance uses twice as much of your reservation as the `xlarge` instance, even though both instances show only one instance\-hour\. Using normalized units instead of instance\-hours, the `xlarge` instance used 8 normalized units, and the `2xlarge` instance used 16 normalized units\. For more information, see [Instance Size Flexibility for EC2 Reserved Instances](https://aws.amazon.com/blogs/aws/new-instance-size-flexibility-for-ec2-reserved-instances)\.
+ [RI utilization reports](#ce-utilization-views)
+ [RI coverage reports](#ce-coverage-views)

### RI utilization reports<a name="ce-utilization-views"></a>

The RI Utilization reports show how much of your Amazon EC2, Amazon Redshift, Amazon RDS, Amazon Elasticsearch Service, and Amazon ElastiCache Reserved Instance \(RIs\) that you use, how much you saved by using RIs, how much you overspent on RIs, and your net savings from purchasing RIs during the selected time range\. This helps you to see if you have purchased too many RIs\. 

The RI Utilization charts display the number of RI hours that your account uses, helping you to understand and monitor your combined usage \(utilization\) across all of your RIs and services\. It also shows how much you saved over On\-Demand Instance costs by purchasing a reservation, the amortized costs of your unused reservations, and your total net savings from purchasing reservations\. AWS calculates your total net savings by subtracting the costs of your unused reservations from your reservations savings\. 

The following table shows an example of potential savings \(all costs are in USD\)\.


**RI utilization example**  

| **Account** | **RI utilization** | **RI hours purchased** | **RI hours used** | **RI hours unused** | **On\-Demand cost of RI hours used** | **Effective RI cost** | **Net savings** | **Total potential savings** | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Martha  |  0\.50  |  100  |  50  |  50  |  $200  |  $150  |  $50  |  $250  | 
|  Liu Jie  |  0\.75  |  100  |  75  |  25  |  $300  |  $150  |  $150  |  $250  | 
|  Saanvi  |  1\.00  |  50  |  50  |  0  |  $200  |  $75  |  $125  |  $125  | 

As shown in the preceding table, Martha, Liu Jie, and Saanvi purchase RIs at $1\.50 an hour and On\-Demand hours at $4\.00 an hour\. Breaking down this example further, you can see how much each of them saves by purchasing RIs:
+ Martha purchases 100 RI hours for $150\. She uses 50 hours, which would cost $200 if she used On\-Demand Instances\. She saves $50, which is the cost of 50 On\-Demand hours minus the cost of the RI\. She could optimize her savings by using more of her purchased RI hours, by converting her RI to cover other instances, or by selling her RIs on the RI Marketplace\. For more information about selling an RI on the RI Marketplace, see [Selling on the Reserved Instance Marketplace](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-general.html) in the [Amazon EC2 User Guide for Linux Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/)\. 
+ Liu Jie purchases 100 RI hours for $150\. He uses 75 of them, which would cost $300 if he used On\-Demand Instances\. So he saves $150, which is the cost of 300 On\-Demand hours minus the cost of the RI\.
+ Saanvi purchases 50 RI hours for $75\. She uses all 50 of them, which would cost $200 if she used On\-Demand Instances\. So she saves $125, which is the cost of 200 On\-Demand hours minus the cost of the RI\.

The reports allow you to define a utilization threshold, known as a *utilization target*, and identify RIs that meet your utilization target and RIs that are underutilized\. The chart shows RI utilization as the percentage of purchased RI hours that are used by matching instances, rounded to the nearest percentage\. 

Target utilization is shown on the chart as a dotted line in the chart and in the table below the chart as a colored RI utilization status bar\. RIs with a red status bar are RIs with no hours used\. RIs with a yellow status bar are under your utilization target\. RIs with a green status bar have met your utilization target\. Instances with a gray bar aren't using reservations\. You can change the utilization target in the **Display Options** section\. To remove the utilization target line from the chart, clear the **Show target line on chart** check box\. You can also create budgets that enable AWS to notify you if you fall below your utilization targets\. For more information, see [Managing your costs with AWS Budgets](budgets-managing-costs.md)\.

You can filter the chart to analyze the purchasing accounts, instance types, and more\. RI reports use a combination of RI\-specific filters and regular Cost Explorer filters\. The RI\-specific filters are available only for the Cost Explorer RI Utilization and RI Coverage reports\. They aren't available anywhere else that AWS uses Cost Explorer filters\. The following filters are available:
+ **Availability Zone** – Filter your RI usage by specific Availability Zones\.
+ **Instance Type** – Filter your RI usage by specific instance types, such as **t2\.micro** or **m3\.medium**\. This also applies to Amazon RDS instance classes, such as **db\.m4**, and Amazon Redshift and ElastiCache node types, such as **dc2\.large**\.
+ **Linked Account** – Filter your reservations by specific member accounts\.
+ **Platform** – Filter your RI usage by platform, such as **Linux** or **Windows**\. This also applies to Amazon RDS database engines\.
+ **Region** – Filter your RI usage by specific regions, such as **US East \(N\. Virginia\)** or **Asia Pacific \(Singapore\)**\.
+ **Scope** \(Amazon EC2\) – Filter your Amazon EC2 usage to show RIs that are purchased for use in specific Availability Zones or regions\.
+ **Tenancy** \(Amazon EC2\) – Filter your Amazon EC2 usage by tenancy, such as **Dedicated** or **Default**\. An RI with a **Dedicated** tenancy is reserved for a single tenant, and an RI with a **Default** tenancy might share hardware with another RI\.

In addition to changing your utilization target and filtering your RIs, you can choose a single RI or a group of RIs to show in the chart\. To choose a single RI or a selection of RIs to see in the chart, select the check box next to the RI in the table below the chart\. You can select up to 10 leases at one time\. 

Cost Explorer shows the combined utilization across all of your RIs in the chart and shows utilization for individual RI reservations in the table below the chart\. The table also includes a subset of the information for each RI reservation\. You can find the following information for each reservation in the downloadable \.csv file:
+ **Account Name** – The name of the account that owns the RI reservation\.
+ **Subscription ID** – The unique subscription ID for the RI reservation\.
+ **Reservation ID** – The unique ID for the RI reservation\.
+ **Instance Type** – The RI instance class, instance type, or node type, such as **t2\.micro**, **db\.m4**, or **dc2\.large**\. 
+ **RI Utilization** – The percentage of purchased RI hours that were used by matching instances\.
+ **RI Hours Purchased** – The number of purchased hours for the RI reservation\.
+ **RI Hours Used** – The number of purchased hours that were used by matching instances\.
+ **RI Hours Unused** – The number of purchased hours that weren't used by matching instances\.
+ **Account ID** – The unique ID of the account that owns the RI reservation\.
+ **Start Date** – The date that the RI starts\.
+ **End Date** – The date that the RI expires\.
+ **Numbers of RIs** – The numbers of RIs that are associated with the reservation\.
+ **Scope** – Whether this RI is for a specific Availability Zone or region\.
+ **Region** – The region that the RI is available in\.
+ **Availability Zone** – The Availability Zone that the RI is available in\.
+ **Platform** \(Amazon EC2\) – The platform that this RI is for\.
+ **Tenancy** \(Amazon EC2\) – Whether this RI is for a shared or dedicated instance\.
+ **Payment Option** – Whether this RI is a Full Upfront, Partial Upfront, or No Upfront RI\.
+ **Offering Type** – Whether this RI is Convertible or Standard\.
+ **On\-Demand Cost Equivalent** – The cost of the RI hours that you used, based on the public On\-Demand prices\.
+ **Amortized Upfront Fee** – The upfront cost of this reservation, amortized over the RI period\.
+ **Amortized Recurring Charges** – The monthly cost of this reservation, amortized over the RI period\.
+ **Effective RI Cost** – The combined amortized upfront and amortized recurring costs of the RI hours that you purchased\.
+ **Net Savings** – The amount that Cost Explorer estimates that you saved by purchasing reservations\.
+ **Potential Savings** – The total potential savings that you might see if you use your entire RI\.
+ **Average On\-Demand Rate** – The On\-Demand rate of the RI hours that you used\. When you view the On\-Demand rates for an extended period of time, the On\-Demand rate reflects any price changes made during that time period\. 

  If there isn't any usage for the given time period, the average On\-Demand rate shows **N/A**\.
+ **Total Asset Value** – The effective cost of your reservation term\. The total asset value takes both your start date and either your end date or your cancellation date into consideration\.
+ **Effective Hourly Rate** – The effective hourly rate of your total RI costs\. The hourly rate takes both your upfront fees and your recurring fees into consideration\.
+ **Upfront Fee** – The one\-time upfront cost of the RI hours that you purchased\.
+ **Hourly Recurring Fee** – The effective hourly rate of your monthly RI costs\. The hourly recurring fee takes only your recurring fees into consideration\.
+ **RI Cost For Unused Hours** – The amount that you spent on RI hours that you didn't use\.

You can use this information to track how many RI usage hours you used and how many RI hours you reserved but didn't use during the selected time range\. 

The Daily RI Utilization chart displays your RI utilization for the previous three months on a daily basis\. The Monthly RI Utilization chart displays your RI utilization for the previous 12 months on a monthly basis\. 

### RI coverage reports<a name="ce-coverage-views"></a>

The RI Coverage reports show how many of your Amazon EC2, Amazon Redshift, Amazon RDS, Amazon Elasticsearch Service, and Amazon ElastiCache instance hours are covered by RIs, how much you spent on On\-Demand Instances, and how much you might have saved had you purchased more reservations\. This enables you to see if you have under\-purchased RIs\. 

The RI coverage charts display the percentage of instance hours that your account used that were covered by reservations, helping you to understand and monitor the combined coverage across all of your RIs\. It also shows how much you spent on On\-Demand Instances and how much you might have saved had you purchased more reservations\.

You can define a threshold for how much coverage you want from RIs, known as a *coverage target*, which enables you to see where you can reserve more RIs\. 

Target coverage is shown on the chart as a dotted line, and the average coverage is shown in the table below the chart as a colored status bar\. Instances with a red status bar are instances with no RI coverage\. Instances with a yellow status bar are under your coverage target\. Instances with a green status bar have met your coverage target\. Instances with a gray bar aren't using reservations\. You can change the coverage target in the **Display Options** section\. To remove the coverage target line from the chart, clear the **Show target line on chart** check box\. You can also create coverage budgets that enable AWS to notify you if you fall below your coverage target\. For more information, see [Managing your costs with AWS Budgets](budgets-managing-costs.md)\.

The RI coverage reports use the Cost Explorer filters instead of the RI Utilization filters\. You can filter the chart to analyze the purchasing accounts, instance types, and more\. RI reports use a combination of RI\-specific filters and regular Cost Explorer filters\. The RI\-specific filters are available only for the Cost Explorer RI Utilization and RI Coverage reports, and aren't available anywhere else that AWS uses Cost Explorer filters\. The following filters are available:
+ **Availability Zone** – Filter your RI usage by specific Availability Zones\.
+ **Instance Type** – Filter your RI usage by specific instance types, such as **t2\.micro** or **m3\.medium**\. This also applies to Amazon RDS instance classes such as **db\.m4**\.
+ **Linked Account** – Filter your RI usage by specific member accounts\.
+ **Platform** – Filter your RI usage by platform, such as **Linux** or **Windows**\. This also applies to Amazon RDS database engines\.
+ **Region** – Filter your RI usage by specific regions, such as **US East \(N\. Virginia\)** or **Asia Pacific \(Singapore\)**\.
+ **Scope** \(Amazon EC2\) – Filter your Amazon EC2 usage to show RIs that are purchased for use in specific Availability Zones or regions\.
+ **Tenancy** \(Amazon EC2\) – Filter your Amazon EC2 usage by tenancy, such as **Dedicated** or **Default**\. A **Dedicated** RI is reserved for a single tenant, and a **Default** RI might share hardware with another RI\.

In addition to changing your coverage target and filtering your instance types with the available filters, you can choose a single instance type or a group of instance types to show in the chart\. To choose a single instance type or a selection of instance types to see in the chart, select the check box next to the instance type in the table below the chart\. You can select up to 10 instances at one time\.

Cost Explorer shows the combined coverage across all of your instance types in the chart and shows coverage for individual instance types in the table below the chart\. The table also includes a subset of the information for each instance type\. You can find the following information for each instance type in the downloadable \.csv file:
+ **Instance Type** \(Amazon EC2\), **Instance Class** \(Amazon RDS\), or **Node Type** \(Amazon Redshift or Amazon ElastiCache\) – The RI instance class, instance type, or node type, such as **t2\.micro**, **db\.m4**, or **dc2\.large**\. 
+ **Database Engine** \(Amazon RDS\) – Filter your Amazon RDS coverage to show RIs that cover a specific database engine, such as **Amazon Aurora**, **MySQL**, or **Oracle**\.
+ **Deployment Option** \(Amazon RDS\) – Filter your Amazon RDS coverage to show RIs that cover a specific deployment option, such as **Multi\-AZ** deployments\.
+ **Region** – The region that the instance ran in, such as **us\-east\-1**\.
+ **Platform** \(Amazon EC2\) – The platform that this RI is for\.
+ **Tenancy** \(Amazon EC2\) – Whether this RI is for a shared, dedicated, or host instance\.
+ **Average Coverage** – The average number of usage hours that a reservation covers\.
+ **RI Covered Hours** – The number of usage hours that a reservation covers\.
+ **On\-Demand Hours** – The number of usage hours that aren't covered by reservations\.
+ **On\-Demand Cost** – The amount that you spent on On\-Demand Instances\.
+ **Total Running Hours** – The total number of usage hours, both covered and uncovered\.

You can use this information to track how many hours you use and how many of those hours are covered by RIs\.

The daily chart displays the number of RI hours that your account used on a daily basis for the last three months\. The monthly chart displays your RI coverage for the previous 12 months, listed by month\. 