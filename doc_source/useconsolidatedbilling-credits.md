# AWS credits<a name="useconsolidatedbilling-credits"></a>

AWS credits are automatically applied to bills to help cover costs that are associated with eligible services\. For more information about eligible services, see [Redeem Your AWS Promotional Credit](http://aws.amazon.com/awscredits/)\. Credits are applied until they are exhausted or they expire\.

For any questions about AWS credits in general or any credits that have already expired, contact AWS Support\. For more information about how to contact AWS Support, see [Getting help with AWS Billing](billing-get-answers.md)\.

**Topics**
+ [1\. Choosing the credits to apply](#selecting-credits-to-apply)
+ [2\. Choose where to apply your credits](#selecting-usage-to-apply-credits-to)
+ [3\. Applying AWS credits across single and multiple accounts](#credits-for-orgs)
+ [4\. Sharing AWS credits](#credit-sharing)

## 1\. Choosing the credits to apply<a name="selecting-credits-to-apply"></a>

This section explains how AWS credits apply in a single or standalone AWS account\. If an AWS account has more than one credit, the available credits apply in the following order:

**The order of how credits apply if an AWS account has more than one credit**

1. The soonest to expire amongst the credits

1. The credit with the least number of eligible services

1. The oldest of all credits

For example, Jorge has two credits available to him\. Credit one is for 10 dollars, it expires January 2019, and it can be used for either Amazon S3 or Amazon EC2\. Credit two is for 5 dollars, it expires December 2019, and it can be used only for Amazon EC2\. Jorge has sufficient AWS charges to apply all credits\. AWS selects credit one for application first because it expires sooner than credit two\.

**Note**  
If you have remaining, eligible usage after credit is consumed, the process will repeat until your credits are consumed or your usage is covered\.
Credit is applied to the largest services charge \(for example, Amazon EC2, Amazon S3\)\. Then, the consumption will continue in a descending pattern for the remainder of the service charges\.
Credits don't require customer selection to apply during the billing process\. AWS will automatically apply eligible credits to applicable services\.

## 2\. Choose where to apply your credits<a name="selecting-usage-to-apply-credits-to"></a>

This section shows how AWS credits apply in an AWS Organizations when credit sharing is turned on\.

**The order of how credits are applied in an AWS Organizations when credit sharing is activated**

1. Account that owns the credit is covered for the service charges

1. Credits are applied towards the AWS account with the highest spend

1. Credits are applied to the service with the highest spend within that account

1. Credits are applied to the SKU with the highest spend within that service

The process repeats until the credit is consumed, or all customer spend is covered\.

AWS applies the credit to the largest available charge across all eligible sellers of record\. This means that AWS tries to apply your credits before they expire\. So they might use a generic credit for a specific service\.

For example, Jorge has two credits available to him\. Credit one is for 10 dollars, expires January 2019, and can be used for either Amazon S3 or Amazon EC2\. Credit two is for 5 dollars, expires December 2019, and can be used only for Amazon EC2\. Jorge has two AWS charges: 100 dollars for Amazon EC2 and 50 dollars for Amazon S3\. AWS applies credit one, which expires in January, to the Amazon EC2 charge, which leaves him with a 90\-dollar Amazon EC2 charge and a 50\-dollar Amazon S3 charge\. AWS applies credit two to the remaining 90 dollars of Amazon EC2 usage, and Jorge has to pay 85 dollars for Amazon EC2 and 50 dollars for Amazon S3\. He has now used all of his credits\.

## 3\. Applying AWS credits across single and multiple accounts<a name="credits-for-orgs"></a>

The following rules specify how AWS applies credits to bills for single accounts and for organizations by default \(Credit sharing turned on\):
+ The billing cycle begins on the first day of each month\.
+ Suppose that an AWS account is owned on the first day of the month by an individual who isn't part of an organization\. Later in the month, that individual account joins an organization\. In this situation, AWS applies that individual's credits to their individual bill for their usage for that month\. That is, AWS applies the credit up to the day that the individual joined the organization\.
**Note**  
An individual's account credits don't cover the account usage from the day that the individual joined the organization to the end of that month\. For this period, the individual's account credits aren't applied to the bill\. However, starting the next month, AWS applies the individual’s account credits to the organization\.
+ If an account is owned by an organization at the start of the month, AWS applies credits redeemed by the payer account or by any linked account to the organization's bill, even if the account leaves the organization in the same month\. The start of the month begins one second after 0:00 UTC\+0\. For example, assume that an account leaves an organization on August 1\. AWS still applies the August credits the account redeemed to the organization's bill because the account belonged to the organization during that calendar month\.
+ If an individual leaves an organization during the month, AWS begins applying credits to the individual’s account on the first day of the following month\.
+ Credits are shared with all accounts that join an organization at any point in the month\. However, the organization’s shared credit pool consists of only credits from accounts that have been part of the organization since the first day of the month\.

For example, assume that Susan owns a single account on the first day of the month and then joins an organization during the month\. Also assume that she redeems her credits on any day after she joins the organization\. AWS applies her credits to her account for usage she incurred from the first of the month to the day that she joined the organization\. However, from the first day of the next month, AWS applies the credits to the organization's bill\. If Susan leaves the organization, any credits that she redeems are also applied to the organization's bill until the first of the month after her departure\. Starting the month after her departure, AWS applies Susan's credits to her bill instead of the organization's bill\.

In another example, assume that Susan owns a single account on January 1 and joins an organization on January 11\. If Susan redeems 100 dollars of credits on January 18, AWS applies them to her account for the usage that she incurred for the month of January\. From February 1st onwards, Susan's credits are applied to the organization's consolidated bill\. If Susan has 50 dollars of credits and leaves the organization on April 16, her credits are applied to the organization's consolidated bill for April\. From May onward, Susan's credits are applied to her account\.

## 4\. Sharing AWS credits<a name="credit-sharing"></a>

You can turn off credit sharing on the **Billing preferences** page on the Billing console\. The following rules specify how credits are applied to bills for single accounts and for organizations when credit sharing is turned off:
+ The billing cycle begins on the first day of each month\.
+ Credits are applied to only the account that received the credits\.
+ Bills are calculated using the credit sharing preference that is active on the last day of the month\.
+ In an organization, only the payer account can turn credit sharing off or on\. The credit sharing preference applies to all accounts in an organization\.<a name="turn-off-credit-sharing"></a>

**To turn off credit sharing**

You can turn off credit sharing through the Billing console\.

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Billing preferences**\.

1. Select **Disable credit sharing**\.

1. Choose **Save preferences**\.