# Changes to the Detailed Billing Reports<a name="detailed-billing-report-changes"></a>

On June 17, 2019, AWS changed the way unused Reserved Instance \(“RI”\) costs are presented in Detailed Billing Report \(DBR\) and Detailed Billing Report with Resources and Tags \(DBR\-RT\)\. If you are utilizing the DBR and DBR\-RT to understand the used and unused portions of your Reserved Instance \(RI\) costs, then please continue reading\. If not, this change does not impact you\. 

Prior to June 17, 2019, in DBR/DBR\-RT, the cost of the recurring monthly RI fees \(RI Fee line items\) are allocated to applicable instance usage line items, and RI\-related fields are transformed to present unused usage and associated costs\. Starting on June 17, 2019, this functionality was discontinued in the DBR and DBR\-RT\. 

The Cost and Usage Report provides the most comprehensive set of data regarding your AWS cost and usage, including additional metadata about AWS services, pricing, and reservations\. This allows you to understand individual costs in depth and analyze them in greater detail\. When allocating RI costs, the CUR provides the following benefits in comparison to DBR and DBR\-RT reports:
+ **Easier RI cost allocation** — Simplifies RI cost allocation by distributing one\-time reservation costs across the term of the lease\. 
+ **Simplified data ingestion** — Eliminates unnecessary data transforms during data ingestion for tracking the cost and usage associated with the monthly unused portion of RIs\.

Additionally, with the Cost and Usage Report, customers can gain additional reservation\-related insights beyond unused RI costs, such as the Amazon Resource Name \(ARN\) for a reservation, the number of reservations, calculated savings, the allocation of RI discounts, and more\. 

Please note that the DBR and DBR\-RT reports will continue to provide accurate information regarding up\-front and recurring RI costs, as well as the costs associated with on\-demand usage covered by RIs\.

The remainder of this document will provide more detail regarding the change by providing 1\) a brief glossary of terms, 2\) a summary of changes in in the DBR and DBR\-RT, and 3\) a detailed walk through of four most common RI\-usage use cases which illustrate how same information is presented in Cost and Usage Report\. 

## Glossary<a name="dbr-glossary"></a>

The following concepts will aid in understanding the changes to the DBR, and how the enhanced functionality of the Cost and Usage Report can be leveraged for understanding unused RI costs\. 
+ **Line Item Types** — Indicates the type of charge covered by a line item in the DBR/DBR\-RT or CUR\.
  + **Fee** — Any upfront annual fee that you paid for reserved instance subscriptions\. For example, the upfront fee that you paid for an All Upfront RI or a Partial Upfront RI\. 
  + **RI Fee** — The monthly recurring fee for reserved instance subscriptions\. For example, the recurring fee for Partial Upfront RIs, No Upfront RIs, and All Upfront RIs that you pay every month\.
  + **Discounted Usage** — The rate for any instances which you received a Reserved Instance \(RI\) discount\.
+ **Track unused RI costs** — Unused RI hours and cost in the DBR and DBR\-RT are captured in the fields UsageQuantity and UnblendedCost for the RI Fee line item\.

## Before and After: Changes to the presentation of unused RI costs \(DBR/DBR\-RT\)<a name="dbr-before-after"></a>

Discounted Usage line items are transformed and replaced with the information from the RI Fee line items to provide visibility into unused RI cost and usage\. Additionally, the UnblendedRate and UnblendedCost fields are updated to reflect the portion of the RI Fee allocated based on the discount received by the Discounted Usage line item\. 

Table 1 below shows how a DBR or DBR\-RT, prior to June 17, 2019, presents data for a partially utilized RI \(i\.e\. when the RI Fee line item had unused usage and associated costs\) and the cells in grey show the fields transformed by monthly recurring RI fee allocation\. After June 17, 2019, the DBR/DBR\-RT transformations that allocate the cost of RI Fee line items to applicable instance usage line items has been discontinued in favor of existing functionality in the CUR\. Table 12below shows how a DBR or DBR\-RT will present data for a partially utilized RI \(i\.e\. when RI Fee line item had unused cost and usage\) once the transformations are discontinued\. The highlighted text denotes the changes\.

