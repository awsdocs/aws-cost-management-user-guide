# Modifying your chart<a name="ce-modify"></a>

You can modify the parameters that Cost Explorer uses to create your chart, enabling you to explore different sets of data\.
+ [Selecting a style for your chart](#ce-style)
+ [Choosing time ranges for the data that you want to view](#ce-timerange)
+ [Grouping data by filter type](#ce-group)
+ [Filtering the data that you want to view](ce-filtering.md)
+ [Choosing advanced options](ce-advanced.md)

## Selecting a style for your chart<a name="ce-style"></a>

Cost Explorer provides two styles for charting your cost data: bar charts \(**Bar**\) or line graphs \(**Line**\)\. You can set the style by using the view dropdown\. 

## Choosing time ranges for the data that you want to view<a name="ce-timerange"></a>

You can choose to view your cost data in monthly or daily *levels of granularity*\. You can use preconfigured time ranges or set custom start and end dates\. 

**To set the granularity and time range for your data**

1. Start Cost Explorer\.

1. Choose a time granularity of **Daily**, **Monthly**, or **Hourly**\.
**Note**  
To enable hourly granularity, opt\-in through the Cost Explorer settings page as the management account\. Once enabled, information for the previous 14 days are available\.

1. For your monthly or daily data, open the calendar and define a custom period for your report or choose a preconfigured period at the bottom of the calendar\. You can choose from a number of historical or forecast time periods\. The name of the period that you choose appears in the calendar\.

1. Choose **Apply**\.

### Historical time range options<a name="timerangeref"></a>

In Cost Explorer, months are defined as calendar months\. Days are defined as 12:00:00 AM to 11:59:59 PM\. Based on these definitions, when you choose **Last 3 Months** for a date range, you see cost data for three previous months, not including the present month\. For example, if you view your chart on June 6, 2017, and select **Last 3 Months**, your chart includes data for March, April, and May 2017\. All times are in Universal Coordinated Time \(UTC\)\. 

You can choose time ranges for both your past costs and your forecasted future costs\.

The following list defines each time range option for your past costs in Cost Explorer\. 
+ Custom

  Displays data for the time range for the **From** and **To** dates that you specify with calendar controls\.
+ 7D \(Last 7 Days\)

  Displays cost data from the current day and the previous six days\. 
+ 14D \(Last 14 Days\)

  Displays cost data from the current day and the previous 13 days\.
+ MTD \(Month\-to\-Date\)

  Displays cost data for the current calendar month\. 
+ 1M \(Last Month\)

  Displays cost data from the last month\.
+ 3M \(Last 3 Months\)

  Includes cost data from the previous three months but does not include the current month\.
+ 6M \(Last 6 Months\)

  Includes cost data from the previous six months but does not include the current month\.
+ YTD \(Year\-to\-Date\)

  Displays cost data from the current calendar year\.
+ 1Y \(Last Year\)

  Displays cost data from the last calendar year\.

### Forecast time range options<a name="timerangereforecast"></a>

The following list defines each time range option for your forecast costs in Cost Explorer\. You can select a **Historical** time period and a **Forecasted** period to display together\. For example, you can select a **Historical** period of one month \(1M\) and select a **Forecasted** period of three months \(3M\)\. Your report includes historical data for the previous month plus forecasted data for the next 3 months\. To clear a **Historical** time period and see only the forecast, choose the **Historical** period again\. 

**Note**  
If you choose any Forecasted dates, your current date’s cost and usage data shows as Forecast\. The current date’s cost and usage will not include historical data\. 
+ Custom

  Displays forecast data for the time range in the **From** and **To** dates that you specify with calendar controls\.
+ EOM \(End of Month\)

  Displays data for the historical time period that you choose plus a forecast to the end of the current month\.
+ \+1M

  Displays forecast data for the current day plus the next month\.
+ \+3M

  Displays forecast data for the current day and the next 3 months\.

## Grouping data by filter type<a name="ce-group"></a>

Use the **Group by** button to have Cost Explorer display the cost data groups by filter type\. By default, Cost Explorer doesn't use grouping\. Forecasting isn't available for charts that have grouping\. If you don't select a **Group by** option, Cost Explorer displays total costs for the specified date range\. 

**To group your data by filter type**

1. Launch Cost Explorer\.

1. \(Optional\) Use the **Filter** controls to configure a view of your cost data\.

1. Choose **Group By** to group by the option that you want\. The data table below the chart also groups your cost figures by the option you selected\.