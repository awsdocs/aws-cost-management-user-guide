# Budget<a name="data-type-budget"></a>

Represents the output of the `CreateBudget` operation\. The content consists of the detailed metadata and data file information, and the current status of the `budget`\.

The ARN pattern for a budget is: `arn:aws:budgetservice::AccountId:budget/budgetName`

## Contents<a name="data-type-budget-contents"></a>

**budgetLimit**  
The total amount of cost or usage that you want to track with a budget\.  
Type: [Spend](data-type-spend.md) object  
Required: Yes

**budgetName**  
The name of a budget\. Unique within accounts\.  
Type: String  
Pattern: \[^:\]\+  
Required: Yes

**budgetType**  
Whether this budget tracks monetary cost or usage\.  
Type: Enum  
Valid values: COST | USAGE | RI\_UTILIZATION  
Required: Yes

**calculatedSpend**  
The actual and forecasted cost or usage being tracked by a budget\.  
Type: Two [Spend](data-type-spend.md) objects  
Valid values:   
Required: No

**costFilters**  
The cost filters applied to a budget, such as service or region\.  
Type: String to string map  
Required: No

**costTypes**  
The types of cost included in a budget, such as tax and subscriptions\.  
Type: [CostTypes](data-type-cost.md) object  
Required: Yes

**timePeriod**  
The period of time covered by a budget\. Has a start date and an end date\. The start date must come before the end date\. There are no restrictions on the end date\.   
If you created your budget using the Billing and Cost Management console and didn't specify a start date, AWS defaults to the first day of the month\. If you created your budget using the Billing and Cost Management console and didn't specify an end date, AWS sets your end date to June 15, 2087\. You can change either date with the `UpdateBudget` operation\.    
After the end date, AWS deletes the budget and all associated notifications and subscribers\.  
Type: TimePeriod  
Required: Yes

**timeUnit**  
The length of time until a budget resets the actual and forecasted spend\.  
Type: Enum  
Valid values: MONTHLY | QUARTERLY | ANNUALLY  
Required: Yes