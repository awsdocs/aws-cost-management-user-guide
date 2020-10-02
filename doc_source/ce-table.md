# Reading the Cost Explorer data table<a name="ce-table"></a>

Below each Cost Explorer chart is a data table, which displays the cost figures that the chart represents\. If your chart is using a grouping, the table displays the aggregate amounts for the filter types that you choose for your chart\. If your chart isn't using a grouping, the table displays the aggregate amounts for your past and forecasted cost data\. You can [download](ce-download-csv.md) the \.csv file that contains the complete data set for your chart\.

**Note**  
For the RI Utilization and Savings report, the maximum table size is 20 rows\. If the data exceeds the maximum table size, it appears in a truncated form\. 

In the grouped data table, each row is a value for one of the filter type options: API operations, Availability Zones, AWS services, custom cost allocation tags, instance types, member accounts, purchase options, Region, usage type, or usage type group\. The columns represent time intervals\. For example, the data table shows the account's costs for selected services for the last three months, with an aggregated total for the three months in the last column\. 

**Note**  
Data transfer costs are included in the services that they're associated with, such as Amazon EC2 or Amazon S3\. They aren't represented as either a separate line item in the data table or a bar in the chart\. 

In the ungrouped data table, the row is your costs\. The columns represent time intervals\.