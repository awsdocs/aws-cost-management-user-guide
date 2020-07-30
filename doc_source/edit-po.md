# Editing your purchase orders<a name="edit-po"></a>


|  | 
| --- |
| Purchase order is in public preview for AWS Billing and Cost Management and is subject to change\. Your use of purchase orders is subject to the Preview Service Participation terms of the [AWS Service Terms](https://aws.amazon.com/service-terms/) \(Section 1\.10\)\. | 

You can edit your purchase order, line item information, and status using the Billing and Cost Management console\. You can't change your purchase order ID in this process\.<a name="edit-po-steps"></a>

**To edit a purchase order**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Purchase orders**\.

1. Select the purchase order that you want to edit\.

1. Choose **Edit purchase order**\.

1. Change any parameter of your choice\. Purchase order IDs cannot be changed\.

1. Choose **Configure line items**\.

1. Choose **Submit purchase order**\.<a name="add-li-steps"></a>

**To add a line item**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Purchase orders**\.

1. Choose the purchase order you want to edit\.

1. In the **Line items** section, choose **Add line item**\.

1. Change the information as needed\.

1. Choose **Save line item**\.<a name="edit-li-steps"></a>

**To edit a line item**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Purchase orders**\.

1. Choose the purchase order you want to edit\.

1. In the **Line items** section, choose **Edit**\.

1. Change the line item information as needed\.

1. Choose **Save line item**\.<a name="delete-li-steps"></a>

**To delete a line item**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Purchase orders**\.

1. Choose the purchase order you want to edit\.

1. Select all of the line items to delete in the **Line items** section\.

1. Choose **Delete**\.

1. Choose **Confirm**\.<a name="change-status-steps"></a>

**To change the status of your purchase order**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Purchase orders**\.

1. Choose the purchase order you want to edit\.

1. Choose **Change status**\.

1. Choose a status:
   + **Suspended** –Your purchase order will no longer be used for invoice association\.
   + **Active** – Your purchase order will be used for invoice association\.

1. Choose **Change status**\.

**Note**  
To use a suspended purchase order for invoice association when it is past its expiration date and set to **Suspended\-Expired** status, you must change the status to **Expired** and update the expiration month to make it **Active**\. Be sure to update your line item end months accordingly\.