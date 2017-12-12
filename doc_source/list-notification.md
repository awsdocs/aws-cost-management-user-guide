# DescribeNotificationsForBudget<a name="list-notification"></a>

Lists the notifications associated with a budget\.

## Request Parameters<a name="list-notification-request-parameters"></a>

The request requires the following data in JSON format\.

**accountId**  
The `accountId` that is associated with the budget\.  
Type: String  
Length constraints: Minimum length of `12`, maximum length of `12`\.  
Required: Yes

**budgetName**  
The name of the budget\. Budget names must be unique within an account\.  
Type: String  
Length constraints: 100 characters  
Pattern: \[^:\]\+  
Required: Yes

**maxResults**  
Optional integer\. Specifies the maximum number of results to return in response\. This parameter value must be greater than 0\.  
Type: Integer  
Required: No

**nextToken**  
The pagination token that indicates the next set of results to retrieve\.  
Type: String  
Required: No

## Response Elements<a name="list-notification-responses"></a>

This operation returns the following parameters\.

**notifications**  
A list of notifications associated with a budget\.  
Type: List of [Notification](data-type-notification.md) objects

**nextToken**  
The pagination token that indicates the next set of results to retrieve\.  
Type: String

## Errors<a name="list-noti-errors"></a>

**ExpiredNextTokenException**  
The pagination token expired\.  
HTTP Status Code: 400

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidNextTokenException**  
The pagination token is invalid\.  
HTTP Status Code: 400

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="list-notification-examples"></a>

The following example request lists notifications associated with the budget named `Example Budget`\.

### Sample Request<a name="list-notification-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#DescribeNotificationsForBudget",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "accountId": "1234567890"
        "pageSize": 50,
        "nextToken": "eyJhbGciOiJIUzI1NiJ9.SldUQ2xhaW1zU2V0IFtpc3M9bnVsbCwgc3ViExampleV0aGluZ3NvbWV0aGluZywgYXVkPW51bGwsIGV4cD1TdW4gQXVnIDE0IDE2OjAxOjA1ExampleAyMDE2LCBuYmY9bnVsbCwgaWF0PW51bGwsIGp0aT1udWxsLCB0eXA9bnVsbCwgY3VzdG9tQ2xhaW1zPXthY2NvdW50SWQ9YWNjb3VudExampleUcnlpbmcgbmV3IHRoaW5ncz15ZXAgeWVwLCBtZD17Im5vdGlmaWNhdGlvbnMiOm51bGwsInRpbWVQZXJpb2QiOnsiZW5kIjoxNDQ4ODQxNjAwMDAwLCJzdGFydCI6MTQzODM4MzYwMDAwMH0sImNvc3RGaWx0ZXJzIjpbXSwidGltZVVuaXQiOiJNb250aGx5IiwiY29zdCI6eyJiYXNlQ3VycmVuY3lDb2RlIjoiVVNEIiwiYW1vdW50Ijo1fSwiYWNjb3VudElkIjoiMjE5MDM4OTkyNTQ5IiwiY29zdFR5cGVzIjp7ImluY2x1ZGVTdWJzY3JpcHRpb24iOnRydWUsInVzZUJsZW5kZWQiOmZhbHNlLCJpbmNsdWRlVGF4Ijp0cnVlfSwiYnVkZ2V0SWQiOiI1OTRmNjFhOC05OTI5LTRjNTItYjA1MC1lODVmNjhjMWYyYTciLCJidWRnZXROYW1lIjoiTW9udGhseSBUb3RhbCBidWRnZXQifSwgYnVkZ2V0SWQ9YnExampleIElEfV0.PoThTg2PppANoA0oIiYsLJqoU-7yF4_sMINKjj7SohQ"
    }
}
```