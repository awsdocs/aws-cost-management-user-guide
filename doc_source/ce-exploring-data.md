# Exploring your data using Cost Explorer<a name="ce-exploring-data"></a>

On the Cost Explorer dashboard, Cost Explorer shows your estimated costs for the month to date, your forecasted costs for the month, a graph of your daily costs, your five top cost trends, and a list of reports that you recently viewed\. 

All costs reflect your usage up to the previous day\. For example, if today is December 2, the data includes your usage through December 1\.

**Note**  
In the current billing period, the data depends on your upstream data from your billing applications, and some data might be updated later than 24 hours\.
+ [Your Cost Explorer costs](#ce-costs)
+ [Your Cost Explorer trends](#ce-trends)
+ [Your daily unblended costs](#ce-graph)
+ [Your monthly unblended costs](#ce-monthly-unblended)
+ [Your net unblended costs](#net-unblended)
+ [Your recent Cost Explorer reports](#ce-recent-reports)
+ [Your amortized costs](#amortized-costs)

## Navigating Cost Explorer<a name="ce-nav-pane"></a>

You can use the icons in the left pane to do the following:
+ Go to the main Cost Explorer dashboard
+ See a list of the default Cost Explorer reports
+ See a list of your saved reports
+ See information about your reservations
+ See your reservation recommendations

## Your Cost Explorer costs<a name="ce-costs"></a>

At the top of the **Cost Explorer** page are the **Month\-to\-date costs** and **Forecasted month end costs**\. The **Month\-to\-date costs** shows how much you're estimated to have incurred in charges so far this month and compares it to this time last month\. The **Forecasted month end costs** shows how much Cost Explorer estimates that you will owe at the end of the month and compares your estimates costs to your actual costs of the previous month\. The **Month\-to\-date costs** and the **Forecasted month end costs** don't include refunds\.

## Your Cost Explorer trends<a name="ce-trends"></a>

In the ***this month* trends** section, Cost Explorer shows your top cost trends\. For example, your costs related to a specific service have gone up, or your costs from a specific type of RI have gone up\. To see all of your costs trends, choose **View all trends** in the upper\-right corner of the trend section\.

To understand a trend in more depth, choose it\. You're taken to a Cost Explorer chart that shows the costs that went into calculating that trend\.

## Your daily unblended costs<a name="ce-graph"></a>

In the center of the Cost Explorer dashboard, Cost Explorer shows a graph of your current unblended daily costs\. You can access the filters and parameters used to create the graph by choosing **Explore costs** in the upper\-right corner\. That takes you to the Cost Explorer report page, enabling you to access the default Cost Explorer reports and modify the parameters used to create the chart\. The Cost Explorer reports offer additional functionality such as downloading your data as a CSV file and saving your specific parameters as a report\. For more information, see [Using Cost Explorer reports](ce-reports.md)\. Your daily unblended costs don't include refunds\.

## Your monthly unblended costs<a name="ce-monthly-unblended"></a>

### Monthly granularity<a name="monthly-granularity"></a>

You can view your unblended costs at the monthly granularity and see the discounts applied to your monthly bill\. You can see this by opening the Cost Explorer page and choosing **Cost Explorer** from the navigation pane\. Discounts appear as the **RI Volume Discount** in the chart\. The discount amount aligns with the discount amount shown in your Billing and Cost Management console\.<a name="see-details-in-BCM"></a>

**To see the details in your Billing and Cost Management console**

1. Sign in to the AWS Management Console and open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/)\.

1. In the navigation pane, choose **Bills**\.

1. To display the discount, select the arrow next to **Total Discounts**, under **Credits, Total Discounts and Tax Invoices**\.

#### Monthly gross charges<a name="monthly-gross-charges"></a>

You can view your gross monthly charges by excluding the **RI Volume Discount**\. <a name="exclude"></a>

**To exclude RI volume discounts in your monthly view**

1. Open the Billing and Cost Management console at [https://console\.aws\.amazon\.com/billing/](https://console.aws.amazon.com/billing/home?#/)\.

1. In the navigation pane, choose **Cost Explorer**\.

1. Select **Launch Cost Explorer**\.

1. In the left pane, choose **Cost Explorer**\.

1. Choose **Cost & Usage**\.

1. On the **Filters** pane, choose **Charge Type**\.

1. Select **RI Volume Discount**\.

1. To open a dropdown, select **Include only** and choose **Exclude only**\.

1. Select **Apply filters**\.

## Your net unblended costs<a name="net-unblended"></a>

This enables you to see your net costs after all applicable discounts are calculated\. You should still exclude any manual adjustment such as refunds and credits as a best practice\. **RI Volume Discounts** are no longer visible because these are post\-discount amounts\.

## Your recent Cost Explorer reports<a name="ce-recent-reports"></a>

At the bottom of the Cost Explorer dashboard is a list of reports that you have accessed recently, when you accessed them, and a link back to the report\. This enables you to switch between reports or remember the reports that you find most useful\.

For more information about Cost Explorer reports, see [Using Cost Explorer reports](ce-reports.md)\.

## Your amortized costs<a name="amortized-costs"></a>

This enables you to see the cost of the RI purchases spread across the usage of the reservation\. AWS estimates your amortized costs by combining the unblended upfront and recurring reservation fees and calculating the effective rate of applicable instances\. In the daily view, Cost Explorer shows the unused portion of your reservation fees at the first of the month or the date of purchase\.