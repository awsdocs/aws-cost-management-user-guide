# CreateSubscriber<a name="create-subscriber"></a>

Creates a subscriber\. You must create the associated budget and notification before you create the subscriber\.

## Request Parameters<a name="create-subscriber-request-parameters"></a>

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
The notification that you want to create a subscriber for\.  
Type: [Notification](data-type-notification.md) object  
Required: Yes

**subscriber**  
The subscriber that you want to associate with a budget notification\.  
Type: [Subscriber](data-type-subscriber.md) object  
Required: Yes

## Errors<a name="create-subscriber-errors"></a>

**CreationLimitExceededException**  
You've exceeded the notification or subscriber limit\.  
HTTP Status Code: 400

**DuplicateRecordException**  
The budget name already exists\. Budget names must be unique within an account\.  
HTTP Status Code: 400

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

## Examples<a name="create-subscriber-examples"></a>

The following example request creates a subscriber to the notification associated with the budget named `Example Budget`\.

### Sample Request<a name="create-subscriber-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#CreateSubscriber",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "accountId": "1234567890",
        "budgetName": "Example Budget",
        "notification": {
            "notificationType": "ACTUAL",
            "comparisonOperator": "LESS_THAN",
            "threshold": 30
        },
        "subscriber":  {
                "subscriptionType": "EMAIL",
                "address": "example@example.com"
        }
    }
}
```