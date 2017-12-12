# CostFilter<a name="data-type-filter"></a>

The Cost Explorer filters for a budget\.

## Contents<a name="data-type-filter-contents"></a>

**key**  
The Cost Explorer key for this filter\.  
Valid keys for a cost filter are `AZ`, `LinkedAccount`, `Operation`, `PurchaseType`, `Service`, and `TagKeyValue`\.   
Valid keys for a usage filter are `AZ`, `LinkedAccount`, `Operation`, `PurchaseType`, `UsageType:<service name>`, and `TagKeyValue`\.  
Type: String  
Required: No

**values**  
The values for the key, such as a specific Availability Zone, tag, or service name\.  
Type: List<String>  
Required: No