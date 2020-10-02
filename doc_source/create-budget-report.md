# Creating an AWS Budgets report<a name="create-budget-report"></a>

Use the following procedure to create an AWS Budgets report\.<a name="creating-budget-report-steps"></a>

**To create an AWS Budgets report**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Budget Reports**\.

1. On the top right of the page, choose **Create Budget report**\.

1. For **Report name**, enter the name of the report\. This name will be the subject line of your budget report email\.

   You can change your report name at any time\.

1. Select the number of budgets to include in your report\.

   You can filter by **Budget name** at the top of the table to simplify your selection\. Selecting **Budget name** sends you to the budget details page\. The table also shows **Budget type**, **Filters**, **Budgeted amount**, and **Budget progress**\.
**Note**  
You can select up to 50 budgets\. If you select more, you can't proceed to the next step until you've changed your selection to 50 or less\.

1. Choose **Configure delivery settings**\.

1. Choose a **Report frequency**\.
   + **Daily**
   + **Weekly**: Specify the day of the week\.
   + **Monthly**: Specify the day of the month\. If you select the twenty\-ninth through the thirty\-first and the next month doesn't have that day, your report is delivered on the final day of the month\.
**Note**  
Reports are delivered at approximately 0:00 UTC on the specified day\.

1. Enter **Email recipient\(s\)**\.

   Add multiple email addresses separated by commas\. You can have up to 50 email recipients for each budget report\.

1. Select **Confirm budget Report**\.

1. Choose **Create**\.

Your report appears on the AWS Budgets Reports dashboard\. You can filter your reports by **Report name** at the top of the table\. The dashboard also shows **Frequency**, number of **Budget\(s\) monitored**, and the **Recipients** of each report\.