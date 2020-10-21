# Best practices for the AWS Cost Explorer API<a name="ce-api-best-practices"></a>

The following are best practices when working with the [Cost Explorer API](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/API_Operations_AWS_Cost_Explorer_Service.html)\.

**Topics**
+ [Best practices for configuring access to the Cost Explorer API](#ce-api-best-practices-access)
+ [Best practices for querying the Cost Explorer API](#ce-api-best-practices-query)
+ [Best practices for optimizing your Cost Explorer API costs](#ce-api-best-practices-optimize-costs)

## Best practices for configuring access to the Cost Explorer API<a name="ce-api-best-practices-access"></a>

An IAM user must be granted explicit permission to query the Cost Explorer API\. Granting an IAM user access to the Cost Explorer API gives that user query access to any cost and usage data available to that account\. For the policy that grants the necessary permissions to an IAM user, see [View costs and usage](billing-example-policies.md#example-policy-ce-api)\.

When configuring access to the Cost Explorer API, we recommend creating a unique IAM user for allowing programmatic access\. If you want to give multiple IAM users query access to the Cost Explorer API, we recommend creating a programmatic access IAM role for each of them\.

## Best practices for querying the Cost Explorer API<a name="ce-api-best-practices-query"></a>

When querying the Cost Explorer API, we recommend using filtering conditions to refine your queries so that you receive only the data that you need\. You can do this by restricting the time range to a smaller interval or by using filters to limit the result set that your request returns\. This enables your queries to return data more quickly than if you're accessing a larger set of data\.

Adding one or more grouping dimensions to your query can increase the size of your result and can impact query performance\. Depending on your use case, it can make sense to filter your data instead\.

The Cost Explorer API can access up to 12 months of historical data and data for the current month\. It can also provide 3 months of cost forecast data at the daily level of granularity and 12 months of cost forecast data at the monthly level of granularity\.

## Best practices for optimizing your Cost Explorer API costs<a name="ce-api-best-practices-optimize-costs"></a>

Because you're charged for the Cost Explorer API per paginated request, we recommend identifying the exact dataset to access before submitting queries\.

AWS billing information is updated up to three times daily\. Typical workloads and use cases for the Cost Explorer API anticipate a call pattern cadence ranging from daily to several times per day\. To receive the most up\-to\-date data available, query for the time period that you're interested in\.

If you're creating an application using the Cost Explorer API, we recommend architecting the application so that it has a caching layer\. This enables you to regularly update the underlying data for your end users, but doesn't trigger queries every time that an individual in your organization accesses it\.