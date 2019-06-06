# Running Athena Queries<a name="run-athena-sql"></a>

To run Athena queries on your data, first use the Athena console to check whether AWS is refreshing your data and then run your query on the Athena console\. When you run your SQL, make sure that the correct database is selected from the dropdown list\. You can use the following SQL to check the status\.

```
select status from cost_and_usage_data_status 
```

The two possible results are `READY` and `UPDATING`\. If the status is `READY`, then you can query your Athena database\. If the status is `UPDATING`, then Athena might return incomplete results\.

After you have confirmed that AWS isn't refreshing your data, you can run your own queries\. For example, the following query shows year\-to\-date costs by service for each month in the example database called `mycostandusage_parquet`\.

```
SELECT line_item_product_code,
sum(line_item_blended_cost) AS cost, month
FROM mycostandusage_parquet
WHERE year='2018'
GROUP BY  line_item_product_code, month
HAVING sum(line_item_blended_cost) > 0
ORDER BY  line_item_product_code;
```

## Column Names<a name="column-transformations"></a>

Athena column name restrictions are different from the AWS Cost and Usage report column name restrictions\. This means that when your AWS Cost and Usage report data is uploaded into an Athena table, the column names change\. AWS makes the following changes:
+ An underscore is added in front of uppercase letters
+ Uppercase letters are replaced with lowercase letters 
+ Any non\-alphanumeric characters are replaced with an underscore
+ Duplicate underscores are removed
+ Any leading and trailing underscores are removed
+ If the column name is longer than the allowed length of column names, underscores are removed from left to right

**Important**  
If AWS encounters resource tag columns that have the same name after AWS applies these rules, AWS keeps the value associated with the first tag that it encountered\. 

For example, the column name `ExampleColumnName : Example Column Name Continued` becomes `example_column_name_example_column_name_continued`\.