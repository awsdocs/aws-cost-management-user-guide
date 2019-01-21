# Forecasting with Cost Explorer<a name="ce-forecast"></a>

You create a forecast by selecting a future time range for your report\. For more information, see [Choosing Time Ranges for the Data That You Want to View](ce-modify.md#ce-timerange)\. The following discussion talks about the accuracy of the forecasts created by Cost Explorer and how to read them\. 

A forecast is a prediction of how much you will use AWS services over the forecast time period you selected, based on your past usage\. Forecasting provides an estimate of what your AWS bill will be and enables you to use alarms and budgets for amounts that you're predicted to use\. Because forecasts are predictions, the forecasted billing amounts are estimated and might differ from your actual charges for each statement period\. 

Like weather forecasts, billing forecasts can vary in accuracy\. Different ranges of accuracy have different confidence intervals\. The higher the confidence interval, the more likely the forecast is to be correct\. For example, suppose you have a budget set to 100 dollars, and you've used 75 dollars in the past three weeks\. Cost Explorer forecasts that there is an 80% probability that your billed costs will be in the 90–100 dollar range\. 

Cost Explorer forecasts have a confidence interval of 80%\. If AWS doesn't have enough data to forecast within an 80% confidence interval, Cost Explorer doesn't show a forecast\. 

## Reading Forecasts<a name="reading-forecasts"></a>

How you read the Cost Explorer forecasts depends on the type of chart that you're using\. Forecasts are available for both line and bar charts\.

When you use line charts, there is a set of lines on either side of your costs line\. The lines indicate the 80% confidence interval\. The wider the range included in the forecast, the higher the probability that your bill will fall in the forecasted range\.

When you are using bar charts there are two lines on either side of the top of your bar\. The lines indicate the 80% confidence interval\. The wider the range included in the forecast, the higher the probability that your bill will fall in the forecasted range\.

## Using Forecasts with Consolidated Billing<a name="budget-consolidated"></a>

If you use the consolidated billing feature in AWS Organizations, the forecasts are calculated with the data from all the accounts\. If you add a new member account to an organization, forecasts will be less accurate until the new spending patterns of the organization are analyzed\. For more information about consolidated billing, see [Consolidated Billing for Organizations](consolidated-billing.md)\.