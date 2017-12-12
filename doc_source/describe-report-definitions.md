# DescribeReportDefinitions<a name="describe-report-definitions"></a>

Describes your AWS Cost and Usage reports\.

## Request Parameters<a name="describe-report-definitions-request-parameters"></a>

The request requires the following data in JSON format\.

**MaxResults**  
Optional integer\. Specifies the maximum number of results to return in response\.   
Type: Integer  
Valid value: 5  
Required: No

## Response Elements<a name="describe-report-definitions-responses"></a>

This operation returns the following parameters\.

**ReportDefinition**  
Returns one or more `ReportDefinition` objects\.  
Type: [ReportDefinition](report-definition.md) object

## Errors<a name="describe-report-definitions-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

## Examples<a name="describe-report-definitions-examples"></a>

The following example requests the AWS Cost and Usage reports for the account\.

### Sample Request<a name="describe-report-definitions-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsorigamiservicegateway#DescribeReportDefinitions",
    "Service": "com.amazonaws.awsorigamiservicegateway#AWSOrigamiServiceGatewayService",
    "Input": {
        "MaxResults": 5
    }
}
```

### Sample Response<a name="describe-report-definitions-examples-sample-response"></a>

The following example requests the AWS Cost and Usage reports for the account\.

```
{
        "ReportDefinitions": [
        {
            "AdditionalArtifacts": ["QUICKSIGHT"],
            "AdditionalSchemaElements": ["RESOURCES"],
            "Compression": "GZIP",
            "Format": "textORcsv",
            "ReportName": "Example Report",
            "S3Bucket": "example-s3-bucket",
            "S3Prefix": "example prefix",
            "S3Region": "us-east-1",
            "TimeUnit": "HOURLY"
        },
        {
            "AdditionalArtifacts": ["QUICKSIGHT"],
            "AdditionalSchemaElements": ["RESOURCES"],
            "Compression": "GZIP",
            "Format": "textORcsv",
            "ReportName": "Example Report 2",
            "S3Bucket": "example-s3-bucket",
            "S3Prefix": "example prefix",
            "S3Region": "us-east-1",
            "TimeUnit": "HOURLY"
        }]
}
```