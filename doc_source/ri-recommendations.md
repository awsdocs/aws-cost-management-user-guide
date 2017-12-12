# Getting Reserved Instance Recommendations<a name="ri-recommendations"></a>

If you enabled Cost Explorer, you automatically get Reserved Instance \(RI\) purchase recommendations that could help you reduce your costs\. RIs provide a discounted hourly rate \(up to 75%\) compared to On\-Demand pricing\. Cost Explorer generates your RI recommendations by identifying your On\-Demand EC2 usage during a specific time period and collecting your usage into categories that are eligible for an RI\. After Cost Explorer has these categories, it simulates every combination of RIs in each category of usage to identify the best number of each type of RI to purchase to maximize your estimated savings\. For example, Cost Explorer automatically aggregates your Linux, Shared tenancy, and c4 family usage in the US West \(Oregon\) region and recommends that you buy size\-flexible regional RIs to apply to the c4 family usage\. Cost Explorer recommends the smallest size instance in an instance family\. This makes it easier to purchase a size\-flexible RI\. Cost Explorer also shows the equal number of Normalized Units so that you can purchase any instance size you wish\. For this example, your RI recommendation would be for `c4.large`, because that is the smallest size instance in the c4 instance family\.

Cost Explorer bases its recommendations on usage of the past seven, 30, or 60 days by the master \(payer\) account and all member accounts in your organization\. Cost Explorer ignores usage that is already covered by an RI\. Cost Explorer updates your recommendations at least once every 24 hours\.

**Note**  
Cost Explorer does not forecast your Amazon EC2 usage, or take forecasts into account when recommending RIs\. Instead, Cost Explorer assumes that your historical usage reflects your future usage when determining which RIs to recommend\. Recommendations are for RIs scoped to Region, not AZ, and your estimated savings reflects the application of those RIs to your EC2 instance usage\.


