# Spend<a name="data-type-spend"></a>

The amount of cost or usage being measured for a budget\.

For example, a `Spend` for `3 GB` of S3 usage would have the following parameters:

+ An `Amount` of `3`

+ A `unit` of `GB`

## Contents<a name="data-type-spend-contents"></a>

**amount**  
The cost or usage amount associated with a budget forecast, actual spend, or budget threshold\.  
Type: Double  
Required: Yes

**unit**  
The unit of measurement used for the budget forecast, actual spend, or budget threshold, such as dollars or GB\.  
Type: String  
Required: Yes