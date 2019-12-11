# Creating Cost Categories<a name="create-cost-categories"></a>


|  | 
| --- |
| Cost Category is in preview release for AWS Billing and Cost Management and is subject to change\. Your use of Cost Categories is subject to the Beta Service Participation terms of the [AWS Service Terms](https://aws.amazon.com/service-terms/) \(Section 1\.10\)\. | 

You can create Cost Categories to organize your cost and usage information\. Regular accounts and Payer accounts in AWS Organizations have default access to create Cost Categories\. Rules are not mutually exclusive, and you can control the order that the rules apply\. Please allow up to 24 hours after creating a Cost Category for your usage records to be updated with values\.

Use the following procedure to create a new Cost Category\.<a name="create-cost-categories-steps"></a>

**To create a Cost Category**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/home\#/](https://console.aws.amazon.com/billing/home)\.

1. In the navigation pane, choose **Cost Categories**\.

1. At the top of the page, choose **Create Cost Category**\.

1. Under **Cost Category Name**, enter the name of your Cost Category\. Your Cost Category name must be unique within your account\.

1. Choose **Define category values**\.

1. For **Value**, enter the name of the Cost Category value\.

1. Select a billing **Dimension** from the dropdown list\. You can select either **Accounts** or **Tag key** \(Cost Allocation tag key\)\.

1. Filter values for Accounts or Tags in the attribute selector\.

1. \(Optional\) To rearrange the rule order, use the arrows or change the number on the top right of each rule\.

1. \(Optional\) To delete a rule, select **Remove** on the top right of each rule\.