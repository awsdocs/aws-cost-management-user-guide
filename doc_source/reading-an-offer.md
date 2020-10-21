# Reading an offer file<a name="reading-an-offer"></a>

An offer file lists the products and prices for a single AWS service in all Regions or a single AWS service in a specific Region\. Offer files are available as either CSV or JSON files\. You can read the files in multiple ways, such as using a spreadsheet program to read and sort the CSV file, a text program to read the file, or a program that parses JSON\.

Offer files include the following types of information:
+ [Offer file details](#offer-term-defs) – File metadata about the offer file itself, such as the format version and the publication date\.
+ [Product details](#offer-product-defs) – Product metadata that lists the products in an offer file along with product information\.
+ [Pricing details \(terms\)](#pricing-details) – Prices for all the products in this offer file\.

**Note**  
In a CSV file, the product and pricing details are combined into one section\. In a JSON file, the product details and pricing details are in separate sections\.

**Topics**
+ [CSV file](#csv)
+ [JSON file](#json)
+ [Offer file definitions](#pps-defs)

## CSV file<a name="csv"></a>

The first five rows of the CSV are the metadata for the offer file\. The sixth row has all the column names for the products and their attributes, such as the SKU, the `OfferTermCode`, the `RateCode`, the `TermType`, and more\. The number of columns varies depending on the service\. The first 12 columns contain all the pricing details, while the other columns contain the product details for a service\.

## JSON file<a name="json"></a>

In the JSON files, the product details and pricing details are in separate sections\. The same product can be offered under multiple terms, and the same term could apply to multiple products\. For example, an EC2 instance is available for an `Hourly` or `Reserved` term\. Use the SKU of a product to identify the terms that are available for that product\.

A JSON offer file looks like this:

```
{
   "formatVersion":"The version of the file format",
   "disclaimer":"The disclaimers for the offer file",
   "offerCode":"The code for the service", 
   "version":"The version of the offer file",
   "publicationDate":"The publication date of the offer file", 
   "Products": {  
      "sku": {
         "sku":"The SKU of the product",
         "productFamily":"The product family of the product", 
         "attributes": {
            "attributeName":"attributeValue", 
         }    
      }  
   }, 
   "Terms": {
      "termType": {
         "sku": {
            "sku": {      
               "offerTermCode":"The term code of the product", 
               "sku":"The SKU of the product",
               "effectiveDate":"The effective date of the pricing details", 
               "termAttributesType":"The attribute type of the terms", 
               "termAttributes": { 
                  "attributeName":"attributeValue", 
               }, 
               "priceDimensions": {       
                  "rateCode": {     
                     "rateCode":"The rate code of the price", 
                     "description":"The description of the term", 
                     "unit":"The usage measurement unit for the price", 
                     "startingRange":"The start range for the term", 
                     "endingRange":"The end range for the term", 
                     "pricePerUnit": {       
                        "currencyCode":"currencyRate", 
                     }            
                  }          
               }        
            }      
         }    
      }  
   }
}
```

## Offer file definitions<a name="pps-defs"></a>

Each of the sections in an offer file includes specific details about that product:
+ [Offer file details](#offer-term-defs) – File metadata about the offer file itself, such as the format version and the publication date\.
+ [Product details](#offer-product-defs) – Product metadata that lists the products in an offer file along with product information\.
+ [Pricing details \(terms\)](#pricing-details) – Prices for all the products in this offer file\.

**Note**  
In a CSV file, the product and pricing details are combined into one section\. In a JSON file, the product details and pricing details are in separate sections\.

The following lists provide definitions for each detail\.

### Offer file details<a name="offer-term-defs"></a>

This section provides metadata about the offer file itself\.

**Format Version**  
An attribute that tracks which format version the offer file is in\. The `formatVersion` of the file is updated when the structure is changed\. For example, the version will change from `v1` to `v2`\. 

**Disclaimer**  
Any disclaimers that apply to the offer file\.

**Offer Code**  
A unique code for the product of an AWS service\. For example, `AmazonEC2` for Amazon EC2 or `AmazonS3` for Amazon S3\.

**Version**  
An attribute that tracks the version of the offer file\. Each time a new file is published, it contains a new version number\. For example, `20150409T022205` and `20150910T182105`\.

**Publication Date**  
The date and time \(UTC\) when an offer file was published\. For example, `2015-04-09T02:22:05Z`, `2015-09-10T18:21:05Z`\.

### Product details<a name="offer-product-defs"></a>

This section provides information about products in an AWS service offer file\. Products are indexed by SKU\.

**Product Details:SKU**  
A unique code for a product\. Use the `SKU` code to correlate product details and pricing\. For example, a product with a SKU of `HCNSHWWAJSGVAHMH` is available only for a price that also lists `HCNSHWWAJSGVAHMH` as a `SKU`\.

**Product Details:SKU:Product Family**  
The category for the type of product\. For example, `compute` for Amazon EC2 or `storage` for Amazon S3\. 

**Product Details:SKU:Attributes**  
A list of all of the product attributes\. 

**Product Details:SKU:Attributes:Attribute Name**  
The name of a product attribute\. For example, `Instance Type`, `Processor`, or `OS`\. 

**Product Details:SKU:Attributes:Attribute Value**  
The value of a product attribute\. For example, `m1.small` \(an instance type\), `xen` \(a type of processor\), or `Linux` \(a type of OS\)\. 

### Pricing details \(terms\)<a name="pricing-details"></a>

This section provides information about the prices for products in an AWS service offer file\. Prices are indexed first by the terms \(`onDemand` and `reserved`\), and then by SKU\.

**Pricing Details:Term Type**  
The specific type of term that a term definition describes\. The valid term types are `reserved` and `onDemand`\.

**Pricing Details:Term Type:SKU**  
A unique code for a product\. Use the `SKU` code to correlate product details and pricing\. For example, a product with a SKU of `HCNSHWWAJSGVAHMH` is available only for a price that also lists `HCNSHWWAJSGVAHMH` as a `SKU`\.

**Pricing Details:Term Type:SKU:Offer Term Code**  
A unique code for a specific type of term\. For example, `KCAKZHGHG`\. Product and price combinations are referenced by the SKU code followed by the term code, separated by a period\. For example, `U7ADXS4BEK5XXHRU.KCAKZHGHG`\.

**Pricing Details:Term Type:SKU:Effective Date**  
The date that an offer file goes into effect\. For example, if a term has an `EffectiveDate` of November 1, 2017, the price is not valid before November 1, 2017\.

**Pricing Details:Term Type:SKU:Term Attributes Type**  
A unique code for identifying what product and product offering are covered by a term\. For example, an EC2\-Reserved attribute type means that a term is available for EC2 reserved hosts\.

**Pricing Details:Term Type:SKU:Term Attributes**  
A list all of the attributes that are applicable to a term type, in the format `attribute-name: attribute-value`\. For example, length of term and type of purchase covered by the term\. 

**Pricing Details:Term Type:SKU:Term Attributes:Attribute Name**  
The name of a `TermAttribute`\. You can use it to look up specific attributes\. For example, you can look up terms by `length` or `PurchaseOption`\.

**Pricing Details:Term Type:SKU:Term Attributes:Attribute Value**  
The value of a `TermAttribute`\. For example, terms can have a length of one year and a purchase option of `All Upfront`\. 

**Pricing Details:Term Type:SKU:Price Dimensions**  
The pricing details for the offer file, such as how usage is measured, the currency that you can use to pay with, and the pricing tier limitations\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code**  
A unique code for a product/offer/pricing\-tier combination\. Product and term combinations can have multiple price dimensions, such as a free tier, a low use tier, and a high use tier\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Description**  
The description for a price or rate\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Unit**  
The type of unit that each service uses to measure usage for billing\. For example, EC2 uses hours as a measuring unit, and S3 uses GB as a measuring unit\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Starting Range**  
The lower limit of the price tier covered by this price\. For example, 0 GB or 1,001 API calls\. 

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Ending Range**  
The upper limit of the price tier covered by this price\. For example, 1,000 GB or 10,000 API calls\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Price Per Unit**  
A calculation of how much a single measured unit for a service costs\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Price Per Unit:Currency Code**  
A code that indicates the currency for prices for a specific product\.

**Pricing Details:Term Type:SKU:Price Dimensions:Rate Code:Price Per Unit:Currency Rate**  
The rate for a product in various supported currencies\. For example, $1\.2536 per unit\.