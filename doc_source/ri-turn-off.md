# Reserved instances and Savings Plans discount sharing<a name="ri-turn-off"></a>

The management account of an organization can turn off Reserved Instance \(RI\) discount and Savings Plans discount sharing for any accounts in that organization, including the management account\. This means that RIs and Savings Plans discounts aren't shared between any accounts that have sharing turned off\. To share an RI or Savings Plans discount with an account, both accounts must have sharing turned on\. This preference isn't permanent, and you can change it at any time\. Each estimated bill is computed using the last set of preferences\. The final bill for the month is calculated based on the preferences set at 23:59:59 UTC time on the last day of the month\.

**Important**  
Turning off RI and Savings Plans discount sharing can result in a higher monthly bill\.

**Topics**
+ [Turning off shared reserved instances and Savings Plans discounts](#ri-turn-off-process)
+ [Turning on shared reserved instances and Savings Plans discounts](#ri-turn-on-process)

## Turning off shared reserved instances and Savings Plans discounts<a name="ri-turn-off-process"></a>

You can turn off RI sharing discounts for individual member accounts\.

You can't share Savings Plans with a set of accounts\. You can choose to restrict the benefit to the account that purchased the Savings Plans, but not share amongst a group of accounts\.

**To turn off shared reserved instances and Savings Plans discounts**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Billing preferences**\.

1. Expand **RI and Savings Plans discount sharing** by selecting the arrow symbol\. 

1. Under **RI and Savings Plans discount sharing enabled**, select the accounts that you want to disable RI discount sharing for\.

1. Choose **Add to list** to add the accounts to the **RI and Savings Plans discount sharing disabled** accounts\.

1. Choose **Save preferences**\.

1. In the **Manage RI Discount, Savings Plans Discount and Credit Sharing** dialog box, choose **Save**\.

## Turning on shared reserved instances and Savings Plans discounts<a name="ri-turn-on-process"></a>

You can use the console to turn RI sharing discounts back on for an account\.

You can share Savings Plans with a set of accounts\. You can either choose to not share the benefit with other accounts, or to open up line item eligibility for the entire consolidated billing family of accounts\.

**To turn on shared reserved instances discounts**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.
**Note**  
Ensure you're logged in to the management account of your AWS Organizations\.

1. In the navigation pane, choose **Billing Preferences**\.

1. Expand **RI and Savings Plans discount sharing** by selecting the arrow symbol\. 

1. Under **RI and Savings Plans discount sharing disabled**, select the accounts that you want to enable RI discount sharing for\.

1. Choose **Remove from list** to remove the accounts from the **RI and Savings Plans discount sharing disabled** accounts\.

1. Choose **Save preferences**\.

1. In the **Manage RI Discount and Credit Sharing** dialog box, choose **Save**\.