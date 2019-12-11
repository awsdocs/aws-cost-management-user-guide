# Setting up Amazon Athena Manually<a name="athena-manual"></a>

If you don't use the provided AWS CloudFormation template, you must do the following steps manually:
+ [Create an Athena table](#create-cur-table)
+ [Create an AWS Cost and Usage report status table](#create-refresh-status)
+ [Upload report partitions](#upload-refresh-parts)

## Creating Your Athena Table<a name="create-cur-table"></a>

If you didn't use the AWS CloudFormation template to set up your Athena table, you must create a table before you can run SQL queries on your AWS Cost and Usage report data\.  You need to do this step at least once a month, and the table includes data from only the current AWS Cost and Usage report\. 

**Note**  
We strongly recommend that you use the AWS CloudFormation template to create your table instead of creating it yourself\. The provided SQL creates a table that covers only a single month of data, but the AWS CloudFormation template creates a table that can include multiple months and that updates automatically\.

As part of the table creation process, AWS transforms the AWS Cost and Usage report column names\. For more information about the transformation process, see [Column Names](run-athena-sql.md#column-transformations)\.<a name="create-athena-table-sql"></a>

**To create your Athena table**

AWS includes the SQL that you need to run to create this table in your AWS Cost and Usage report bucket\.

1. Sign in to the AWS Management Console and open the Amazon S3 console at [https://console\.aws\.amazon\.com/s3/](https://console.aws.amazon.com/s3/)\.

1. From the list of buckets, choose the bucket where you chose to receive your AWS Cost and Usage report\.

1.  From there, navigate the path `your-report-prefix-your-report-name-path-to-report`\.

   The exact path depends on whether your AWS Cost and Usage report is set to overwrite previous versions\. For more information, see [Viewing AWS Cost and Usage Report Files in Amazon S3](billing-reports-costusage-files.md)\.

1. Open the file `my-report-name-create-table.sql`\.

1. Copy the SQL from the file, starting with `CREATE` and ending with `LOCATION 's3://your-report-prefix/your-report-name/the-rest-of-the=path'`\. Take note of the first line, as you need the database name and table to create the Athena database\.

1. Open the Athena console at [https://console\.aws\.amazon\.com/athena/](https://console.aws.amazon.com/athena/home)\.

1. In the **New query 1** query pane, paste the following SQL\. For *`<database name>.<table name>`*, use the database and table name from the first line of the SQL that you copied\.

   ```
   CREATE DATABASE <database name>
   ```

1. Choose **Run query**\.

1. In the dropdown menu, choose the database that you just created\.

1. In the **New query 1** query pane, paste the rest of the SQL from the SQL file\.

1. Choose **Run query**\.

After you create your table, you must load your partitions before you can run a query\. For more information, see [Upload Your Report Partitions](#upload-refresh-parts)\.

## Create the AWS Cost and Usage Report Status Table<a name="create-refresh-status"></a>

AWS refreshes your AWS Cost and Usage report multiple times a day\. There is no way for Athena to know whether AWS is in the process of refreshing your AWS Cost and Usage report, which can lead to query results with a combination of old and new data\. To mitigate this, create a table to track whether AWS is refreshing your AWS Cost and Usage report and query that table to see if AWS is refreshing your data\. You need to create this table only once\. After that, AWS keeps the table up to date\.<a name="create-refresh-table"></a>

**To create your refresh table**

1. Open the Athena console at [https://console\.aws\.amazon\.com/athena/](https://console.aws.amazon.com/athena/home)\.

1. In the **New query 1** query pane, paste the following SQL\. 

   ```
   CREATE EXTERNAL TABLE IF NOT EXISTS cost_and_usage_data_status(
     status STRING)
   ROW FORMAT SERDE
     'org.apache.hadoop.hive.ql.io.parquet.serde.ParquetHiveSerDe'
   WITH SERDEPROPERTIES (
    'serialization.format' = '1'
   )
   LOCATION 's3://{S3_Bucket_Name}/{Report_Key}/cost_and_usage_data_status/'
   ```

1. Choose **Run query**\.

To check whether AWS is refreshing your data, use the Athena console to run the following SQL query\.

```
select status from cost_and_usage_data_status 
```

## Upload Your Report Partitions<a name="upload-refresh-parts"></a>

To query your AWS Cost and Usage report data, you must upload the data into your Athena table\. You must do this for each new AWS Cost and Usage report that AWS delivers to you\.<a name="upload-partitions"></a>

**To upload your latest partitions**

1. Open the Athena console at [https://console\.aws\.amazon\.com/athena/](https://console.aws.amazon.com/athena/home)\.

1. Choose the **\.\.\.** next to your table and choose **Load Partitions**\.

 If you don't upload your partitions, Athena returns either no results or an error message that indicates missing data from new partitions\. 