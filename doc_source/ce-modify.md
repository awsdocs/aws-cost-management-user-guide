# Modifying your chart<a name="ce-modify"></a>

You can modify the parameters that Cost Explorer uses to create your chart, enabling you to explore different sets of data\.
+ [Selecting a style for your chart](#ce-style)
+ [Choosing time ranges for the data that you want to view](#ce-timerange)
+ [Grouping data by filter type](#ce-group)
+ [Filtering the data that you want to view](ce-filtering.md)
+ [Choosing advanced options](ce-advanced.md)

## Selecting a style for your chart<a name="ce-style"></a>

Cost Explorer provides three styles for charting your cost data: 
+ Bar charts \(**Bar**\)
+ Stacked bar charts \(**Stack**\)
+ Line graphs \(**Line**\)

You can set the style by using the view dropdown list\.

## Choosing time ranges for the data that you want to view<a name="ce-timerange"></a>

You can choose to view your cost data in monthly or daily *levels of granularity*\. You can use preconfigured time ranges or set custom start and end dates\. 

**To set the granularity and time range for your data**

1. Start Cost Explorer\.

1. Choose a time granularity of **Daily**, **Monthly**, or **Hourly**\.
**Note**  
To enable hourly granularity, opt in through the Cost Explorer settings page as the management account\. When hourly granularity is enabled, information is available for the previous 14 days\.

1. For your monthly or daily data, open the calendar and define a custom time range for your report, or choose a preconfigured time range \(**Auto\-select**\) at the bottom of the calendar\. You can choose from a number of historical or forecast time ranges\. The name of the time range that you choose appears in the calendar\.

1. Choose **Apply**\.

### Historical time range options<a name="timerangeref"></a>

In Cost Explorer, months are defined as calendar months\. Days are defined as 12:00:00 AM to 11:59:59 PM\. Based on these definitions, when you choose **Last 3 Months** for a date range, you see cost data for the 3 previous months, not including the present month\. For example, if you view your chart on June 6, 2017, and select **Last 3 Months**, your chart includes data for March, April, and May 2017\. All times are in Universal Coordinated Time \(UTC\)\. 

You can choose time ranges for both your past costs and your forecasted future costs\.

The following list defines each time range option for your past costs in Cost Explorer\. 
+ Custom

  Displays data for the **From** and **To** time range that you specify with calendar controls\.
+ 1D \(Last 1 Day\)

  Displays cost data from the current day\.
+ 7D \(Last 7 Days\)

  Displays cost data from the current day and the previous 6 days\. 
+ Current Month

  Displays cost data and forecast data for the current month\.
+ 3M \(Last 3 Months\)

  Includes cost data from the previous 3 months but does not include the current month\.
+ 6M \(Last 6 Months\)

  Includes cost data from the previous 6 months but does not include the current month\.
+ 1Y \(Last 12 Months\)

  Includes cost data from the previous 12 months but does not include the current month\.
+ MTD \(Month to Date\)

  Displays cost data from the current calendar month\. 
+ YTD \(Year to Date\)

  Displays cost data from the current calendar year\.

### Forecast time range options<a name="timerangereforecast"></a>

With the **Daily** or **Monthly** time granularity, you have the option to view forecast costs in Cost Explorer\. The following list defines each time range option for your forecast data\. You can select a **Historical** time range and a **Forecasted** time range to display together\. For example, you can select a **Historical** time range of 3 months \(3M\) and select a **Forecasted** time range of 3 months \(\+3M\)\. Your report includes historical data for the previous 3 months plus forecasted data for the next 3 months\. To clear a **Historical** time range and see only the forecast, choose the **Historical** time range option again\. 

**Note**  
If you choose any forecasted dates, your current date’s cost and usage data shows as **Forecast**\. The current date’s cost and usage won't include historical data\. 
+ Custom

  Displays forecast data for the **From** and **To** time range that you specify with calendar controls\.
+ \+1M

  Displays forecast data for the next month\. This option is available if you choose the **Daily** time granularity\.
+ \+3M

  Displays forecast data for the next 3 months\. This option is available if you choose the **Daily** or **Monthly** time granularity\.
+ \+12M

  Displays forecast data for the next 12 months\. This option is available if you choose the **Monthly** time granularity\.

## Grouping data by filter type<a name="ce-group"></a>

Use the **Group by** button to have Cost Explorer display the cost data groups by filter type\. By default, Cost Explorer doesn't use grouping\. Forecasting isn't available for charts that have grouping\. If you don't select a **Group by** option, Cost Explorer displays total costs for the specified date range\. 

**To group your data by filter type**

1. Launch Cost Explorer\.

1. \(Optional\) Use the **Filters** controls to configure a view of your cost data\.

1. Choose a **Group by** option to group by the category that you want\. The data table below the chart also groups your cost figures by the category that you select\.