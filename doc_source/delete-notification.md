# DeleteNotification<a name="delete-notification"></a>

Deletes a notification\.

**Warning**  
Deleting a notification also deletes the subscribers associated with the notification\.

## Request Parameters<a name="delete-notification-request-parameters"></a>

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
The notification that you want to delete\.  
Type: [Notification](data-type-notification.md) object  
Required: Yes

## Errors<a name="delete-noti-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="delete-notification-examples"></a>

The following example request deletes a notification for the budget named `Example Budget`\.

### Sample Request<a name="delete-notification-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#DeleteNotification",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "notification": {
            "notificationType": "ACTUAL",
            "comparisonOperator": "GREATER_THAN",
            "threshold": 80
        },
        "accountId": "1234567890"
    }
}
```