**Table 1 – DBR and DBR\-RT Prior to June 17, 2019**


| ProductName | UsageType | Operation | Availability Zone | Reserved Instance | ItemDescription | Usage Quantity | Unblended Rate | Unblended Cost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge \(744 hours purchased, 644 hours used\) | 100 | 0\.1 | 10 | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 644 | 0\.1 | 64\.4 | 

**Table 2 \- DBR and DBR\-RT after June 17, 2019**


| ProductName | UsageType | Operation | Availability Zone | Reserved Instance | ItemDescription | Usage Quantity | Unblended Rate | Unblended Cost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 0\.1 | 74\.4 | 
|  Amazon Elastic Compute Cloud  | USE1\-BoxUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 644 | 0 | 0 | 

## Understanding unused RI costs via the CUR<a name="dbr-unused-ri-via-cur"></a>

To illustrate the how the CUR can be leveraged to better understand unused RI costs, let’s review the following four scenarios\.

### Scenario 1: RI is completely utilized<a name="scenario-1"></a>

RI Fee line item has $0 unused cost and 0 usage hours\.

Utilizing the DBR/DBR\-RT, you can understand your unused RI usage and costs by referring to the fields UsageQuantity and UnblendedCosts for RI Fee line items\. RI Fee line items can be identified by the existence of ‘purchased hours’ information in the ItemDescription field\. Table 3 below illustrates the columns and information utilized to manage unused RI costs in the DBR and DBR\-RT report\.

**Table 3 – Unused RI costs for a 100% utilized RI in DBR and DBR\-RT prior to June 17, 2019**


| ProductName | UsageType | Operation | Availability Zone | Reserved Instance | ItemDescription | Usage Quantity | Unblended Rate | Unblended Cost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge \(744 hours purchased, 744 hours used\) | 0 | 0\.1 | 0 | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 0\.1 | 74\.4 | 

Utilizing the CUR, you can understand your unused RI usage and costs by referring to the fields ‘reservation/ UnusedQuantity’ and ‘reservation/ UnusedRecurringFee’ for RI Fee line items\. Table 4 below illustrates the current columns and information utilized to manage unused RI costs in the CUR\.

**Table 4 – Unused RI costs for a 100% utilized RI in Cost and Usage Reports**


| lineitem/ Productcode | UsageType | lineitem/ LineItemType | lineitem/ LineItemDescription | lineitem/ UsageAmount | lineitem/ NormalizedUsageAmount | lineitem/ UnblendedRate | lineitem/ UnblendedCost | reservation/ UnusedQuantity | reservation/ UnusedRecurringFee | reservation/ UnusedAmortizedUpfrontFeeForBillingPeriod | reservation/ RecurringFeeForUsage | reservation/ AmortizedUpfrontCostForUsage | reservation/ EffectiveCost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon EC2  | HeavyUsage:c3\.8xlarge | RI Fee | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 47,616 | 0\.1 | 74\.4 | 0 | 0 | 0 |  |  |  | 
|  Amazon EC2  | USW2\-BoxUsage:c3\.8xlarge | DiscountedUsage | USD 0\.00 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 47,616 | 0 | 0 |  |  |  | 74\.4 | 5 | 79\.4 | 

In addition to matching the current functionality supported by DBR/DBR\-RT, CUR has the following advantages:
+ Using the CUR, you are able to access information regarding the EffectiveCost for the DiscountedUsage line item, which includes both the recurring and upfront fees\. The DBR only accounts for recurring fees\.
+ In the CUR, the UsageType field is not transformed for the DiscountedUsage line items whereas DBR replaces the information with RI Fee line item information\. This is because the user can group line items in the CUR by ReservationARN in order to understand what usage was discounted by which RI\.
+ In CUR, the LineItemDescription field is not transformed for the RI Fee line item; whereas, DBR appends the hours purchased and hours used

