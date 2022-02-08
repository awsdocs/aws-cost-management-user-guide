# Using the AWS Billing console dashboard<a name="view-billing-dashboard"></a>

You can use the dashboard page of the AWS Billing console to gain a general view of your AWS spending\. You can also use it to identify your highest cost service or Region and view trends in your spending over the past few months\. You can use the dashboard page to see various breakdowns of your AWS usage\. This is especially useful if you're a Free Tier user\. To view more details about your AWS costs and invoices, choose **Billing details** in the left navigation pane\. You can customize your dashboard layout at any time by choosing the gear icon at the top of the page to match your use case\.

Viewing your AWS costs in the AWS Billing console dashboard doesn't require turning on Cost Explorer\. To turn on Cost Explorer to access additional views of your cost and usage data, see [Enabling Cost Explorer](ce-enable.md)\.

**To open the AWS Billing console and dashboard**
+ Sign in to the AWS Management Console and open the AWS Billing console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

By default, the console shows the **AWS Billing Dashboard** page\.

## Understanding your dashboard page<a name="understanding-billing-dash"></a>

Your AWS Billing console dashboard contains the following sections\. To create your preferred layout, drag and drop sections of the** Dashboard** page\. To customize the visible sections and layout, choose the gear icon at the top of the page\. These preferences are stored for ongoing visits to the **Dashboard** page\. To temporarily remove sections from your view, choose the `x` icon for each section\. To make all sections visible, choose refresh at the top of the page\.

**AWS summary**  
This section is an overview of your AWS costs across all accounts, AWS Regions, service providers, and services, and other KPIs\. **Total compared to prior period** displays your total AWS costs for the most recent closed month\. It also provides a comparison to your total forecasted costs for the current month\. Choose the gear icon on the card to decide which KPIs you want to display\.

**Highest cost and usage details**  
This section shows your top service, account, or Region by estimated month\-to\-date \(MTD\) spend\. To choose which to view, choose the gear icon on the top right\.

**Cost trend by top five services**  
In this section, you can see the cost trend for your top five services for the most recent three to six closed billing periods\.  
You can choose between chart types and time periods on the top of the section\. You can adjust additional preferences using the gear icon\.  
The columns provide the following information:  
+ **Average**: The average cost over the trailing three months\.
+ **Total**: The total for the most recent closed month\.
+ **Trend**: Compares the **Total** column with the **Average** column\.

**Account cost trend**  
This section shows the cost trend for your account for the most recent three to six closed billing periods\. If you're a management account of AWS Organizations, the **cost trend by top five section** shows your top five AWS accounts for the most recent three to six closed billing periods\. If invoices weren't already issued, the data isn't visible in this section\.  
You can choose between chart types and time periods on the top of the section\. Adjust additional preferences using the gear icon\.  
The columns provide the following information:  
+ **Average**: The average cost over the trailing three months\.
+ **Total**: The total for the most recent closed month\.
+ **Trend**: Compares the **Total** column with the **Average** column\.

## Understanding your dashboard \(old console\)<a name="collapsible-oldconsole-dash"></a>

On the dashboard, you can view the following graphs:
+ **Spend Summary**
+ **Month\-to\-Date Spend by Service**
+ **Month\-to\-Date Top Services by Spend**

**Spend Summary**  
The **Spend Summary** graph shows you how much you spent last month, the estimated costs of your AWS usage for the month\-to\-date, and a forecast for how much you are likely to spend this month\. The forecast is an estimate that's based on your past AWS costs\. Therefore, your actual monthly costs might not match the forecast\.

**Month\-to\-Date Spend by Service**  
The **Month\-to\-Date Spend by Service** graph shows the top services that you use most and the proportion of your costs that service contributed to\. The **Month\-to\-Date Spend by Service** graph doesn't include forecasting\.

**Month\-to\-Date Top Services by Spend**  
The **Month\-to\-Date Top Services by Spend** graph shows the services that you use most, along with the costs incurred for the month to date\. The **Month\-to\-Date Top Services by Spend** graph doesn't include forecasting\.

**Note**  
The Billing and Cost Management console has a refresh time of approximately 24 hours to reflect your billing data\.