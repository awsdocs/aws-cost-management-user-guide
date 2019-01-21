# Using the Bulk API<a name="using-ppslong"></a>

The AWS Price List API is actually a URL that provides up\-to\-date pricing information on the current AWS products and services\. To access pricing information using the AWS Price List API, download the offer file:
+ **Offer file** – A JSON or CSV file that lists the products and prices for either a single AWS service in all regions or a single AWS service in a specific region\. For more information, see [Downloading an Offer File](#download-offers)\.

To find a list of all available offer files, download the offer index file:
+ **Offer index file** – A JSON file that lists the supported AWS services, with a URL for each offer file where you can download pricing details\. The file also includes metadata about the offer index file itself, URLs for service offer files, and URLs for regional offer index files\. For more information, see [Downloading an Offer Index File](#download-the-offer-index)\.

Offer files don't include information about expiring free tier offers or Amazon EC2 Spot Instances\. 

**Note**  
The AWS Price List API provides pricing details for your information only\. If there is a discrepancy between the offer file and a service pricing page, AWS charges the prices that are listed on the service pricing page\. For more information about AWS service pricing, see [Cloud Services Pricing](https://aws.amazon.com/pricing/services/)\.

**Topics**
+ [Downloading an Offer Index File](#download-the-offer-index)
+ [Downloading an Offer File](#download-offers)
+ [Finding Prices in an Offer File](procedures.md)
+ [Reading an Offer File](reading-an-offer.md)
+ [Reading the Offer Index File](reading-the-offer-index.md)

To receive SNS notifications when prices change, see [Setting Up Notifications](price-notification.md)\.

## Downloading an Offer Index File<a name="download-the-offer-index"></a>

To download the offer index file, go to the following [URL](https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/index.json):

```
https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/index.json
```

The URL opens the offer index file\. In the offer index file, search for the service that you want prices for\. You need the service code to download the service\-specific offer file\. To download an offer index file for a specific service and region, find the service that you want prices for and open the regional offer index file\.

For more information, see [Reading the Offer Index File](reading-the-offer-index.md)\.

## Downloading an Offer File<a name="download-offers"></a>

To download the offer file for the service that you want, go to the URL for that offer file\. For example, to download the current JSON version of the Amazon EC2 offer file, go to the following [URL](https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/AmazonEC2/current/index.json):

```
https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/AmazonEC2/current/index.json
```

The offer index file includes the JSON URLS\. To download the CSV version, replace the `.json` extension in the offer file URL with `.csv`\. If you want to download the offer file for a specific service and you know the service code, replace the `AmazonEC2` in the URL with the service code to download the offer file for that service\. If you don't know the service code, download the offer index file to find it\. If you want to download the offer file for a specific service in a specific region and you know the service code and region, use the URL for that regional offer file\. For example, to download the current JSON version of the Amazon EC2 offer file for US East \(N\. Virginia\), use the following [URL](https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/AmazonEC2/current/us-east-1/index.json):

```
https://pricing.us-east-1.amazonaws.com/offers/v1.0/aws/AmazonEC2/current/us-east-1/index.json
```

If you access the offer files programmatically, you can use the offer index file to find the current URLs\. For more information about the offer index file, see [Finding Prices in an Offer File](procedures.md) and [Reading an Offer File](reading-an-offer.md)\.