# DeleteReportDefinition<a name="delete-report-definition"></a>

Deletes an AWS Cost and Usage report\.

## Request Parameters<a name="delete-report-definition-request-parameters"></a>

The request requires the following data in JSON format\.

**ReportName**  
The `ReportName` of the report to be deleted\.  
Type: String  
Length constraints: Maximum length of `256`\.  
Required: Yes

## Errors<a name="delete-report-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**ValidationException**  
The input fails to satisfy the constraints specified by an AWS service\.  
HTTP Status Code: 400

## Examples<a name="delete-report-definition-examples"></a>

The following example request deletes the AWS Cost and Usage report named `Example Report`\.

### Sample Request<a name="delete-report-definition-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsorigamiservicegateway#DeleteReportDefinition",
    "Service": "com.amazonaws.awsorigamiservicegateway#AWSOrigamiServiceGatewayService",
    "Input": {
        "ReportName": "Example Report",
    }
}
```