# Amortizing Reserved Instances<a name="amortizing-ri"></a>

Amortizing is when you distribute one\-time reservation costs across the billing period that is affected by that cost\. That enables you to see your costs in accrual\-based accounting as opposed to cash\-based accounting\. For example, if you pay $365 for an All Upfront RI for one year and you have a matching instance that uses that RI, that instance costs you $1 a day, amortized\.

You can see the data that Billing and Cost Management uses to calculate your amortized costs in the following AWS Cost and Usage report columns\. 

## Reserved Instance Inventory<a name="ri-inventory"></a>

You can use the following columns to track your RI inventory\. The values for these columns appear only for RI subscription line items \(also known as `RI Fee` line items\) and not for the actual instances using the RIs\.

** reservation/UpfrontValue**  
The initial upfront payment value for All Upfront RIs and Partial Upfront RIs\.   
Because there are no upfront payments for No Upfront RIs, the value for this line for No Upfront RIs is `0`\.

** reservation/startTime**  
The start time for a Reserved Instance reservation\.

** reservation/endTime**  
The end time for a Reserved Instance reservation\.

** reservation/modificationStatus**  
The modification status of a Reserved Instance reservation\. For example, if you bought an RI and never modified it, the value is `Original`\. If you bought an RI and modified it using the console or API, the value is `System`\. If you bought an RI and modified it with CS's help, the value is `Manual`\. If you bought an RI and modified it with CS's help, and AWS calculated estimated costs for the RI, the value is `ManualWithData`\.  
Valid values are: `Original`, `System`, `ManualWithData`, and `Manual`\.

## Amortization Data for the Billing Period<a name="understanding-ri"></a>

You can use the following columns to understand the amortized costs of your RIs for the billing period\. The values for these columns appear only for RI subscription line items \(also known as `RI Fee` line items\) and not for the actual instances using the RIs\.

** reservation/amortizedUpfrontFeeForBillingPeriod**  
The initial upfront payment for All Upfront RIs and Partial Upfront RIs, amortized over this month\. Because there are no upfront fees for No Upfront RIs, the value for No Upfront RIs is `0`\.  
This tells you how much the upfront fee for this reservation costs you for this billing period\. 

** reservation/unusedQuantity**  
The number of RI hours that you didn't use during this billing period\.

** reservation/unusedNormalizedUnitQuantity**  
The number of unused normalized units for a size\-flexible regional RI that you didn't use during this billing period\.

** reservation/unusedRecurringFee**  
The recurring fees associated with your unused reservation hours for Partial Upfront and No Upfront RIs\.  
Because All Upfront RIs don't have recurring fees greater than `0`, the value for All Upfront RIs is `0`\.

** reservation/unusedAmortizedUpfrontFeeForBillingPeriod**  
The amortized portion of the initial upfront fee for All Upfront RIs and Partial Upfront RIs\. Because there are no upfront payments for No Upfront RIs, the value for No Upfront RIs is `0`\.

## Reserved Instance Effective Costs<a name="effective-costs"></a>

You can use the following columns to understand your effective cost at the instance level\. The values for these columns appear only for instance usage line items \(also known as `Discounted Usage boxUsage` line items\)\. 

** reservation/amortizedUpfrontCostForUsage**  
The initial upfront payment for All Upfront RIs and Partial Upfront RIs amortized for usage time\. Because there are no upfront payments for No Upfront RIs, the value for a No Upfront RI is `0`\.

** reservation/recurringFeeForUsage**  
For Partial Upfront RIs and No Upfront RIs, this is the recurring fee amortized for usage time\. Because All Upfront RIs don't have recurring fee payments greater than `0`, the value for All Upfront RIs is `0`\.

** reservation/effectiveCost**  
The total effective cost of your usage with RI rates applied\. This is calculated by taking the `amortizedUpfrontCostForUsage` and adding it to the `recurringFeeForUsage`\.