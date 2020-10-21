# Using the query API<a name="using-pelong"></a>

AWS Price List Service API is a centralized and convenient way to programmatically query AWS for services, products, and pricing information\. The Price List Service API uses standardized product attributes such as `Location`, `Storage Class`, and `Operating System`, and provides prices at the SKU level\. You can use Price List Service to build cost control and scenario planning tools, reconcile billing data, forecast future spend for budgeting purposes, and provide cost benefit analyses that compare your internal workloads with AWS\. The query API does not support Savings Plans prices\.

If you use a programming language that AWS provides an SDK for, we recommend that you use the SDK\. All of the AWS SDKs greatly simplify the process of signing requests and save you a significant amount of time when compared with using the Price List Service API\. In addition, the SDKs integrate easily with your development environment and provide easy access to related commands\.

**Note**  
The Price List Service API provides pricing details for your information only\. If there is a discrepancy between the offer file and a service pricing page, AWS charges the prices that are listed on the service pricing page\. For more information about AWS service pricing, see [Cloud Services Pricing](https://aws.amazon.com/pricing/services/)\.

For more information about available SDKs, see [Tools for Amazon Web Services](https://aws.amazon.com/tools)\. For more information about the AWS Price List Service API, see the [AWS Billing and Cost Management API Reference](https://docs.aws.amazon.com/aws-cost-management/latest/APIReference/API_Operations_AWS_Price_List_Service.html)\.

## Service endpoint<a name="pe-endpoint"></a>

AWS Price List Service API provides the following two endpoints:
+ **https://api\.pricing\.us\-east\-1\.amazonaws\.com**
+ **https://api\.pricing\.ap\-south\-1\.amazonaws\.com**

## Granting IAM permissions to use the AWS Price List Service API<a name="pe-iam"></a>

An IAM user must be granted explicit permission to query the AWS Price List Service API\. For the policy that grants the necessary permissions to an IAM user, see [Find products and prices](billing-example-policies.md#example-policy-pe-api)\. 