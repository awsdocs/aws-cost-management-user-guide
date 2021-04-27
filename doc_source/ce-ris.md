# Understanding your reservations with Cost Explorer<a name="ce-ris"></a>

A significant part of using AWS involves balancing your Reserved Instance \(RI\) usage and your On\-Demand Instance usage\. To help with that, Cost Explorer provides a couple of tools to help you understand where your greatest RI costs are and how you can potentially lower your costs\. Cost Explorer does this by providing you with an overview of your current reservations, showing your RI utilization and coverage, and calculating recommended RIs that could save you money if you purchase them\.

## Using your RI reports<a name="using-ri-reports"></a>

You can use the **RI reports** page in the Cost Explorer console to see how many reservations you have, how much your reservations are saving you compared to similar usage of On\-Demand Instances, and how many of your reservations are expiring this month\.

Cost Explorer breaks down your reservations and savings by service and lists your potential savings: that is, the costs of On\-Demand usage compared to what that usage could cost you with an RI\.

To take advantage of your potential savings, see [Accessing Reserved Instance Recommendations](ri-recommendations.md)\.

## Managing your reservation expiration alerts<a name="managing-ri-alerts"></a>

You can track your reservations and their expiration in Cost Explorer\. Reservation expiration alerts enable you to receive email alerts 7, 30, or 60 days in advance before your reservation expiration date\. These notifications also alert you on the date of expiration and can be sent to up to 10 email recipients\. Reservation expiration alerts are supported for Amazon EC2, Amazon RDS, Amazon Redshift, Amazon ElastiCache, and Amazon Elasticsearch Service reservations\.

**To turn on reservation expiration alerts**

1. Sign in to the AWS Management Console and open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. Navigate to the **Overview** page under the **Reservations** section\.

1. In the **Reservation expiring** section, choose **Manage alerts** in the upper right corner\.

1. Select the check boxes for when you want to receive your alerts\.

1. Enter email addresses for who you want to notify\. You can add up to 10 emails\. 

1. Choose **Save**\. 

AWS begins monitoring your reservation portfolio and automatically sends alerts at your preference\.