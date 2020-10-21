# Volume discounts<a name="useconsolidatedbilling-discounts"></a>

For billing purposes, AWS treats all of the accounts in the organization as if they were one account\. Some services, such as AWS Data Transfer and Amazon S3, have volume pricing tiers across certain usage dimensions that give you lower prices the more you use the service\. With consolidated billing, AWS combines the usage from all accounts to determine which volume pricing tiers to apply, giving you a lower overall price whenever possible\. AWS then allocates each member account a portion of the overall volume discount based on the account's usage\.

The **Bills** page for each member account displays an average tiered rate that is calculated across all the accounts on the consolidated bill for the organization\. For example, let's say that Bob's consolidated bill includes both Bob's own account and Susan's account\. Bob's account is the management account, so he pays the charges for both himself and Susan\.

As shown in the following illustration, Bob transfers 8 TB of data during the month and Susan transfers 4 TB\.

For the purposes of this example, AWS charges $0\.17 per GB for the first 10 TB of data transferred and $0\.13 for the next 40 TB\. This translates into $174\.08 per TB \(= \.17\*1024\) for the first 10 TB, and $133\.12 per TB \(= \.13\*1024\) for the next 40 TB\. Remember that 1 TB = 1024 GB\.

For the 12 TB that Bob and Susan used, Bob's management account is charged \($174\.08 \* 10 TB\) \+ \($133\.12 \* 2 TB\) = $1740\.80 \+ $266\.24 = $2,007\.04\.

![\[Volume discounts\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/VolumeDiscount.png)

Without the benefit of tiering across the consolidated bill, AWS would have charged Bob and Susan each $174\.08 per TB for their usage, for a total of $2,088\.96\.

To learn more about pricing, see [AWS Pricing](http://aws.amazon.com/pricing/)\.

## AWS Free Tier for AWS Organizations<a name="cb-free"></a>

For services such as Amazon EC2 that support a free tier, AWS applies the free tier to the total usage across all accounts in an AWS organization\. AWS doesn't apply the free tier to each account individually\.

AWS provides budgets that track whether you exceed the free tier limits or are forecasted to go over the free tier limits\. Free tier budgets are not enabled for organizations by default\. Management account can opt in to free tier usage alerts through the Billing and Cost Management console\. Free tier usage alerts aren't available to individual member accounts\.

For more information about free tiers, see [AWS Free Usage Tier FAQs](https://aws.amazon.com/free/faqs/)\. For more information about AWS Free Tier usage alerts through AWS Budgets and opting in, see [AWS Free Tier usage alerts using AWS Budgets](tracking-free-tier-usage.md#free-budget)\.