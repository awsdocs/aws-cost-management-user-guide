# Forecasting with Cost Explorer<a name="ce-forecast"></a>

You create a forecast by selecting a future time range for your report\. For more information, see [Choosing time ranges for the data that you want to view](ce-modify.md#ce-timerange)\. The following section discusses the accuracy of the forecasts created by Cost Explorer and how to read them\. 

A forecast is a prediction of how much you will use AWS services over the forecast time period that you selected, based on your past usage\. Forecasting provides an estimate of what your AWS bill will be and enables you to use alarms and budgets for amounts that you're predicted to use\. Because forecasts are predictions, the forecasted billing amounts are estimated and might differ from your actual charges for each statement period\. 

Like weather forecasts, billing forecasts can vary in accuracy\. Different ranges of accuracy have different prediction intervals\. The higher the prediction interval, the more likely the forecast will have a wider range\. For example, suppose that you have a budget set to 100 dollars for a given month\. An 80% prediction interval might forecast your spend between 90 and 100, with a mean of 95\. The range in the prediction band is dependent on your historical spend volatility, or fluctuations\. The more consistent and predictable the historical spend, the narrower the prediction range in forecast spend\.

Cost Explorer forecasts have a prediction interval of 80%\. If AWS doesn't have enough data to forecast an 80% prediction interval, Cost Explorer doesn't provide a forecast\. This is common for accounts that have less than one full billing cycle\.

## Reading forecasts<a name="reading-forecasts"></a>

How you read the Cost Explorer forecasts depends on the type of chart that you're using\. Forecasts are available for both line charts and bar charts\.

The 80% prediction interval appears differently on each type of chart:
+ Line charts represent the prediction interval as a set of lines on either side of your costs line
+ Bar charts represent the prediction interval as two lines on either side of the top of your bar

If you receive discounts, we encourage you to use **Show net unblended costs** when forecasting your monthly costs to include discounts\. Unblended costs don't include discounts, but instead separates discounts into their own line item\. For more information about different costs, see [Cost Explorer Advanced Options](ce-advanced.md)\.

## Using forecasts with consolidated billing<a name="budget-consolidated"></a>

If you use the consolidated billing feature in AWS Organizations, the forecasts are calculated with the data from all the accounts\. If you add a new member account to an organization, forecasts will be less accurate until the new spending patterns of the organization are analyzed\. For more information about consolidated billing, see [Consolidated billing for AWS Organizations](consolidated-billing.md)\.