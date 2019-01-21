# Turning Off Reserved Instance Sharing<a name="ri-turn-off"></a>

The payer account of an organization can turn off Reserved Instance \(RI\) sharing for any accounts in that organization, including the payer account\. This means that Reserved Instances aren't shared between any accounts that have sharing turned off\. To share an RI with an account, both accounts must have sharing turned on\. This preference isn't permanent, and you can change it at any time\. Each estimated bill is computed using the last set of preferences\. The final bill for the month is calculated based on the preferences set at 23:59:59 UTC time on the last day of the month\.

**Important**  
Turning off RI sharing can result in a higher monthly bill\.

**To turn off shared Reserved Instances**

You can turn off RI sharing for individual linked accounts\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Expand **RI discount sharing** by selecting the arrow symbol\. 

1. Under **RI discount sharing enabled**, select the accounts that you want to disable RI sharing for\. 

1. Choose **Add to list** to add the accounts to the **RI discount sharing disabled** accounts\.

1. Choose **Save preferences**\.

1. In the **Manage RI Discount and Credit Sharing** dialog box, choose **Save**\.

**To turn on shared Reserved Instances**

If shared Reserved Instances is turned off for an account and you want to turn it back on, you can use the same console page to turn on sharing\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Expand **RI discount sharing** by selecting the arrow symbol\. 

1. Under **RI discount sharing disabled**, select the accounts that you want to enable RI sharing for\. 

1. Choose **Remove from list** to remove the accounts from the **RI discount sharing disabled** accounts\.

1. Choose **Save preferences**\.

1. In the **Manage RI Discount and Credit Sharing** dialog box, choose **Save**\.