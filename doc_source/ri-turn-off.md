# Turning Off Reserved Instance Sharing<a name="ri-turn-off"></a>

The master account of an organization can turn off Reserved Instance \(RI\) sharing for member accounts in that organization\. This means that Reserved Instances are not shared between that member account and other member accounts\. You can change this preference multiple times\. Each estimated bill is computed using the last set of preferences\. The final bill for the month is calculated based on the preferences set at midnight UTC time, on the last day of the month\. 

**Important**  
Turning off Reserved Instance sharing can result in a higher monthly bill\.

**To turn off shared Reserved Instances**

You can turn off Reserved Instance \(RI\) sharing for individual member accounts\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Expand **RI discount sharing** by selecting the arrow symbol\. 

1. Under **RI discount sharing enabled**, select the accounts that you want to disable RI sharing for\. 

1. Choose **Add to list** to add the accounts to the **RI discount sharing disabled** accounts\.

1. Choose **Save preferences**\.

1. In the **Manage RI Discount and Credit Sharing** dialog box, choose **Save**\.

**To turn on shared Reserved Instances**

If shared Reserved Instances is turned off for an account and you want to turn it back on, you can use the same console page to turn sharing on\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Expand **RI discount sharing** by selecting the arrow symbol\. 

1. Under **RI discount sharing disabled**, select the accounts that you want to enable RI sharing for\. 

1. Choose **Remove from list** to remove the accounts from the **RI discount sharing disabled** accounts\.

1. Choose **Save preferences**\.

1. In the **Manage RI Discount and Credit Sharing** dialog box, choose **Save**\.