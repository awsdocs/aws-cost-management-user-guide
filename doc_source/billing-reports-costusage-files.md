# Viewing AWS Cost and Usage Report Files in Amazon S3<a name="billing-reports-costusage-files"></a>

The AWS Cost and Usage report is a \.csv file or a collection of \.csv files that is stored in an Amazon S3 bucket\. During the report period, AWS delivers a new report and a new manifest file each time AWS updates the report\. The new report includes all of the information included in the previous report and information new to the current report\. AWS builds on previous reports until the end of the billing period\. After the end of the report billing period, AWS generates a new report with none of the information from the previous report\. The size of an individual report can grow to more than a gigabyte and might exceed the capacity of desktop spreadsheet applications to display every line\. If a report is larger than most applications can handle, AWS splits the report into multiple files that are stored in the same folder in the Amazon S3 bucket\. The specific organization and naming conventions of your AWS Cost and Usage report files depend on what parameters you chose when you created your AWS Cost and Usage report\.
+ [Keeping Previous AWS Cost and Usage Reports](#versioned)
+ [Overwriting Previous AWS Cost and Usage Reports](#overwrite)

## Keeping Previous AWS Cost and Usage Reports<a name="versioned"></a>

When you choose to keep your previous AWS Cost and Usage report, your AWS Cost and Usage report uses the following Amazon S3 organization and naming conventions\.

```
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<assemblyId>/<example-report-name>-<file-number>.csv.<zip|gz>
```
+ `report-prefix` = The prefix that you assign to the report\.
+ `report-name` = The name that you assign to the report\.
+ `yyyymmdd-yyyymmdd` = The range of dates that the report covers\. Reports are finalized at the end of the date range\.
+ `assemblyId` = An ID that AWS creates each time that the report is updated\.
+ `file-number` = If the update includes a large file, AWS might split it into multiple files\. The `file-number` tracks the different files in an update\.
+ `csv` = The format of the report files\.
+ `zip` or `gz` = The type of compression applied to the report files\.

For example, your report could be delivered as a collection of the following files\.

```
<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-<1>.csv.<zip>
<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-<2>.csv.<zip>
<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-<3>.csv.<zip>
<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-Manifest.json
<example-report-prefix>/<example-report-name>/20160101-20160131/<example-report-name>-Manifest.json
```

AWS delivers all reports in a report date range to the same `report-prefix/report-name/yyyymmdd-yyyymmdd` folder\. AWS gives each report a unique ID and delivers it to the `assemblyId` subfolder in the date range folder\. If the report is too large for a single file, the report is split into multiple files and delivered to the same `assemblyId` folder\.

## Overwriting Previous AWS Cost and Usage Reports<a name="overwrite"></a>

When you choose to overwrite your previous AWS Cost and Usage report, your AWS Cost and Usage report uses the following Amazon S3 organization and naming conventions\.

```
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-<file-number>.csv.<zip|gz>
```
+ `report-prefix` = The prefix that you assign to the report\.
+ `report-name` = The name that you assign to the report\.
+ `yyyymmdd-yyyymmdd` = The range of dates that the report covers\. AWS finalizes reports at the end of the date range\.
+ `file-number` = If the update includes a large file, AWS might split it into multiple files\. The `file-number` tracks the different files in an update\.
+ `csv` = The format of the report files\.
+ `zip` or `gz` = The type of compression applied to the report files\.

For example, your report could be delivered as a collection of the following files\.

```
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-<1>.csv.<zip>
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-<2>.csv.<zip><example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-<3>.csv.<zip>
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-Manifest.json
```

If you chose Athena support when you created your AWS Cost and Usage report, the file naming conventions are the same as when you choose to overwrite your AWS Cost and Usage report except for the format and compression\. Athena AWS Cost and Usage report files use `.parquet` instead\. For example, your report could be delivered as a collection of the following files\.

```
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>.parquet
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<cost_and_usage_data_status>
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-Manifest.json
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-create-table.sql
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/crawler-cfn.yml
```

In addition to the AWS Cost and Usage report files, AWS also delivers an AWS CloudFormation template that you can use to set up an AWS CloudFormation stack that enables you to query Amazon S3 data using Athena\. If you don't want to use the AWS CloudFormation template, you can use the provided SQL to create your own Athena tables\. For more information, see [Uploading an AWS Cost and Usage Report to Amazon Athena](athena.md)\.

AWS delivers all reports in a report date range to the same folder\. If the report is too large for a single file, the report is split into multiple files and delivered to the same folder\.

## AWS Cost and Usage Report Manifest Files<a name="manifests"></a>

When AWS updates the AWS Cost and Usage report, AWS also creates and delivers manifest files that you can use for Amazon Redshift, Amazon QuickSight, or Amazon Athena\. When you keep the previous AWS Cost and Usage reports, the manifest file is delivered to both the date range folder and the `assemblyId` folder\. When you overwrite the previous AWS Cost and Usage report, the manifest file is delivered to the `month=mm` folder along with the report files\. The manifest files list all of the detail columns that are included in the report to date, a list of report files if the report was split into multiple files, the time period covered by the report, and other information\. Manifest files use the naming conventions\.

```
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-Manifest.json
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<assemblyId>/<example-report-name>-Manifest.json
<example-report-prefix>/<example-report-name>/<example-report-name>/year=2018/month=12/<example-report-name>-Manifest.json
```

When you keep the previous AWS Cost and Usage reports, each time that AWS creates a new AWS Cost and Usage report for a date range, it overwrites the manifest file stored in the date range folder with an updated manifest file\. AWS delivers the same updated manifest file to the `assemblyId` folder along with the files for that update\. Manifest files in the `assemblyId` folder aren't overwritten\. When you overwrite the previous AWS Cost and Usage report, the manifest file is overwritten along with the report files\.

If you chose the option for Amazon Redshift support in your AWS Cost and Usage report, AWS also creates and delivers a file with the SQL commands that you need to upload your report into Amazon Redshift\. You can open the SQL file with a regular text editor\. The SQL file uses the following naming convention\.

```
<example-report-prefix>/<example-report-name>/yyyymmdd-yyyymmdd/<assemblyId>/<example-report-name>-RedshiftCommands.sql
```

If you use the commands in the `RedshiftCommands` file, you don't need to open the `RedshiftManifest` file\.

**Important**  
The `manifest` file determines which report files the `copy` command in the `RedshiftCommands` file uploads\. Deleting or removing the `manifest` file breaks the copy command in the `RedshiftCommands` file\.

If you chose the option for Amazon Athena support in your AWS Cost and Usage report, AWS also creates and delivers multiple files to help set up all of the resources that you need\. AWS delivers a AWS CloudFormation template, a SQL file with the SQL to create your Athena table manually, and a file with the SQL to check your AWS Cost and Usage report refresh status\. These files use the following naming conventions\.

```
<example-report-prefix>/<example-report-name>/<example-report-name>/yyyymmdd-yyyymmdd/crawler-cfn.yml
<example-report-prefix>/<example-report-name>/<example-report-name>/yyyymmdd-yyyymmdd/<example-report-name>-create-table.sql
<example-report-prefix>/<example-report-name>/<example-report-name>/yyyymmdd-yyyymmdd/<cost_and_usage_data_status>
```