### Scenario 2: RI is partially utilized<a name="scenario-2"></a>

RI Fee line item has unused cost and usage\.

Utilizing the DBR/DBR\-RT, you can understand your unused RI usage and costs by referring to fields UsageQuantity and UnblendedCosts for RI Fee line items\. Table 5 below illustrates the columns and information utilized to manage unused RI costs in the DBR and DBR\-RT report\.

**Table 5 – Unused RI costs for a partially utilized RI in DBR and DBR\-RT prior to June 17, 2019**


| ProductName | UsageType | Operation | Availability Zone | Reserved Instance | ItemDescription | Usage Quantity | Unblended Rate | Unblended Cost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge \(744 hours purchased, 644 hours used\) | 100 | 0\.1 | 10 | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 644 | 0\.1 | 64\.4 | 

Utilizing the CUR, you can understand your unused RI usage and costs by referring to fields ‘reservation/ UnusedQuantity’ and ‘reservation/ UnusedRecurringFee’ for RI Fee line items\. Table 6 below illustrates the current columns and information utilized to manage unused RI costs in the CUR\.

**Table 6 – Unused RI costs for a partially utilized RI in Cost and Usage Reports**


| lineitem/ Productcode | UsageType | lineitem/ LineItemType | lineitem/ LineItemDescription | lineitem/ UsageAmount | lineitem/ NormalizedUsageAmount | lineitem/ UnblendedRate | lineitem/ UnblendedCost | reservation/ UnusedQuantity | reservation/ UnusedRecurringFee | reservation/ UnusedAmortizedUpfrontFeeForBillingPeriod | reservation/ RecurringFeeForUsage | reservation/ AmortizedUpfrontCostForUsage | reservation/ EffectiveCost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon EC2  | HeavyUsage:c3\.8xlarge | RI Fee | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 47,616 | 0\.1 | 74\.4 | 100 | 0 | 1 |  |  |  | 
|  Amazon EC2  | USW2\-BoxUsage:c3\.8xlarge | DiscountedUsage | USD 0\.00 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 644 | 47,216 | 0 | 0 |  |  |  | 64\.4 | 5 | 69\.4 | 

In addition to matching the current functionality supported by DBR/DBR\-RT, CUR has the following advantages:
+ CUR has a separate column representing UnusedQuantity for the RI Fee line item vs\. DBR / DBR\-RT which overloads the UsageQuantity column with the unused hours 

### Scenario 3: Capacity Reservation<a name="scenario-3"></a>

DBR/DBR\-RT filters out Capacity Reservation related UnusedBox and UnusedDed usage type line items when covered by an RI because the RI Fee line item already covers the unused amount in the UsageQuantity and UnblendedCost fields\. Table 7 below illustrates the columns and information utilized to manage unused RI costs in the DBR and DBR\-RT report\.

**Table 7 – Unused RI costs for capacity reservation scenario in DBR and DBR\-RT prior to June 17 2019**


| ProductName | UsageType | Operation | Availability Zone | Reserved Instance | ItemDescription | Usage Quantity | Unblended Rate | Unblended Cost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge \(744 hours purchased, 734 hours used\) | 10 | 0\.1 | 1 | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 734 | 0\.1 | 73\.4 | 

The CUR shows these line items as DiscountedUsage\. Table 8 below illustrates the current columns and information utilized to manage unused RI costs in the CUR\.

**Table 8 – Unused RI costs for a capacity reservation scenario in Cost and Usage Reports**


