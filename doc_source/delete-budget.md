# DeleteBudget<a name="delete-budget"></a>

Deletes a budget\. You can delete your budget at any time\.

**Warning**  
Deleting a budget also deletes the notifications and subscribers associated with that budget\.

## Request Parameters<a name="delete-budget-request-parameters"></a>

The request requires the following data in JSON format\.

**accountId**  
The `accountId` that is associated with the budget\.  
Type: String  
Length constraints: Minimum length of `12`, maximum length of `12`\.  
Required: Yes

**budgetName**  
The name of the budget that you want to delete\.  
Type: String  
Pattern: \[^:\]\+  
Required: Yes

## Errors<a name="delete-budget-errors"></a>

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

## Examples<a name="delete-budget-examples"></a>

The following example request deletes the budget named `Example Budget`\.

### Sample Request<a name="delete-budget-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#DeleteBudget",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "accountId": "1234567890"
    }
}
```