# Pricing Details<a name="pricing-columns"></a>

You can use the pricing columns to find information about the prices for a line item\. The pricing columns are based off of the AWS Price List Service API\. AWS Price List Service API doesn't include Free Tier pricing, spot instances, products in AWS Marketplace, upfront annual subscription fees \(`Fee`\), and monthly recurring fees \(`RIFee`\)\. The columns include but are not limited to the following:

** pricing/LeaseContractLength**  
The length of time that your RI is reserved for\.

** pricing/publicOnDemandCost**  
The total cost for the line item based on public On\-Demand Instance rates\. If you have SKUs with multiple On\-Demand public costs, the equivalent cost for the highest tier is displayed \(for example, services offering free\-tiers or tiered pricing\)\.

** pricing/publicOnDemandRate**  
The public On\-Demand Instance rate in this billing period for the specific line item of usage\. If you have SKUs with multiple On\-Demand public rates, the equivalent rate for the highest tier is displayed \(for example, services offering free\-tiers or tiered pricing\)\.

** pricing/PurchaseOption**  
How you chose to pay for this line item\. Valid values are `All Upfront`, `Partial Upfront`, and `No Upfront`\.

** pricing/RateId**  
The ID of the rate for a line item\. You can use the **RateId** to get up\-to\-date pricing for a product by using the [Using the AWS Price List API ](price-changes.md)\.

** pricing/term**  
Whether your AWS usage is Reserved or On\-Demand\. 

** pricing/unit**  
The pricing unit that AWS used for calculating your usage cost\. For example, the pricing unit for Amazon EC2 instance usage is in hours\.