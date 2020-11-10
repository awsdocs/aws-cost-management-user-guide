# Using Cost Allocation Tags<a name="cost-alloc-tags"></a>

A tag is a label that you or AWS assigns to an AWS resource\. Each tag consists of a *key* and a *value*\. For each resource, each tag key must be unique, and each tag key can have only one value\. You can use tags to organize your resources, and cost allocation tags to track your AWS costs on a detailed level\. After you activate cost allocation tags, AWS uses the cost allocation tags to organize your resource costs on your cost allocation report, to make it easier for you to categorize and track your AWS costs\. AWS provides two types of cost allocation tags, an *AWS generated tags* and *user\-defined tags*\. AWS, or AWS Marketplace ISV defines, creates, and applies the AWS generated tags for you, and you define, create, and apply user\-defined tags\. You must activate both types of tags separately before they can appear in Cost Explorer or on a cost allocation report\.

The following diagram illustrates the concept\. In the example, you've assigned and activated tags on two Amazon EC2 instances, one tag called Cost Center and another tag called Stack\. Each of the tags has an associated value\. You also activated the AWS generated tags, `createdBy` before creating these resources\. The `createdBy` tag tracks who created a resource\. The user\-defined tags use the `user` prefix, and the AWS generated tag uses the `aws:` prefix\.

![\[Example Keys\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/Tag_Example.png)

After you or AWS applies tags to your AWS resources \(such as Amazon EC2 instances or Amazon S3 buckets\) and you activate the tags in the Billing and Cost Management console, AWS generates a cost allocation report as a comma\-separated value \(CSV file\) with your usage and costs grouped by your active tags\. You can apply tags that represent business categories \(such as cost centers, application names, or owners\) to organize your costs across multiple services\.

The cost allocation report includes all of your AWS costs for each billing period\. The report includes both tagged and untagged resources, so that you can clearly organize the charges for resources\. For example, if you tag resources with an application name, you can track the total cost of a single application that runs on those resources\. The following screenshot shows a partial report with columns for each tag\.

![\[Partial Cost Allocation Report showing your tag names, which are also called keys, as columns\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/images/CostAllocationPartExampleReport.png)

At the end of the billing cycle, the total charges \(tagged and untagged\) on the billing report with cost allocation tags reconciles with the total charges on your [https://console.aws.amazon.com/billing/home#/bill](https://console.aws.amazon.com/billing/home#/bill) page total and other billing reports for the same period\. 

You can also use tags to filter views in Cost Explorer\. For more information about Cost Explorer, see [Analyzing your costs with Cost Explorer](ce-what-is.md)\. 

 For more information about activating the AWS generated tags, see [Activating the AWS\-Generated Cost Allocation Tags](activate-built-in-tags.md)\. For more information about applying and activating user\-defined tags, see [User\-Defined Cost Allocation Tags](custom-tags.md)\. All tags can take up to 24 hours to appear in the Billing and Cost Management console\.

**Note**  
As a best practice, do not include sensitive information in tags\.
Only management account in an organization and single accounts that are not members of an organization have access to the **Cost Allocation Tags** manager in the Billing console\.

**Topics**
+ [AWS\-Generated Cost Allocation Tags](aws-tags.md)
+ [User\-Defined Cost Allocation Tags](custom-tags.md)
+ [Monthly cost allocation report](configurecostallocreport.md)