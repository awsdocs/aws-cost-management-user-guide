# CreateNotification<a name="create-notification"></a>

Creates a notification\. You must create the budget before you create the associated notification\.

## Request Parameters<a name="create-notification-request-parameters"></a>

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

**notification**  
The notification that you want to create\.  
Type: [Notification](data-type-notification.md) object  
Required: Yes

**subscribers**  
A list of subscribers that you want to associate with the notification\. Each notification can have one SNS subscriber and up to ten email subscribers\.  
Type: A list of [Subscriber](data-type-subscriber.md) objects  
Required: Yes

## Errors<a name="create-notification-errors"></a>

**CreationLimitExceededException**  
You've exceeded the notification or subscriber limit\.  
HTTP Status Code: 400

**DuplicateRecordException**  
The budget name already exists\. Budget names must be unique within an account\.  
HTTP Status Code: 400

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="create-notification-examples"></a>

The following example request creates a notification for the budget named `Example Budget`\.

### Sample Request<a name="create-notification-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#CreateNotification",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "notification": {
            "notificationType": "ACTUAL",
            "comparisonOperator": "LESS_THAN",
            "threshold": 30
        },
        "subscribers": [ {
                "subscriptionType": "EMAIL",
                "address": "example@example.com"
            }, 
            {
                "subscriptionType": "EMAIL",
                "address": "example2@example.com"
            }, 
            {
                "subscriptionType": "SNS",
                "address": "exampleSnsTopic"
            }
        ],
        "accountId": "1234567890"
    }
}
```