# Viewing your budgets<a name="budgets-view"></a>

The **Budgets** dashboard shows you the state of your budgets at a glance\. Your budgets are listed on the dashboard along with the following data:
+ Your current costs and usage incurred for a budget during the budget period
+ Your budgeted costs or usage for the budget period
+ Your forecasted usage or costs for the budget period
+ A percentage that shows your costs or usage compared to your budgeted amount
+ A percentage that shows your forecasted costs or usage compared to your budgeted amount

**To view your budgets**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation pane, choose **Budgets**\.

1. To see the filters and cost variances for your budgets, choose the budget's name in your list of budgets\. 

## Reading your budgets<a name="reading-budgets"></a>

After you choose your budget name, you see your budget details page\. This page includes the following information:
+ **Current vs budgeted** – Your current incurred costs compared to your budgeted costs\.
+ **Forecasted vs budgeted** – Your forecasted costs compared to your budgeted costs\.
+ **Alerts** – Any alerts or notifications about the state of your budgets\.
+ **Budget History** – A table showing the history of your budgets\. `QUARTERLY` budgets show the last four quarters of history, and `MONTHLY` budgets show the last 12 months\. Budget history isn't available for `ANNUAL` budgets\.

  If you change the budgeted amount for a budget period, the budgeted amount in the table is the last budgeted amount\. For example, if you have a monthly budget set for 100 in January and change the budget to 200 in February, the February line in the table shows only the 200\.
+ **Budget details** – The period, type, and filters that you used when you created this budget\.
+ **Budgeted amount** – The budgeted amount for the current and future planned periods for Monthly or Quarterly Planning budgets\.

You can use this information to see how well your budget has matched your costs and usage in the past\. You can also download all of the data that Budgets used to create the table using the following procedure\.<a name="download-budget-csv"></a>

**To download a budget CSV**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. On the navigation pane, choose **Budgets**\.

1. To see the filters and cost variances for your budgets, choose the budget's name in your list of budgets\. 

1. In **Budget History**, choose **Download as CSV**\.

1. Follow the instructions onscreen\.