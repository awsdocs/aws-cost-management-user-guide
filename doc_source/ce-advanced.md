# Choosing advanced options<a name="ce-advanced"></a>

You can customize how you view your data in Cost Explorer using **Advanced Options** to include or exclude specific types of data\. 

**To exclude data from your chart**

Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.
+ In the right pane, under **Advanced Options**, under **Include costs related to**, deselect the data type that you want to exclude\. 

In addition to the costs that Cost Explorer includes, you can show specific costs such as untagged resources or blended costs\. This enables you to see the following alternate views of your costs\.

**Show only untagged resources**  
By default, Cost Explorer includes costs both for resources that have cost allocation tags and for resources that don't have cost allocation tags\. To find untagged resources that add to your costs, select **Show only untagged resources**\. For more information about cost allocation tags, see [Using Cost Allocation Tags](cost-alloc-tags.md)\.

**Show blended costs**  
This cost metric reflects the average cost of usage across the consolidated billing family\. If you use the consolidated billing feature in AWS Organizations, you can view costs using *blended rates*\. For more information, see [Blended Rates](con-bill-blended-rates.md#Blended_CB)\.

**Show unblended costs**  
This cost metric reflects the cost of the usage\. When grouped by charge type****, *unblended costs* separate discounts into their own line items\. This enables you to view the amount of each discount received\.

**Show net unblended costs**  
This cost metric reflects the cost after discounts\.

**Show amortized costs**  
This cost metric reflects the effective cost of the upfront and monthly reservation fees spread across the billing period\. By default, Cost Explorer shows the fees for Reserved Instances as a spike on the day that you're charged, but if you choose to show costs as amortized costs, the costs are amortized over the billing period\. This means that the costs are broken out into the effective daily rate\. AWS estimates your amortized costs by combining your unblended costs with the amortized portion of your upfront and recurring reservation fees\. For the daily view, Cost Explorer shows the unused portion of your upfront reservation fees and recurring RI charges on the first of the month\.   
For example, suppose that Alejandro purchases a Partial Upfront `t2.micro` RI for a one\-year term at $30 dollars upfront, with a monthly fee of $2\.48\. Cost Explorer shows the costs for this RI as a spike on the first of the month\. If Alejandro chooses **Amortized costs** for a 30\-day month, the Cost Explorer chart shows a daily effective rate of $0\.165, which is the EC2 effective rate multiplied by the number of hours in a day\.  
Amortized costs aren't available for billing periods before 2018\. If you want to see how much of your reservation was unused, group by purchase option\.

**Show net amortized costs**  
This cost metric amortizes the upfront and monthly reservation fees while including discounts such as RI volume discounts\.

You can show these specific costs by using the following procedure\.

**To show specific cost types in your chart**

Open the AWS Cost Management at [https://console\.aws\.amazon\.com/cost\-management/home](https://console.aws.amazon.com/cost-management/home)\.
+ In the right pane, under **Advanced Options**, under **Other**, select the cost type that you want to show\. 