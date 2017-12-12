# PutReportDefinition<a name="put-report-definition"></a>

Creates an AWS Cost and Usage report\.

## Request Parameters<a name="put-report-definition-request-parameters"></a>

The request requires the following data in JSON format\.

**ReportDefinition**  
The report definition object that you want to create\.  
Type: [ReportDefinition](report-definition.md) object  
Required: Yes

## Errors<a name="put-report-definition-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**ValidationException**  
The input fails to satisfy the constraints specified by an AWS service\.  
HTTP Status Code: 400

**DuplicateReportNameException**  
A report with the specified name already exists in the account\. Specify a different report name\.  
HTTP Status Code: 400

**ReportLimitReachedException**  
This account already have five report defined\. To define a new report, you must delete an existing report\.  
HTTP Status Code: 400

## Examples<a name="put-report-definition-examples"></a>

The following example request creates a report named `Example Report`\.

### Sample Request<a name="put-report-definition-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsorigamiservicegateway#PutReportDefinition",
    "Service": "com.amazonaws.awsorigamiservicegateway#AWSOrigamiServiceGatewayService",
    "Input": {
        "ReportDefinition": {
            "ReportName": "Example Report",
            "TimeUnit": "DAILY",
            "Format": "textORcsv",
            "Compression": "ZIP",
            "AdditionalSchemaElements": [ 
                "RESOURCES"
            ],
            "S3Bucket": "example-s3-bucket",
            "S3Prefix": "example prefix",
            "S3Region": "us-east-1",
            "AdditionalArtifacts": [ 
                "REDSHIFT",
                "QUICKSIGHT"
            ]
        }
    }
}
```