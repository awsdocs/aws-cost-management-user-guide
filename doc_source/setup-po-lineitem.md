# Setting up purchase order configurations<a name="setup-po-lineitem"></a>

You can use purchase orders and their line item attributes to flexibly define a configuration that best fits your needs\. The following are examples of purchase order configuration scenarios that you can use\.

You can configure separate purchase orders for different time periods by choosing distinct effective and expiration months\.

**Example 1**  
If you use monthly purchase orders, you can define one purchase order for each month by selecting the same effective and expiration month for each purchase order\. The purchase order will only apply to invoices that are generated during that month\.   
Here are a few purchase order configurations that you can use for this setup:  
+ `PO #M1_2021` with the effective month set to Jan 2021 and expiration month Jan 2021\.
+ `PO #M2_2021` with the effective month set to Feb 2021 and expiration month Feb 2021\.
+ `PO #M3_2021` with the effective month set to Mar 2021 and expiration month Mar 2021\.
Here is an example of how you can also define a purchase order for a particular quarter, half\-year, or the entire year:  
+ `PO #Q4_2021` with the effective month set to Apr 2021 and expiration month Jun 2021\.
+ `PO #2H_2021` with the effective month set to Jul 2021 and expiration month Dec 2021\.
+ `PO #2022Y` with the effective month set to Jan 2022 and expiration month as Dec 2022\.

**Example 2**  
You can configure separate purchase orders for different types of invoices through line item configurations\.  
+ `PO #Anniversary_Q4_2021` with the effective month set to Apr 2021, and expiration month Jun 2021, `Line item type = AWS monthly usage`\.
+ `PO #Subscriptions_Q4_2021` with the effective month set to Apr 2021, and expiration month Jun 2021, `Line item type = AWS Subscription Purchase`\.
+ `PO #Marketplace_Q4_2021` with the effective month set to Apr 2021, and expiration month Jun 2021, `Line item type = AWS Marketplace Purchase`\.

You can track the balance of a given purchase order for different time periods by configuring granular line item start and end months\.

**Example 3**  
Consider `PO #Q4_2021` from Example 1 with an effective month of Apr 2021 and an expiration month Jun 2021\. You can track this PO's balance on a monthly basis by setting up the following line items:  
+ `Line item #1` with the start month Apr 2021, end month Apr 2021, `Line item type = ALL`\.
+ `Line item #2` with the start month May 2021, end month May 2021, `Line item type = ALL`\.
+ `Line item #3` with the start month Jun 2021, end month Jun 2021, `Line item type = ALL`\.

Alternatively, you can track balance for each line item type separately for the same purchase order and time period\.

**Example 4**  
The same `PO #Q4_2021` from Example 1 can be set up using the following configuration to track balance of different line item types separately\.  
+ `Line item #1` with the start month Apr 2021, end month Jun 2021, `Line item type = AWS monthly usage`\.
+ `Line item #1.2` with the start month Apr 2021, end month Jun 2021, `Line item type = AWS Subscription Purchase`\.
+ `Line item #1.3` with the start month Apr 2021, end month Jun 2021, `Line item type = AWS Marketplace Purchase`\.

Continue this configuration for May and June\.

**Example 5**  
You can also combine the previous two configurations to track balances for different time periods and line item types separately\.  
+ `Line item #1.1` with the start month Apr 2021, end month Apr 2021, `Line item type = AWS monthly usage`\.
+ `Line item #1.2` with the start month Apr 2021, end month Apr 2021, `Line item type = AWS Subscription Purchase`\.
+ `Line item #1.3` with the start month Apr 2021, end month Apr 2021, `Line item type = AWS Marketplace Purchase`\.

Continue this configuration for May and June\.