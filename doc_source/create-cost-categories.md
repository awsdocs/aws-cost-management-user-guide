# Creating cost categories<a name="create-cost-categories"></a>

You can create cost categories to organize your cost and usage information\. Regular accounts and the management account in AWS Organizations have default access to create cost categories\. Rules aren't mutually exclusive, and you can control the order that the rules apply in\. Allow up to 24 hours after creating a cost category for your usage records to be updated with values\.

There are five major steps in creating cost categories\.

1. Define a name for your cost category \(for example, `business units`, `Teams`\)\.

1. \(Optional\) Add a tag to your cost category\. For more information about tags, see [Tagging AWS resources](https://docs.aws.amazon.com/general/latest/gr/aws_tagging.html) in the *AWS General Reference guide*\.

1. \(Optional\) Set the lookback period for your cost category rules\. The default will be set to the current month\.

1. Write the rules to categorize your costs into cost category values \(for example, `Team-A`, `Team-B`, `Team-C`\)\.

1. \(Optional\) Define rules to split charges between your cost category values\.

   For more information about split charges, see [Splitting charges within cost categories](splitcharge-cost-categories.md)\.

Use the following procedure to create a new cost category\.<a name="create-cost-categories-steps"></a>

**To create a cost category**

1. Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **AWS Cost Categories**\.

1. At the top of the page, choose **Create Cost category**\.

1. Under **Cost category details**, enter the name of your cost category\. Your cost category name must be unique within your account\.

1. \(Optional\) To add a tag, choose **Add new resource tag** and enter a key and value\.

1. \(Optional\) To add a lookback period for your cost category rules, choose the **Apply cost category rules starting any specified month from the previous 12 months** radio button, and select the month where you want to retroactively apply the rules\.

1. Choose **Next**\.

1. Choose **Define category values**\.

   Use either the **Rule Builder** or **JSON editor** to define your cost categories\. 

   For more information about the JSON request syntax, see the [AWS Billing and Cost Management API Reference](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/)\.

1. For **Value**, enter the name of the cost category value\.

1. Choose a **Rule Type**, either **Regular** or **Inherited value**\.

1. Choose a billing **Dimension** from the dropdown list\. For a regular rule type, you can choose **Accounts**, **Service**, **Charge Type** \(for example, recurring reservation fee\), **Tag key**, or **Cost Category**\. \(You can choose **Cost Category** to create hierarchical relationships among your cost categories\.\) For an inherited value rule type, you can choose **Account** or **Tag key** \(Cost Allocation tag key\)\.

1. For a regular rule type, choose **Operator** from the dropdown list\. Your options are **Is**, **Contains**, **Starts with**, and **Ends with**\.
**Note**  
**Contains**, **Starts with**, and **Ends with** are only supported with Accounts and Tag dimensions\. If you use these operators with Accounts, the engine evaluates against account name, and not account ID\.

   Choose a filtered value for your **Dimension** in the attribute selector\.

1. Choose a dimension operator for your rule from the dropdown\. You can choose between `AND` and `OR`\. `AND` is the default operator\. Changing the operator impacts all dimensions in this rule\.

1. For an inherited value rule type, choose **Account** or **Tag** for **Dimension**\. If **Tag** is the **Dimension**, choose the **Tag key** to inherit the cost category value from\.
**Note**  
The **Account** dimension uses account names, not account IDs for the inherited cost category value\.

1. \(Optional\) Add a default value\. It categorizes all unmatched costs to this value\.

1. \(Optional\) To rearrange the rule order, use the arrows or change the number on the top right of each rule\.

1. \(Optional\) To delete a rule, choose **Remove** on the top right of each rule\.

1. \(Optional\) Under **Define split charges**, choose **Next**\.

   For more information about split charge rules, see [Splitting charges within cost categories](splitcharge-cost-categories.md)\.

   1. Choose **Add a split charge**\.

   1. Under **Source value**, choose your cost category value\.

      **Uncategorized** cost isn't an option at this time, but is an available source if you edit your cost category\. For more information, see [Editing cost categories](edit-cost-categories.md)\.

   1. Under **Target values**, choose one or more cost category values you wish to allocate split charges to\.

   1. Under **Charge allocation method**, choose how you want to allocate your costs\. Your choices are **proportional**, **fixed**, and **even split**\.

      For **fixed** charge allocation, enter the percentage amount to allocate each target cost category value\.

   1. Choose **Create split charge**\.

   1. Choose **Add a split charge** and repeat steps to define more split charges\.

1. Choose **Create cost category**\.