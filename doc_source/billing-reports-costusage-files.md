# Viewing AWS Cost and Usage Report Files in Amazon S3<a name="billing-reports-costusage-files"></a>

The AWS Cost and Usage report is a \.csv file or a collection of \.csv files that is stored in an Amazon S3 bucket\. During the report period, AWS delivers a new report and a new manifest file each time the report is updated\. The new report includes all the information included in the previous report, as well as information new to the current report\. AWS builds on previous reports until the end of the billing period\. After the end of the billing period, AWS generates a new report with none of the information from the previous report\. The size of an individual report can grow to more than a gigabyte and might exceed the capacity of desktop spreadsheet applications to display every line\. If a report is larger than most applications can handle, AWS splits the report into multiple files that are stored in the same folder in the Amazon S3 bucket\. 

The AWS Cost and Usage report uses the following Amazon S3 organization and naming conventions:

```
<report-prefix>/<report-name>/yyyymmdd-yyyymmdd/<assemblyId>/<report-name>-<file-number>.csv.<zip|gz>
```
+ `report-prefix` = The prefix that you assign to the report\.
+ `report-name` = The name that you assign to the report\.
+ `yyyymmdd-yyyymmdd` = The range of dates that you specify for the report\. Reports are finalized at the end of the date range\.
+ `assemblyId` = An ID that AWS creates each time that the report is updated\.
+ `file-number` = If the update includes a large file, AWS might split it into multiple files\. The file\-number tracks the different files in an update\.
+ `csv` = The format of the report files\.
+ `zip` or `gz` = The type of compression applied to the report files\.

For example, your report could be delivered as a collection of the following files:

```
			<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-<1>.csv.<zip><example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-<2>.csv.<zip>
			<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-<3>.csv.<zip>
			<example-report-prefix>/<example-report-name>/20160101-20160131/<123456789>/<example-report-name>-Manifest.json
```

AWS delivers all reports in a report date range to the same `report-prefix/report-name/yyyymmdd-yyyymmdd` folder\. AWS gives each report a unique ID and delivers it to the `assemblyId` subfolder in the date range folder\. If the report is too large for a single file, the report is split into multiple files and delivered to the same `assemblyId` folder\.

When the AWS Cost and Usage report is updated, AWS creates and delivers a manifest file\. The manifest file lists all of the detail columns that are included in the report to date, a list of report files if the report was split into multiple files, the time period covered by the report, and other information\. Manifest files also are stored in the date range and `assemblyId` folders, using the following naming conventions:

```
<report-prefix>/<report-name>/YYYYMMDD-YYYYMMDD/<report-name>-Manifest.json
```

```
<report-prefix>/<report-name>/YYYYMMDD-YYYYMMDD/<assemblyId>/<report-name>-Manifest.json
```

Each time that AWS creates a new AWS Cost and Usage report for a date range, it overwrites the manifest file stored in the date range folder with an updated manifest file\. AWS delivers the same updated manifest file to the `assemblyId` folder along with the files for that update\. Manifest files in the `assemblyId` folder aren't overwritten\.

If you chose the option to include an Amazon Redshift manifest in your AWS Cost and Usage report, AWS also creates and delivers an Amazon Redshift manifest file and a file with the SQL commands that you need to upload your report into Amazon Redshift\. You can open the SQL file with a regular text editor\. The manifest and SQL files use the following naming conventions:

```
<report-prefix>/<report-name>/YYYYMMDD-YYYYMMDD/<assemblyId>/<report-name>-RedshiftManifest.json
```

```
<report-prefix>/<report-name>/YYYYMMDD-YYYYMMDD/<assemblyId>/<report-name>-RedshiftCommands.sql
```

If you use the commands in the `RedshiftCommands` file, you don't need to open the `RedshiftManifest` file\.

**Important**  
The `RedshiftManifest` file determines which report files the `copy` command in the `RedshiftCommands` file uploads\. Deleting or removing the `RedshiftManifest` file breaks the copy command in the `RedshiftCommands` file\.