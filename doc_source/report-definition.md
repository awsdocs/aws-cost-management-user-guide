# ReportDefinition<a name="report-definition"></a>

Represents the output of the `PutReportDefinition` operation\. The content consists of the detailed metadata and data file information\.

## Contents<a name="data-type-report-contents"></a>

**ReportName**  
The `ReportName` of the report to be created\.  
Type: String  
Length constraints: Maximum length of `256`\.  
Required: Yes

**TimeUnit**  
The length of time covered by this report\.  
Type: String  
Valid values: HOURLY | DAILY   
Required: Yes

**Format**  
The format that the report is saved in\.  
Type: String  
Valid value: textORcsv   
Required: Yes

**Compression**  
The compression type that is applied to the report\.  
Type: String  
Valid values: ZIP | GZIP   
Required: Yes

**AdditionalSchemaElements**  
A list of strings that indicate additional content that is included in the report, such as individual resource IDs\.  
Type: List of Strings  
Valid value: RESOURCES   
Required: Yes

**S3Bucket**  
The S3 bucket where the report is delivered\.  
Type: String  
Required: Yes

**S3Prefix**  
The prefix that AWS adds to the report name when the report is delivered\.  
Type: String  
Required: Yes

**S3Region**  
The region of the S3 bucket\.  
Type: String  
Required: Yes

**AdditionalArtifacts**  
A list of manifests that you want to be created for this report\.  
Type: List of Strings  
Valid values: REDSHIFT | QUICKSIGHT   
Required: No