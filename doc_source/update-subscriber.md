# UpdateSubscriber<a name="update-subscriber"></a>

Updates a subscriber\.

## Request Parameters<a name="update-subscriber-request-parameters"></a>

Updates the `subscriber` associated with the budget notification\. You can use the `ListSubscribersForNotification` operation to view the contents of the updated subscriber\.

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
The notification whose subscriber you want to update\.  
Type: [Notification](data-type-notification.md) object  
Required: Yes

**oldSubscriber**  
The previous subscriber associated with a budget notification\.  
Type: [Subscriber](data-type-subscriber.md) object  
Required: Yes

**newSubscriber**  
The updated subscriber associated with a budget notification\.  
Type: [Subscriber](data-type-subscriber.md) object  
Required: Yes

## Errors<a name="update-sub-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="update-subscriber-examples"></a>

The following example request updates a subscriber associated with the notification for the budget named `Example Budget`\.

### Sample Request<a name="update-subscriber-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#UpdateSubscriber",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "notification": {
            "notificationType": "ACTUAL",
            "comparisonOperator": "GREATER_THAN",
            "threshold": 30
        },
        "oldSubscriber": {
            "subscriptionType": "SNS",
            "address": "exampleSnstopic"
        },
        "newSubscriber": {
            "subscriptionType": "EMAIL",
            "address": "example@example.com"
        },
        "accountId": "1234567890"
    }
}
```