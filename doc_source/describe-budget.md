# DescribeBudget<a name="describe-budget"></a>

Describes a budget\.

## Request Parameters<a name="describe-budget-request-parameters"></a>

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

## Response Elements<a name="describe-budget-responses"></a>

This operation returns the following parameters\.

**budget**  
Returns a budget object\.  
Type: [Budget](data-type-budget.md) object

## Errors<a name="describe-bud-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="describe-budget-examples"></a>

The following example requests a budget named `Example Budget`\.

### Sample Request<a name="describe-budget-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#DescribeBudget",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "budgetName": "Example Budget",
        "accountId": "1234567890"
    }
}
```