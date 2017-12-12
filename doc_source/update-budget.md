# UpdateBudget<a name="update-budget"></a>

Updates a budget\. You can change every part of a budget except for the `budgetName` and the `calculatedSpend`\. When a budget is modified, the `calculatedSpend` drops to zero until AWS has new usage data to use for forecasting\.

## Request Parameters<a name="update-budget-request-parameters"></a>

The request requires the following data in JSON format\.

**accountId**  
The `accountId` that is associated with the budget\.  
Type: String  
Length constraints: Minimum length of `12`, maximum length of `12`\.  
Required: Yes

**newBudget**  
The budget that you want to update your budget to\.  
Type: [Budget](data-type-budget.md) object  
Required: Yes

## Errors<a name="update-budget-errors"></a>

**InternalErrorException**  
An error on the server occurred during the processing of your request\. Try again later\.  
HTTP Status Code: 500

**InvalidParameterException**  
An error on the client occurred\. Typically, the cause is an invalid input value\.  
HTTP Status Code: 400

**NotFoundException**  
We can’t locate the resource that you specified\.  
HTTP Status Code: 400

## Examples<a name="update-budget-examples"></a>

The following example request updates a budget named `Example Budget`\.

### Sample Request<a name="update-budget-examples-sample-request"></a>

```
{
    "Operation": "com.amazonaws.awsbudgets#UpdateBudget",
    "Service": "com.amazonaws.awsbudgets#AWSBudgets",
    "Input": {
        "newBudget":{
           "budgetName":"Example Budget",
           "budgetLimit":{
      		    "amount":"200",
	      		"unit":"USD"
	      	},
           "costFilters":{
               "AZ":"us-east-1"
	      	},
           "costTypes":{      		    "includeCredit":"true",
      		    "includeDiscount":"true",
      		    "includeOtherSubscription":"true",
      		    "includeRecurring":"true",
      		    "includeRefund":"true",
                       "includeSubscription":"false",
      		    "includeSupport":"true",
      		    "includeTax":"true",
      		    "includeUpfront":"true",<!--
      		    "useAmortized":"true",-->
      		    "useBlended":"false"
	      	},
           "timeUnit":"MONTHLY",
           "timePeriod":{
	      	    "start":"1477353600000",
	      		"end":"1478958399000"
	        },
           "budgetType":"COST"
         },
        "accountId": "1234567890"
    }
}
```