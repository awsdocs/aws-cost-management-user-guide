# Using the AWS Free Tier<a name="billing-free-tier"></a>

When you create an AWS account, you can try some AWS services free of charge within certain usage limits\. There are three types of offers in the AWS Free Tier programs to choose from:

**Always free**  
These free tier offers do not expire and are available to all AWS customers\.

**12 months free**  
You can use these offers for 12\-months following your initial sign\-up date to AWS\.

**Short\-term trials**  
You can use a free tier limit each month for less than 12 months\. Most short\-term free trial offers start from the date you activate a particular service\.

For the list of services that offer AWS Free Tier benefits, types, and usage limits, see [AWS Free Tier](http://aws.amazon.com/free/)\.

For more information on how to avoid charges while you’re eligible for the AWS Free Tier, see the following resources:
+ [Tracking your AWS Free Tier usage](tracking-free-tier-usage.md)
+ [Avoiding unexpected charges after the AWS Free Tier](#avoid-charges-after-free-tier)

## Eligibility for the AWS Free Tier<a name="free-tier-eligibility"></a>

Your AWS usage stays within the AWS Free Tier limits when all of these conditions are met:
+ You’re within the active trial period for the AWS Free Tier offering\. For example, within 12 months for a 12\-month free type of service like Amazon EC2\.
+ You use only AWS services that offer AWS Free Tier benefits\.
+ Your usage stays within the AWS Free Tier limits of those services\.

If you use AWS services beyond one or more of these conditions, then that usage exceeds the Free Tier limits\. You're charged at the standard AWS billing rates for usage that exceeds the Free Tier limits\.

To learn more about the AWS Free Tier limits, see [AWS Free Tier](http://aws.amazon.com/free/)\.

**Note**  
For AWS Organizations, the AWS Free Tier eligibility for all member accounts begins on the day that the management account is created\. For more information, see the [AWS Organizations User Guide](https://docs.aws.amazon.com/organizations/latest/userguide/)\.

## Avoiding unexpected charges after the AWS Free Tier<a name="avoid-charges-after-free-tier"></a>

Your eligibility for the 12 month free service offering AWS Free Tier expires 12 months after you first create your account\. You can’t extend your Free Tier eligibility after this time\.

**Note**  
You can continue to use Always Free offers, even after your Free Tier eligibility expires\. To learn more about available Always Free offers, see [AWS Free Tier](http://aws.amazon.com/free/)\.

As the expiration date of your AWS Free Tier eligibility approaches, we recommend that you terminate any resources you no longer need\. After your eligibility expires, you’re charged at the standard AWS billing rates for usage\.

Even if you aren’t regularly logging in to your account, you might have active resources running\. Use the following procedure to identify your account’s active resources\.

For short\-term trials, there are no expiration notification for these services\. You'll receive free tier alerts during the trial period only\. To avoid unexpected costs in a short\-term trial, you must turn off these resources before the end of the trial period\.<a name="identify-active-resources-billing"></a>

**To identify your account’s active resources using AWS Billing**

1. Sign in to the AWS Management Console and open the Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. Choose the **Bills** page from the navigation pane\.

1. Next to **Details**, choose **Expand All**\.

1. Review the list under **AWS Service Charges**\. This list shows you the services with active resources by AWS Region\.<a name="identify-active-resources"></a>

**To identify your account’s active resources using AWS Cost Explorer**

1. Sign in to the AWS Management Console and open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.

1. Choose **AWS Cost Explorer** from the navigation pane\.

Note the services and AWS Regions with resources that you no longer need\. For instructions on how to terminate those resources, see the documentation for that service\.

You might decide to close your AWS account\. To avoid generating future charges, we recommend that you retrieve the content you want to keep and terminate any remaining resources before you close your account\. Closing your account might not automatically terminate all your active resources and you might continue to incur charges\. Make sure to review your content and resources across different AWS Regions\. For more information and important considerations, see [Closing an account](close-account.md)\.