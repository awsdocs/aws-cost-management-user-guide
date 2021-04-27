# Finding Savings Plan prices in an offer file<a name="sp-offer-file"></a>

You can use the offer files to find prices and discounts when Savings Plans are applied to your usage\.

The following procedures show how to find products participating in Savings Plans by downloading a Savings Plans CSV or JSON file\.<a name="find-sp-procedure"></a>

**To find Savings Plans for a service**

1. Download the index file\.

1. Navigate to your relevant service\.

1. Search for `savingsPlanVersionIndexUrl` to find Savings Plans rates that apply to the service\.

**Note**  
Some services might not have Savings Plans that apply\.<a name="find-sp-rates"></a>

**To find Savings Plans rates for a service**

1. Download the Savings Plans index file\.

1. Find the relevant `regionalIndexURLs` for the Regions\.

   The Compute Savings Plans that apply across multiple Regions will be in the **global** Region\.

1. Download the Savings Plans offer file\.
+ **Terms** includes the contract length and rates for all available Savings Plans\.
+ **Rates** lists all SKUs that are covered by Savings Plans along with the applicable rate\. Details of these SKUs are available in the individual service files\. For example, Amazon EC2, Fargate, and AWS Lambda\.

Files are available in both CSV and JSON format\.