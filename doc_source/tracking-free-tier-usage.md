# Tracking Your AWS Free Tier Usage<a name="tracking-free-tier-usage"></a>

You can track your AWS Free Tier usage to help you stay under the free tier limits\. AWS automatically provides alerts through AWS Budgets to notify you by email when you exceed the free tier limits or when you are forecast to go over the free tier limits\. You can also view the **Top Free Tier Services by Usage** table on the Billing and Cost Management dashboard to see which five services you've used the most and how much you've used them\.


+ [AWS Free Tier Usage Alerts Using AWS Budgets](#free-budget)
+ [Top Free Tier Services Table](#free-tier-table)

## AWS Free Tier Usage Alerts Using AWS Budgets<a name="free-budget"></a>

AWS automatically provides AWS Free Tier usage alerts using AWS Budgets to help you track your free tier usage\. These budgets allow AWS to notify you when you're close to exceeding the free tier limits or are forecast to exceed the free tier limits\. You can also use the budgets to plan how you use AWS resources to avoid exceeding the free tier limits\. Any usage over the free tier limits is charged at the regular rate\. 

When you exceed the free tier limits or are forecast to exceed them, AWS sends an alert to the email address that you used to create your account\. You can change which email address that AWS uses for the alerts on the Billing and Cost Management console\. AWS sends the notifications when you either go over 100% of your available free tier or are forecasted to go over 101%\. The AWS Free Tier usage alert forecast does not use the Cost Explorer forecasting, and instead assumes that your usage remains steady throughout the month\. For example, if you use 50 Amazon EC2 hours over five days, the forecast assumes that you are using 50 EC2 hours every five days\. Only one notification per usage type is sent during a month\. Usage types are the units that each service uses to measure the usage of a specific type of resource\. For example, the `BoxUsage:t2.micro(Hrs)` usage type filters by the running hours of Amazon EC2 `t2.micro` instances\.

**Important**  
If you launch more AWS resources than the free tier covers in a short period of time, you can exceed the free tier limits before AWS can proactively notify you about exceeding the free tier usage limits\. If that happens, AWS still notifies you that your incurred usage exceeded the free tier limit\.

AWS Free Tier usage alerts cover non\-expiring free tier offerings, such as the first 25 GB of DynamoDB storage or the first ten custom CloudWatch metrics\. The alerts also cover free tier offerings that expire after 12 months, such as the 750 hours per month of Amazon EC2 `Windows t2.micro` instance usage and the first five GB of standard Amazon S3 storage\. Services that are not covered by the free tier usage alerts include the following:

+ AWS Directory Service

+ Amazon Lightsail

+ Amazon Redshift

+ Amazon AppStream 2\.0

+ Amazon WorkSpaces

AWS Free Tier usage alerts are enabled automatically for all individual accounts, but not for a master account in an organization in AWS Organizations\. If you are an owner of a master account in an organization, you can opt in to the usage alerts on the **Preferences** page on the Billing and Cost Management console\. The same free tier limit applies to all accounts in an organization \(both master and member accounts\), so the same budget also applies to all the accounts\. For example, if Alejandro has a member account and uses 400 Amazon EC2 hours and Mary has a member account and uses 400 Amazon EC2 hours, for a total of 800 hours, the organization has exceeded the free tier limit by 50 Amazon EC2 hours\.

**To opt in or out of AWS Free Tier usage alerts**

You can opt in to or out of the AWS Free Tier usage alerts through the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Under **Cost Management Preferences**, select **Receive Free Tier Usage Alerts** to opt in to free tier usage alerts\. To opt out, clear the **Receive Free Tier Usage Alerts** check box\.

**To change the email address for free tier usage alerts**

AWS sends free tier usage alerts to the email address that you used when you created your account\. You can change the email address on the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Under **Cost Management Preferences**, under **Receive Free Tier Usage Alerts**, for **Email Address**, type the email address where you want to receive the usage alerts\.

1. Scroll to the end of the page and choose the **Save preferences** button\.

## Top Free Tier Services Table<a name="free-tier-table"></a>

If you are eligible for the free tier and you use a free tier offering, you can track your usage with the **Top Free Tier Services by Usage** table on the dashboard of the [Billing and Cost Management console](https://console.aws.amazon.com/billing/home)\. The table doesn't appear if any of following conditions are true: 

+ You use an AWS service that doesn't offer a free tier\.

+ Your free tier has expired\.

+ You access AWS through Amazon Internet Services Pvt\. Ltd \(AISPL\)\.

+ You access AWS through AWS Organizations, but you don't use the master account\.

The **Top Free Tier Service by Usage** table shows how much you've used of the free tier limits for your top five services, along with a forecast of how much you are predicted to use by the end of the month\. The table shows usage as both a percentage of the free tier limit and as a ratio of the free tier limit\. For example, if you use 3 GB of the free tier Amazon S3 storage, the table shows 60% and `3/5 GB`\.

The table is grouped by service limit\. This means that a service might have multiple lines, and you can track each free tier limit closely\. For example, each month you get 5 GB of Amazon S3 storage and 2,000 Amazon S3 `Put` operations\. The free tier usage table will have two lines, one for `S3 - Storage` and one for `S3 - Puts`, as shown in the following screenshot\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

To see more details about your free tier usage, including all of your active free tier services, choose **View All** in the **Top Free Tier Services by Usage** table\. The detailed table includes additional information such as the free tier limits and a status icon to alert you if you have exceeded the limits, or are predicted to exceed the limits\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)