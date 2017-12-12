# DeleteSubscriber<a name="delete-subscriber"></a>

Deletes a subscriber\.

**Warning**  
Deleting the last subscriber to a notification also deletes the notification\.

## Request Parameters<a name="delete-subscriber-request-parameters"></a>

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
The notification whose subscriber you want to delete\.  
Type: [Notification](data-type-notification.md) object  
Required: Yes

**subscriber**  
The subscriber that you want to delete\.  
Type: [Subscriber](data-type-subscriber.md) object  
Required: Yes

## Errors<a name="delete-sub-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="delete-subscriber-examples"></a>

The following example request deletes a subscriber for the budget named `Example Budget`\.

### Sample Request<a name="delete-subscriber-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#DeleteSubscriber",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "notification": {
            "notificationType": "FORECASTED",
            "comparisonOperator": "LESS_THAN",
            "threshold": 80
        },
        "subscriber": {
            "subscriptionType": "EMAIL",
            "address": "example@example.com"
        },
        "accountId": "1234567890"
    }
}
```