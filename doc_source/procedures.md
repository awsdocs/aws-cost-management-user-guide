# Finding Prices in an Offer File<a name="procedures"></a>

The Price List API provides prices for all AWS products for informational purposes, including On\-Demand and Reserved Instance pricing\. Price List API isn't available for limited\-period free tiers like AWS Free Tier pricing\.

You can use the offer files to find the prices and terms for a specific product\. For example, you can find a list of Amazon EC2 instance prices\.

Use the following procedures to find prices for the products you're interested in\.

**Topics**
+ [Finding On\-Demand Prices for services](#Ondemand-price-ec2)
+ [Finding tiered prices for services](#tiered-price)
+ [Finding tiered prices for services with Free Tier](#tiered-price-free)
+ [Finding prices for services with Reserved Instances](#price-ri)

## Finding On\-Demand Prices for services<a name="Ondemand-price-ec2"></a>

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

1. Under **Terms** and **on\-demand**, find the SKU of interest\.

   If you don't know the SKU, search for the **usage type** and **operation**\.

1. See the **pricePerUnit** to find the corresponding On\-Demand price for the SKU\.

## Finding tiered prices for services<a name="tiered-price"></a>

The following procedure shows how to find tiered prices for services \(for example, Amazon S3\)\.<a name="S3-csv-procedure"></a>

**To find tiered prices for services using the csv file**

1. Download the csv file for the service\.

1. Open the csv file with your program of choice\.

1. Under the **TermType** column, filter to show **OnDemand**\.

1. Find the usage type and operation of your choice\.

1. In the **PricePerUnit** column, see the corresponding price for each **BeginRange** and **EndRange**\.<a name="S3-json-procedure"></a>

**To find tiered prices for services using the JSON file**

1. Download the JSON file\.

1. Open the JSON file with your program of choice\.

1. Under **Terms** and **on\-demand**find the SKU of interest\.

   If you don't know the SKU, search for the **usage type** and **operation**\.

1. Under each **beginRange** and **endRange**, see the **pricePerUnit** to find the corresponding tiered prices\.

## Finding tiered prices for services with Free Tier<a name="tiered-price-free"></a>

The following procedure shows how to find tiered prices for services with Free Tier \(for example, AWS Lambda\)\.<a name="Lambda-csv-procedure"></a>

**To find prices for services with Free Tier using csv**

1. Download the csv file for the service\.

1. Open the csv file with your program of choice\.

1. Under the **TermType** column, filter to show **OnDemand** and **Location**\.

1. Choose **Any**\.

1. To find the covered usage by Free Tier across all locations, see the **BeginRange** and **EndRange**\.

1. To find a list of eligible locations and SKU for any Free Tier SKU, replace **Global** in the **usageType** with a relevant Region or wild card character\. This shows all applicable products and AWSRegions\.<a name="Lambda-json-procedure"></a>

**To find tiered prices for services with Free Tier using the JSON file**

1. Download the JSON file for the service\.

1. Open the JSON file with your program of choice\.

1. Under **products**, find the **usageType** with the Region prefix **Global**\.

1. Take note of the SKU and look for the same SKU under **terms** and **OnDemand**\.

1. For the amount of Free Tier usage, see the **BeginRange** and **EndRange** \.

   For a list of products and Regions covered by Free Tier, see **appliesTo**\.

## Finding prices for services with Reserved Instances<a name="price-ri"></a>

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

1. Under **Terms** and **Reserved**, find the SKU of interest\.

   If you don't know the SKU, search for the **usage type** and **operation**\.

You can find prices for all **LeaseContractLength**, **PurchaseOption**, and **OfferingClass** for the same product\.