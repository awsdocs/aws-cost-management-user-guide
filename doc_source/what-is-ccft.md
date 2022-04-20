# Understanding your customer carbon footprint tool<a name="what-is-ccft"></a>

You can use the customer carbon footprint tool to view estimates of the carbon emissions associated with your AWS products and services\.

**Topics**
+ [Getting started with customer carbon footprint tool](#ccft-gettingstarted)
+ [Understanding your customer carbon footprint tool overview](ccft-overview.md)
+ [Understanding your carbon emission estimations](ccft-estimation.md)

## Getting started with customer carbon footprint tool<a name="ccft-gettingstarted"></a>

The customer carbon footprint tool is available for all accounts\. If a report isn't available for your account, your account might be too new to show data\. After each month, you might have a delay of up to three months for AWS to show your carbon emission estimates\.

**To view your customer carbon footprint tool**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation bar, choose **Cost & Usage Reports**\.

1. Under **date range**, choose your **start month** and **end month**\.

### IAM policies<a name="ccft-gettingstarted-IAM"></a>

You must have the IAM permission `sustainability:GetCarbonFootprintSummary` to access the customer carbon footprint tool and data\. For more information regarding IAM permissions, see [AWS Identity and Access Management for AWS Billing](security-iam.md)\.

### AWS Organizations users<a name="ccft-gettingstarted-org"></a>

If you're logged in as a management account of AWS Organizations, the customer carbon footprint tool reports the member account data for the duration that those accounts were a part of your management account\. If you're a member account, the customer carbon footprint tool reports emission data for all the periods\. This is regardless of any changes that might have occurred to your account's associated membership in one of the AWS Organizations\.