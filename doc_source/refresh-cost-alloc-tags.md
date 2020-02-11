# Refreshing User\-Defined Cost Allocation Tags<a name="refresh-cost-alloc-tags"></a>

Cost allocation tags created by linked accounts can take up to 24 hours to appear in the Billing and Cost Management console\. After the tags appear, you can activate them to be included in your cost allocation report\. Every 24 hours, you can manually trigger a refresh of your cost allocation tags, shortening the wait time for your tags appear\. After a refresh, AWS applies your tags and sends you an email when the refresh is complete\. 

Before you can refresh your tags, you must create them and apply them to your resources\. For more information, see [Applying User\-Defined Cost Allocation Tags](custom-tags.md#allocation-how)\.<a name="trigger-tag-refresh"></a>

**To refresh your cost allocation tags**

You can refresh your cost allocation tags in the Billing and Cost Management console\.

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Cost Allocation Tags**\.

1. Under **Cost allocation tags**, choose **Refresh**\.

After AWS refreshes your tags, you can use the new tag in your AWS Cost and Usage report or cost allocation report\. AWS doesn’t apply tags to resources, spend, or usage that happened before AWS applied the tag\. For more information, see the [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.