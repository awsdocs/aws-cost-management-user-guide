# Volume Discounts<a name="useconsolidatedbilling-discounts"></a>

For billing purposes, AWS treats all the accounts in the organization as if they were one account\. Some services, such as Amazon EC2 and Amazon S3, have volume pricing tiers across certain usage dimensions that give you lower prices the more you use the service\. With consolidated billing, AWS combines the usage from all accounts to determine which volume pricing tiers to apply, giving you a lower overall price whenever possible\. AWS then allocates each member account a portion of the overall volume discount based on the account's usage\.

The **Bills** page for each member account displays an average tiered rate that is calculated across all the accounts on the consolidated bill for the organization\. For example, let's say that Bob's consolidated bill includes both Bob's own account and Susan's account\. Bob's account is the master account, so he pays the charges for both himself and Susan\.

As shown in the following illustration, Bob transfers 8 TB of data during the month and Susan transfers 4 TB\.

For the purposes of this example, AWS charges $0\.17 per GB for the first 10 TB of data transferred and $0\.13 for the next 40 TB\. This translates into $174\.08 per TB \(= \.17\*1024\) for the first 10 TB, and $133\.12 per TB \(= \.13\*1024\) for the next 40 TB\. Remember that 1 TB = 1024 GB\.

For the 12 TB that Bob and Susan used, Bob's master account is charged \($174\.08 \* 10 TB\) \+ \($133\.12 \* 2 TB\) = $1740\.80 \+ $266\.24 = $2,007\.04\.

![\[Volume discounts\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/VolumeDiscount.png)

The average cost\-per\-unit of data transfer out for the month is therefore $2,007\.04 / 12 TB = $167\.25 per TB\. That is the average tiered rate shown on the **Bills** page and in the downloadable cost report for each member account on the consolidated bill\.

Without the benefit of tiering across the consolidated bill, AWS would have charged Bob and Susan each $174\.08 per TB for their usage, for a total of $2,088\.96\.

## AWS Free Tier for Organizations<a name="cb-free"></a>

For services such as Amazon EC2 that support a free tier, AWS applies the free tier to the total usage across all accounts in an organization\. AWS does not apply the free tier to each account individually\.

AWS provides budgets that track whether you exceed the free tier limits or are forecast to go over the free tier limits\. Free tier budgets are not enabled for organizations by default\. Master accounts can opt\-in to free tier usage alerts through the Billing and Cost Management console\. Free tier usage alerts aren't available to individual member accounts\.

For more information about free tiers, see [AWS Free Usage Tier FAQs](https://aws.amazon.com/free/faqs/)\. For more information about AWS Free Tier usage alerts via AWS Budgets and opting in, see [AWS Free Tier Usage Alerts Using AWS Budgets](tracking-free-tier-usage.md#free-budget)\.