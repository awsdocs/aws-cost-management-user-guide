# Creating cost categories<a name="create-cost-categories"></a>

You can create cost categories to organize your cost and usage information\. Regular accounts and the management account in AWS Organizations have default access to create cost categories\. Rules are not mutually exclusive, and you can control the order in which the rules apply\. Allow up to 24 hours after creating a cost category for your usage records to be updated with values\.

Use the following procedure to create a new cost category\.<a name="create-cost-categories-steps"></a>

**To create a cost category**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **AWS Cost Categories**\.

1. At the top of the page, choose **Create Cost category**\.

1. Under **Cost category details**, enter the name of your cost category\. Your cost category name must be unique within your account\.

1. Choose **Next**\.

1. Choose **Define category values**\.

   Use either the **Rule Builder** or **JSON editor** to define your cost categories\. 

   For more information about the JSON request syntax, see the [AWS Billing and Cost Management API Reference](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/)\.

1. For **Value**, enter the name of the cost category value\.

1. Choose a billing **Dimension** from the dropdown list\. You can choose **Accounts**, **Service**, **Charge Type** \(for example, recurring reservation fee\), or **Tag key** \(Cost Allocation tag key\)\.

1. Choose **Operator** from the dropdown list\. Your options are **Is**, **Contains**, **Starts with**, and **Ends with**\.
**Note**  
**Contains**, **Starts with**, and **Ends with** are only supported with Accounts and Tag dimensions\. If you use these operators with Accounts, the engine evaluates against account name, and not account ID\.

1. Choose a filtered value for your **Dimension** in the attribute selector\.

1. \(Optional\) To rearrange the rule order, use the arrows or change the number on the top right of each rule\.

1. \(Optional\) To delete a rule, select **Remove** on the top right of each rule\.