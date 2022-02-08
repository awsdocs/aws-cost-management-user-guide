# Using the AWS Price List API<a name="price-changes"></a>

AWS offers two APIs that you can use to query prices:
+ With the AWS Price List Bulk API, you can query the prices of AWS services in bulk\. The API returns either a JSON or a CSV file\. The bulk API retains all historical versions of the price list\.
+ With the AWS Price List Query API, you can query specific information about AWS services, products, and pricing using an AWS SDK or the AWS CLI\. This API can retrieve information about certain products or prices, rather than retrieving prices in bulk\. This allows you to get pricing information in environments that might not be able to process a bulk price list, such as in mobile or web browser\-based applications\. For example, you can use the query API to fetch pricing information for Amazon EC2 instances with 64 vCPUs, 256 GiB of memory, and pre\-installed SQL Server Enterprise in the Asia Pacific \(Mumbai\) Region\. The query API serves the current prices and doesn’t retain historical prices\.

**Topics**
+ [Using the query API](using-pelong.md)
+ [Using the bulk API](using-ppslong.md)
+ [Setting up notifications](price-notification.md)