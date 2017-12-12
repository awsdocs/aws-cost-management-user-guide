# CalculatedSpend<a name="data-type-calculated-spend"></a>

The spend objects associated with this budget\. The `actualSpend` tracks how much you've used, cost or usage, and the `forecastedSpend` tracks how much you are predicted to spend if your current usage remains steady\.

For example, if it is the 20th of the month and you have spent `50` dollars on Amazon EC2, your `actualSpend` is `50 USD`, and your `forecastedSpend` is `75 USD`\.

## Contents<a name="data-type-calculated-spend-contents"></a>

**actualSpend**  
The amount of cost or usage that you have used\.  
Type: [Spend](data-type-spend.md) object  
Required: Yes

**forecastedSpend**  
The amount of cost or usage that you are forecasted to use\.  
Type: [Spend](data-type-spend.md) object  
Required: No