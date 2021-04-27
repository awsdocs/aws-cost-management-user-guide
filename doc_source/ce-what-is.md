# Analyzing your costs with Cost Explorer<a name="ce-what-is"></a>

Cost Explorer is a tool that enables you to view and analyze your costs and usage\. You can explore your usage and costs using the main graph, the Cost Explorer cost and usage reports, or the Cost Explorer RI reports\. You can view data for up to the last 12 months, forecast how much you're likely to spend for the next 12 months, and get recommendations for what Reserved Instances to purchase\. You can use Cost Explorer to identify areas that need further inquiry and see trends that you can use to understand your costs\. 

You can view your costs and usage using the Cost Explorer user interface free of charge\. You can also access your data programmatically using the Cost Explorer API\. Each paginated API request incurs a charge of $0\.01\. You can't disable Cost Explorer after you enable it\.

In addition, Cost Explorer provides preconfigured views that display at\-a\-glance information about your cost trends and give you a head start on customizing views that suit your needs\. 

When you first sign up for Cost Explorer, AWS prepares the data about your costs for the current month and the last 12 months, and then calculates the forecast for the next 12 months\. The current month's data is available for viewing in about 24 hours\. The rest of your data takes a few days longer\. Cost Explorer refreshes your cost data at least once every 24 hours\. However, this depends on your upstream data from your billing applications, and some data might be updated later than 24 hours\. After you sign up, Cost Explorer can display up to 12 months of historical data \(if you have that much\), the current month, and the forecasted costs for the next 12 months\. The first time that you use Cost Explorer, Cost Explorer walks you through the main parts of the console with an explanation for each section\. You can trigger this walkthrough at a later time as well\. For more information, see [To trigger the Cost Explorer walkthrough](ce-getting-started.md#ce-walkthrough)\.

Cost Explorer uses the same dataset that is used to generate the AWS Cost and Usage Reports and the detailed billing reports\. For a comprehensive review of the data, you can download it into a comma\-separated value \(CSV\) file\.

**Topics**
+ [Enabling Cost Explorer](ce-enable.md)
+ [Getting started with Cost Explorer](ce-getting-started.md)
+ [Exploring your data using Cost Explorer](ce-exploring-data.md)
+ [Using Cost Explorer reports](ce-reports.md)
+ [Understanding your reservations with Cost Explorer](ce-ris.md)
+ [Optimizing your cost with Rightsizing Recommendations](ce-rightsizing.md)
+ [Using the AWS Cost Explorer API](ce-api.md)