| lineitem/ Productcode | UsageType | lineitem/ LineItemType | lineitem/ LineItemDescription | lineitem/ UsageAmount | lineitem/ NormalizedUsageAmount | lineitem/ UnblendedRate | lineitem/ UnblendedCost | reservation/ RecurringFeeForUsage | reservation/ AmortizedUpfrontCostForUsage | reservation/ EffectiveCost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon EC2  | HeavyUsage:c3\.8xlarge | RI Fee | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 47,616 | 0\.1 | 74\.4 |  |  |  | 
|  Amazon EC2  | USW2\-Reservation:c3\.8xlarge | Usage | USD 0\.00 per Reservation Linux/UNIX \(Amazon VPC\), c3:8xlarge Instance Hour | 744 |  | 0 | 0 |  |  |  | 
| Amazon EC2 | USW2\-BoxUsage:c3\.8xlarge | DiscountedUsage | USD 0\.00 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 644 | 47,216 | 0 | 0 | 64\.4 | 5 | 69\.4 | 
| Amazon EC2 | USW2\-UnusedBox:c3\.8xlarge | DiscountedUsage | USD 0\.0058 used Reservation Linux/UNIX \(Amazon VPC\), c3:8xlarge Instance Hour | 100 | 6,500 | 0 | 0 | 10 | 1 | 11 | 

### Scenario 4: Size Flexible Reservations<a name="scenario-4"></a>

Utilizing the DBR/DBR\-RT, you can understand your unused RI usage and costs by referring to fields UsageQuantity and UnblendedCosts for RI Fee line items\. RI Fee line items can be identified by the existence of ‘purchased hours’ information in the ItemDescription field\. Table 9 below illustrates the columns and information utilized to manage unused RI costs in the DBR and DBR\-RT report\.

**Table 9 – Unused RI costs for a size flex RI scenario in DBR and DBR\-RT prior to June 17, 2019**


| ProductName | UsageType | Operation | Availability Zone | Reserved Instance | ItemDescription | Usage Quantity | Unblended Rate | Unblended Cost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge \(744 hours purchased, 644 hours used\) | 100 | 0\.1 | 10 | 
|  Amazon Elastic Compute Cloud  | HeavyUsage:c3\.8xlarge | RunInstances | us\-east\-1a | Y | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge; UsageType: BoxUsage:c3\.large | 644 | 0\.1 | 64\.4 | 

Utilizing CUR, you can understand your unused RI usage and costs by referring to fields ‘reservation/ UnusedQuantity’ and ‘reservation/ UnusedRecurringFee’ for RI Fee line items\. Table 10 below illustrates the current columns and information utilized to manage unused RI costs in the CUR\.

**Table 10 – Unused RI costs for a size flex RI scenario in Cost and Usage Reports**


| lineitem/ Productcode | UsageType | lineitem/ LineItemType | lineitem/ LineItemDescription | lineitem/ UsageAmount | lineitem/ NormalizedUsageAmount | lineitem/ UnblendedRate | lineitem/ UnblendedCost | reservation/ UnusedQuantity | reservation/ UnusedRecurringFee | reservation/ UnusedAmortizedUpfrontFeeForBillingPeriod | reservation/ RecurringFeeForUsage | reservation/ AmortizedUpfrontCostForUsage | reservation/ EffectiveCost | 
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | 
|  Amazon EC2  | HeavyUsage:c3\.8xlarge | RI Fee | USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge | 744 | 47,616 | 0\.1 | 74\.4 | 100 | 70\.37 | 5\.5 |  |  |  | 
|  Amazon EC2  | USW2\-BoxUsage:c3\.8xlarge | DiscountedUsage | USD 0\.00 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8large | 644 | 2,576 | 0 | 0 |  |  |  | 4\.03 | 0\.5 | 4\.53 | 

In addition to matching the current functionality supported by DBR/DBR\-RT, CUR has the following advantages:
+ CUR has the NormalizedUsageAmount and quantity\. The DBR / DBR\-RT do not have columns representing this\.
+ CUR UsageType and Operation are not transformed for the DiscountedUsage lineitem\. The DBR / DBR\-RT replaces these values with the RI Fee line item\.
+ CUR LineItemDescription is not transformed for the DiscountedUsage line item\. In DBR / DBR\-RT, which replaces with the RI Fee line item description and appends the DiscountedUsage line item Usage Type to the end of the string i\.e\. “USD 0\.10 hourly fee per Linux/UNIX \(Amazon VPC\), c3:8xlarge; UsageType: BoxUsage:c3\.large”