+ [RI Recommendations for Size\-Flexible RIs](#rex-flex)
+ [Viewing the Cost Explorer RI Recommendations](#viewing-rex)
+ [Reading the Cost Explorer RI Recommendations](#reading-rex)
+ [Modifying Your RI Recommendations](#modifying-rex)
+ [Saving Your RI Recommendations](#saving-rex)
+ [Using Your RI Recommendations](#using-rex)

## RI Recommendations for Size\-Flexible RIs<a name="rex-flex"></a>

Cost Explorer also considers the benefits of size\-flexible regional RIs when generating your EC2 RI purchase recommendations\. Size\-flexible regional RIs help maximize your estimated savings across eligible instance families in your recommendations\. AWS uses the concept of normalized units to compare the various sizes within an instance family\. Cost Explorer uses the smallest normalization factor to represent the instance type that it recommends\. For more information, see [Instance Size Flexibility for EC2 Reserved Instances](https://aws.amazon.com/blogs/aws/new-instance-size-flexibility-for-ec2-reserved-instances)\.

For example, let’s say you own an RI for a `c4.8xlarge`\. This RI applies to any usage of a `Linux/UNIX c4` instance with shared tenancy in the same region as the RI, such as the following instances:

+ One `c4.8xlarge` instance

+ Two `c4.4xlarge` instances

+ Four `c4.2xlarge` instances

+ Sixteen `c4.large` instances

It also includes combinations of EC2 usage, such as one `c4.4xlarge` and eight `c4.large` instances\.

If you own an RI that is smaller than the instance that you are running, you will be charged the prorated, On\-Demand price for the excess\. This means that you could buy an RI for a `c4.4xlarge`, use a `c4.4xlarge` instance most of the time, but occasionally scale up to a `c4.8xlarge` instance\. Some of your `c4.8xlarge` usage is covered by the purchased RI, and the rest is charged at On\-Demand prices\. For more information, see [How Reserved Instances Are Applied](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/apply_ri.html) in the *Amazon Elastic Compute Cloud User Guide*\.

## Viewing the Cost Explorer RI Recommendations<a name="viewing-rex"></a>

To view your RI recommendations, use the following procedure\. 

**To view your RI recommendations**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

   The console opens to the **Dashboard**, where you can see your current month\-to\-date usage graphs\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the **Cost Explorer** page, choose **Launch Cost Explorer**\.

1. On the navigation bar, choose the menu, and then choose **Recommendations**\. The default recommendation is for RIs with a one\-year term and a payment option of Partial Upfront \(based on your previous 7 days of usage\)\.

## Reading the Cost Explorer RI Recommendations<a name="reading-rex"></a>

At the top of the RI recommendation page there are three numbers, and a right pane has four parameters\. The numbers are your **Estimated Annual Savings**, your **Savings vs\. On\-Demand**, and your **Purchase Recommendations**\. The parameters control what settings Cost Explorer uses to generate your recommendations\. Your **Estimated Annual Savings** is how much Cost Explorer calculates that you could save by purchasing all the recommended RIs\. Your **Savings vs\. On\-Demand** is your estimated savings as a percentage of your current costs\. Your **Purchase Recommendations** is how many different RI purchase options that Cost Explorer found for you\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

At the bottom of the page are three main savings estimates\. The table shows your different purchase recommendations and details about them\. If you want to see the usage that Cost Explorer based a recommendation on, choose the **View Associated EC2 Usage** link in the recommendation details\. This takes you to a report that shows the exact parameters that Cost Explorer used to generate your recommendation\. The report also shows your costs and associated usage grouped by **Purchase Option**, so that you can view the On\-Demand Instance usage that your recommendation is based on\.

You can sort your recommendations by **Monthly Estimated Savings**, **Upfront RI Cost**, **Purchase recommendation**, or **Instance Type**\.

## Modifying Your RI Recommendations<a name="modifying-rex"></a>

You can change the information that Cost Explorer uses when it creates your recommendations, and you can also change the types of recommendations that you want\. This allows you to see recommendations for the RIs that work best for you, such as All UpFront RIs with a one\-year term, based on your last 30 days of usage\. 

**Note**  
Instead of forecasting your future usage, Cost Explorer assumes that your future usage is the same as your previous usage\. Cost Explorer also assumes that you are renewing any expiring RIs\.

**To modify Your RI recommendations**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

   The console opens to the **Dashboard**, where you can see your current month\-to\-date usage graphs\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the **Cost Explorer** page, choose **Launch Cost Explorer**\.

1. In the navigation bar, choose the menu, and then choose **Recommendations**\.

1. On the parameter pane, change the parameters that you want to change\. Your estimated savings update automatically\.

   1. For **RI term**, select the RI term that you want\.

   1. For **Offering class**, select the RI class that you want\.

   1. For **Payment option**, select the purchase option that you want\.

   1. For **Based on the past**, select how many days of usage that you want your RI recommendations to be based on\.

## Saving Your RI Recommendations<a name="saving-rex"></a>

You can save your RI recommendations as a CSV file\.

**To save your RI recommendations**

1. On the **Reserved Instance Recommendations** page, on the parameter pane, change the parameters that you want to change\. Your estimated savings update automatically\.

1. Above the recommendation table, choose **Download CSV**\.

## Using Your RI Recommendations<a name="using-rex"></a>

To purchase the recommended RIs, you can go directly to the [Amazon EC2 RI Purchase Console](https://console.aws.amazon.com/ec2/v2/home?region=us-east-1#ReservedInstances:sort=reservedInstancesId), or you can save a CSV file of your recommendations and purchase them at a later date\. 

****

1. On the **Reserved Instance Recommendations** page, choose **EC2 RI Purchase Console** to go to the Amazon EC2 Purchase Console\.

1. Purchase your RIs following the instructions at [Buying Reserved Instances](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ri-market-concepts-buying.html) in the Amazon EC2 User Guide for Linux Instances\.