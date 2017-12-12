# Identity Details<a name="enhanced-identity-columns"></a>

Columns under the **identity** header are static fields that appear in every AWS Cost and Usage report\. You can use the identity line items in the AWS Cost and Usage report to find specific line items that have been split across multiple AWS Cost and Usage report files\. This includes the following columns: 

** identity/LineItemId**  
An ID that uniquely identifies every line item in a single given version of the AWS Cost and Usage report\. The line item ID is not consistent between different AWS Cost and Usage reports, and can't be used to identify the same line item across different AWS Cost and Usage reports\.   
For example, the AWS Cost and Usage report created for November 29 can be large enough to require multiple files\. The **LineItemId** is consistent between the November 29 AWS Cost and Usage report files, but doesn't match the **LineItemId** for the same resource in the November 30 AWS Cost and Usage report\.

** identity/TimeInterval**  
The time interval that this line item applies to, in the following format: `YYYY-MM-DDTHH:mm:ssZ/YYYY-MM-DDTHH:mm:ssZ`\. The time interval is in UTC, and can be either daily or hourly depending on the granularity of the report\.  
For example, `2017-11-01T00:00:00Z/2017-12-01T00:00:00Z` includes the entire month of November, 2017\.