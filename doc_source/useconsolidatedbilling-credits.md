# AWS credits<a name="useconsolidatedbilling-credits"></a>

AWS credits are applied to bills to help cover costs that are associated with eligible services\. For more information about eligible services, see [Redeem Your AWS Promotional Credit](https://aws.amazon.com/awscredits/)\. Credits are applied until they are exhausted or they expire\.
+ [Applying AWS credits](#apply-credits)
+ [Applying AWS credits across single and multiple accounts](#credits-for-orgs)
+ [Sharing AWS credits](#credit-sharing)

## Applying AWS credits<a name="apply-credits"></a>

Credits are applied using the following process:

1. [Selecting credits to apply](#selecting-credits-to-apply)

1. [Selecting where to apply credits](#selecting-usage-to-apply-credits-to)

## Selecting credits to apply<a name="selecting-credits-to-apply"></a>

When selecting credits to apply, AWS prioritizes the credits based on the following parameters:

1. Soonest to expire

1. Least number of applicable products

1. Oldest credit

For example, Jorge has two credits available to him\. Credit one is for 10 dollars, it expires January 2019, and it can be used for either Amazon S3 or Amazon EC2\. Credit two is for 5 dollars, it expires December 2019, and it can be used only for Amazon EC2\. Jorge has sufficient AWS charges to apply all credits\. AWS selects credit one for application first because it expires sooner than credit two\.

## Selecting where to apply credits<a name="selecting-usage-to-apply-credits-to"></a>

When selecting usage to apply credits to, AWS prioritizes the credits based on the following:

1. Account that owns the credit

1. Account with the highest spend

1. Service with the highest spend within that account

1. SKU with the highest spend within that service

AWS repeats this process until the applicable credits are exhausted\.

AWS applies the credit to the largest available charge across all eligible sellers of record\. This means that AWS tries to apply your credits before they expire\. So they might use a generic credit for a specific service\.

For example, Jorge has two credits available to him\. Credit one is for 10 dollars, expires January 2019, and can be used for either Amazon S3 or Amazon EC2\. Credit two is for 5 dollars, expires December 2019, and can be used only for Amazon EC2\. Jorge has two AWS charges: 100 dollars for Amazon EC2 and 50 dollars for Amazon S3\. AWS applies credit one, which expires in January, to the Amazon EC2 charge, which leaves him with a 90\-dollar Amazon EC2 charge and a 50\-dollar Amazon S3 charge\. AWS applies credit two to the remaining 90 dollars of Amazon EC2 usage, and Jorge has to pay 85 dollars for Amazon EC2 and 50 dollars for Amazon S3\. He has now used all of his credits\.

## Applying AWS credits across single and multiple accounts<a name="credits-for-orgs"></a>

The following rules specify how AWS applies credits to bills for single accounts and for organizations by default \(Credit sharing turned on\):
+ The billing cycle begins on the first day of each month\.
+ If an account is owned on the first day of the month by an individual who is not part of an organization, but joins the organization later in the month, AWS applies credits that are owned by the individual to that individual's bill for their usage for that month\. The next month, AWS applies credits to the organization the individual joined\.
+ If an account is owned on the first day of the month by an organization, AWS applies credits redeemed by the payer account or by any linked account to the organization's bill, regardless of whether the account owner moves out of the organization later that month\.
+ If an individual leaves an organization during the month, AWS begins applying credits to the individual’s account on the first day of the following month\.
+ Credits are shared with all accounts that join an organization at any point in the month\. However, the organization’s shared credit pool consists of only credits from accounts that have been part of the organization since the first day of the month\.

For example, assume that Susan owns a single account on the first of the month and then joins an organization during the month\. Also assume that she redeems her credits on any day after she joins the organization\. AWS applies her credits to her account for usage she incurred from the first of the month to the day that she joined the organization\. However, from the first day of the next month, AWS applies the credits to the organization's bill\. If Susan leaves the organization, any credits that she redeems are also applied to the organization's bill until the first of the month after her departure\. Starting the day after her departure, AWS applies Susan's credits to her bill instead of the organization's bill\.

In another example, assume that Susan owns a single account on January 1 and joins an organization on January 11\. If Susan redeems 100 dollars of credits on January 18, AWS applies them to her account for the usage that she incurred for the month of January\. From February 1st onwards, Susan's credits are applied to the organization's consolidated bill\. If Susan has 50 dollars of credits and leaves the organization on April 16, her credits are applied to the organization's consolidated bill for April\. From May onward, Susan's credits are applied to her account\.

## Sharing AWS credits<a name="credit-sharing"></a>

You can turn off credit sharing on the **Preferences** page on the Billing and Cost Management console\. The following rules specify how credits are applied to bills for single accounts and for organizations when credit sharing is turned off:
+ The billing cycle begins on the first day of each month\.
+ Credits are applied to only the account that received the credits\.
+ Bills are calculated using the credit sharing preference that is active on the last day of the month\.
+ In an organization, only the payer account can turn credit sharing off or on\. The credit sharing preference applies to all accounts in an organization\.<a name="turn-off-credit-sharing"></a>

**To turn off credit sharing**

You can turn off credit sharing through the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Preferences**\.

1. Select **Disable credit sharing**\. 

1. Choose **Save preferences**\.