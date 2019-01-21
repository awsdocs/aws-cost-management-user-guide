# AWS Credits<a name="useconsolidatedbilling-credits"></a>

AWS credits are applied to bills to help cover costs that are associated with eligible services\. For more information about eligible services, see [Redeem Your AWS Promotional Credit](https://aws.amazon.com/awscredits/)\. Credits are applied until they are exhausted or expire\. The following rules specify how AWS applies credits to bills for single accounts and for organizations:
+ The billing cycle begins on the first day of each month\.
+ If an account is owned on the first day of the month by an individual who is not part of an organization but who later in the month joins one, AWS applies credits to that individual's bill for their usage from the first day of the month until the day that they join the organization\.
+ If an account is owned on the first day of the month by an organization, AWS applies credits redeemed by the payer account or by any linked account to the organization's bill\.
+ If an individual leaves an organization during the month, AWS begins applying credits to the single account on the first day of the following month\.

For example, assume that Susan owns a single account on the first of the month and then joins an organization during the month\. Assume also that she redeems her credits on any day after she joins the organization\. AWS applies her credits to her account for usage she incurred from the 1st to the day that she joined the organization\. However, from the first of the following month on, AWS applies the credits to the organization's bill\. If Susan leaves the organization, any credits she redeems are also applied to the organization's bill until the first of the month following her departure\. On that day, AWS again applies Susan's credits to her bill\.

If you are more comfortable with numbers, assume that Susan owns a single account on January 1 and joins an organization on January 11\. If Susan redeems 100 dollars of credits on January 18, AWS applies these to her account for the usage that she incurred from January 1 to January 11\. From February on, Susan's credits are applied to the organization's consolidated bill\. If Susan has 50 dollars of credits and leaves the organization on April 16, her credits are applied to the organization's consolidated bill for April\. From May on, Susan's credits are applied to Susan's account\.

You can turn off credit sharing on the **Preferences** page on the Billing and Cost Management console\. The following rules specify how credits are applied to bills for single accounts and for organizations when credit sharing is turned off:
+ The billing cycle begins on the first day of each month\.
+ Credits are applied to only the account that received the credits\.
+ Bills are calculated using the credit sharing preference that is active on the last day of the month\.
+ In an organization, only the payer account can turn credit sharing off or on\. The credit sharing preference applies to all accounts in an organization\.<a name="turn-off-credit-sharing"></a>

**To turn off credit sharing**

You can turn off credit sharing through the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Preferences**\.

1. Select **Disable credit sharing**\. 

1. Choose **Save preferences**\.