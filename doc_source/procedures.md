# Finding prices in an offer file<a name="procedures"></a>

The Price List Service API provides prices for all AWS products for informational purposes, including On\-Demand and Reserved Instance pricing\.

You can use the offer files to find the prices and terms for a specific product\. For example, you can find a list of Amazon EC2 instance prices\.

**Note**  
The Price List Service API is not a comprehensive source for limited period Free Tiers, such as AWS Free Tier pricing\. For complete information on Free Tier prices, see [AWS Free Tier](https://aws.amazon.com/free/)\.

Use the following procedures to find prices for the products you're interested in\.

**Topics**
+ [Finding On\-Demand prices for services](#Ondemand-price-ec2)
+ [Finding tiered prices for services](#tiered-price)
+ [Finding tiered prices for services with free tier](#tiered-price-free)
+ [Finding prices for services with reserved instances](#price-ri)

## Finding On\-Demand prices for services<a name="Ondemand-price-ec2"></a>

The following procedure shows how to find On\-Demand prices for services \(for example, Amazon EC2\)\.<a name="ec2-csv-procedure"></a>

**To find an On\-Demand price using the csv file**

1. Download the csv file for the service\.

1. Open the csv file with your program of choice\.

1. Under the **TermType** column, filter to show **OnDemand**\.

1. Find the usage type and operation of your choice\.

1. In the **PricePerUnit** column, see the corresponding price\.<a name="ec2-json-procedure"></a>

**To find an On\-Demand price using the JSON file**

1. Download the JSON file for the service\.

1. Open the JSON file with your program of choice\.

1. Under **terms** and **On\-Demand**, find the SKU of interest\.

   If you don't know the SKU, search under **products** for the **usage type** and **operation**\.

1. See the **pricePerUnit** to find the corresponding On\-Demand price for the SKU\.

## Finding tiered prices for services<a name="tiered-price"></a>

The following procedure shows how to find tiered prices for services \(for example, Amazon S3\)\.<a name="S3-csv-procedure"></a>

**To find tiered prices for services using the csv file**

1. Download the csv file for the service\.

1. Open the csv file with your program of choice\.

1. Under the **TermType** column, filter to show **OnDemand**\.

1. Find the usage type and operation of your choice\.

1. In the **PricePerUnit** column, see the corresponding price for each **StartingRange** and **EndingRange**\.<a name="S3-json-procedure"></a>

**To find tiered prices for services using the JSON file**

1. Download the JSON file\.

1. Open the JSON file with your program of choice\.

1. Under **terms** and **On\-Demand**find the SKU of interest\.

   If you don't know the SKU, search under **products** for the **usage type** and **operation**\.

1. Under each **beginRange** and **endRange**, see the **pricePerUnit** to find the corresponding tiered prices\.

## Finding tiered prices for services with free tier<a name="tiered-price-free"></a>

The following procedure shows how to find AWS services that publish free tier prices in the Price List Service API \(for example, AWS Lambda\)\.

All Free Tier prices are subject to the terms documented in [AWS Free Tier](https://aws.amazon.com/free/)\.<a name="Lambda-csv-procedure"></a>

**To find prices for services with free tier using csv**

1. Download the csv file for the service\.

1. Open the csv file with your program of choice\.

1. Under the **TermType** column, filter to show **OnDemand**\.

1. Under the **Location** column, filter to show **Any**\.

   **Any** does not represent all AWS Regions in this scenario\. It is a subset of Regions defined by other line items in the csv file, with a **RelatedTo** column matching the SKU for the location **Any** entry\.

1. To find a list of all eligible locations and products for a given Free Tier SKU, find the Free Tier SKU under the **RelatedTo** column\.

1. To find the covered usage by Free Tier across all eligible locations, see the **StartingRange** and **EndingRange** for the location **Any**\.

### Example<a name="tiered-price-free-example"></a>

This example assumes there are no more entries in the price file where **RelatedTo** equals to the SKU `ABCD`\.

The free tier offer with SKU `ABCD` is valid in Regions `Asia Pacific (Singapore)` and `US East (Ohio)`, but not in `AWS GovCloud (US)`\. The covered usage by Free Tier is 400,000 seconds total, used across both eligible Regions\.


****  

| SKU | StartingRage | EndingRange | Unit | RelatedTo | Location | 
| --- | --- | --- | --- | --- | --- | 
| ABCD | 0 | 400000 | seconds |  | Any | 
| QWER | 0 | Inf | seconds | ABCD | Asia Pacific \(Singapore\) | 
| WERT | 0 | Inf | seconds | ABCD | US East \(Ohio\) | 
| ERTY | 0 | Inf | seconds |  | AWS GovCloud \(US\) | <a name="Lambda-json-procedure"></a>

**To find tiered prices for services with free tier using the JSON file**

1. Download the JSON file for the service\.

1. Open the JSON file with your program of choice\.

1. Under **products**, find the **usagetype** with the Region prefix **Global**\.

1. Take note of the SKU and look for the same SKU under **terms** and **OnDemand**\.

1. For the amount of Free Tier usage, see the **BeginRange** and **EndRange** \.

   For a list of products and Regions covered by Free Tier, see **appliesTo**\.

## Finding prices for services with reserved instances<a name="price-ri"></a>

The following procedure shows how to find prices for services with Reserved Instances \(for example, Amazon RDS\)\.<a name="ec2-csv-procedure"></a>

**To find an Reserved Instance using the csv file**

1. Download the EC2 csv file for the service\.

1. Open the csv file with your program of choice\.

1. Under the **TermType** column, filter to show **reserved**\.

1. Find the usage type and operation of your choice\.

1. For each **LeaseContractLength**, **PurchaseOption**, and **OfferingClass**, see the **PricePerUnit** column for the corresponding price \.<a name="ec2-json-procedure"></a>

**To find an prices for Reserved Instance using the JSON file**

1. Download the JSON file for the service\.

1. Open the JSON file with your program of choice\.

1. Under **terms** and **Reserved**, find the SKU of interest\.

   If you don't know the SKU, search under **products** for the **usage type** and **operation**\.

You can find prices for all **LeaseContractLength**, **PurchaseOption**, and **OfferingClass** for the same product\.