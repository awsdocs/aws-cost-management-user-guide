# Choosing Advanced Options<a name="advanced"></a>

You can customize how you view your data in Cost Explorer using **Advanced Options** to include or exclude specific types of data\. The following types of data are included by default:

**Refunds**  
Any refunds that you received\. Refunds are listed as a separate line item in the data table\. They do not appear as an item in the chart because they represent a negative value in the calculation of your costs\. The chart displays only positive values\.

**Credits**  
Any AWS credits that are applied to your account\.

**Upfront reservation fees**  
Any upfront fees that are charged to your account\. When you purchase an All Upfront or Partial Upfront Reserved Instance from AWS, you pay an upfront fee in exchange for a lower rate for using the instance\. The upfront fees can result in spikes in the chart for the days or months when you make your purchases\.

**Recurring reservation charges**  
Any recurring charges to your account\. When you purchase a Partial Upfront or No Upfront Reserved Instance from AWS, you pay a recurring charge in exchange for a lower rate for using the instance\. The recurring charges can result in spikes on the first day of every month, when AWS charges your account\.

**Taxes**  
Any taxes that are associated with the charges or fees in your cost chart\. Cost Explorer adds all taxes together as a single component of your costs\. If you select five or fewer filters, Cost Explorer displays your tax expenses as a single bar\. If you select six or more filters, Cost Explorer displays five bars, stacks, or lines, and then aggregates all remaining items, including taxes, into a sixth bar, stack slice, or plot line that is labeled **Other**\.   
If you choose to omit **RI upfront fees**, **RI recurring charges**, or **Support charges** from your chart, Cost Explorer continues to include any taxes that are associated with the charges\.  
Cost Explorer displays your tax costs in the chart only when you choose the **Month** tab\. When you filter your cost chart, the following rules govern the inclusion of taxes:   

1. Taxes are excluded if you select non\-**Linked Account** filters, either singly or in combination with other filters\. 

1. Taxes are included if you select the **Linked Accounts** filters\. 

**Support charges**  
Any charges that AWS charges you for a support plan\. When you purchase a support plan from AWS, you pay a monthly charge in exchange for service support\. The monthly charges can result in spikes on the first day of every month, when AWS charges your account\.

**Other subscription costs**  
Other applicable subscription costs that are not covered by the other data categories\. These costs can include data such as AWS training fees, AWS competency fees, out\-of\-cycle charges such as registering a domain with Amazon Route 53, and more\.

You can exclude these data types from your chart using the following procedure:

**To exclude data from your chart**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the **Cost Explorer** page, choose **Launch Cost Explorer**\.
**Note**  
Cost Explorer is available in any AWS account for no cost\.

1. In the right pane, under **Advanced Options**, under **Include costs related to**, deselect the data type that you want to exclude\. 

In addition to the costs that Cost Explorer includes, you can show specific costs such as untagged resources or blended costs\. This allows you to see the following alternate views of your costs:

**Show only untagged resources**  
By default, Cost Explorer includes costs both for resources that have cost allocation tags and for resources that don't have cost allocation tags\. To find untagged resources that add to your costs, select **Show only untagged resources**\. For more information about cost allocation tags, see [Using Cost Allocation Tags](cost-alloc-tags.md)\.

**Show blended costs**  
If you use the consolidated billing feature in AWS Organizations, you can view costs using *blended rates*\. For more information, see Blended Rates\.

You can show these specific costs by using the following procedure\.

**To show specific cost types in your chart**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Cost Explorer**\.

1. On the **Cost Explorer** page, choose **Launch Cost Explorer**\.
**Note**  
Cost Explorer is available in any AWS account for no cost\.

1. In the right pane, under **Advanced Options**, under **Other**, select the cost type that you want to show\. 