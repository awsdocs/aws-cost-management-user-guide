# Reservation Details<a name="enhanced-reservation-columns"></a>

The reservation columns provide details about reserved resources\.

## Downloading a Reservation Column Spreadsheet<a name="download-reservation"></a>

The following list is a subset of reservation columns and the corresponding definitions\. To download the full list of the columns that can appear in the Cost and Usage Report and the services that the columns apply to, choose [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\.

 [A](#r-A) \| B \| C \| D \| [E](#r-E) \| F \| G \| H \| I \| J \| K \| L \| [M](#r-M) \| [N](#r-N) \| O \| P \| Q \| [R](#r-R) \| [S](#r-S) \| [T](#r-T) \| [U](#r-U) \| VWXYZ 

## A<a name="reservation-details-A"></a>

### reservation/AmortizedUpfrontCostForUsage<a name="reservation-details-A-AmortizedUpfrontCostForUsage"></a>
+ **Description:** The initial upfront payment for All Upfront RIs and Partial Upfront RIs amortized for usage time\. Because there are no upfront payments for No Upfront RIs, the value for a No Upfront RI is `0`\.
+ **Line items applicable:** DiscountedUsage
+ **Sample values:** `0.05`, `0.17`, `0.15`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/AmortizedUpfrontFeeForBillingPeriod<a name="reservation-details-A-AmortizedUpfrontFeeForBillingPeriod"></a>
+ **Description:** Describes how much of the upfront fee for this reservation is costing you for the billing period\. The initial upfront payment for All Upfront RIs and Partial Upfront RIs, amortized over this month\. Because there are no upfront fees for No Upfront RIs, the value for No Upfront RIs is `0`\.
+ **Line items applicable:** RIFee
+ **Sample values:** `29.15`, `200.67`, `214.43`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/AvailabilityZone<a name="reservation-details-A-AvailabilityZone"></a>
+ **Description:** The availability zone of the resource that is associated with this line item\.
+ **Line items applicable:** Fee, Refund, RIFee
+ **Sample values:** `us-east-1`, `us-east-1b`, `eu-west-1b`, `ap-southeast-2a`
+ **Services:**
  + Amazon EC2

## E<a name="reservation-details-E"></a>

### reservation/EffectiveCost<a name="reservation-details-E-EffectiveCost"></a>
+ **Description:** The sum of both the upfront and hourly rate of your RI, averaged into an effective hourly rate\. `EffectiveCost` is calculated by taking the `amortizedUpfrontCostForUsage` and adding it to the `recurringFeeForUsage`\. For more information, see [Amazon EC2 Reserved Instances Pricing](https://aws.amazon.com/ec2/pricing/reserved-instances/pricing/)\.
+ **Line items applicable:** DiscountedUsage
+ **Sample values:** `0.23`, `0.68`, `0.10`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon ElastiCache
  + Amazon RDS

### reservation/EndTime<a name="reservation-details-E-EndTime"></a>
+ **Description:** The end date of the associated RI lease term\.
+ **Line items applicable:** RIFee
+ **Sample values:** `2019-05-15T04:23:14.000Z`, `2020-02-08T17:32:15.000Z`, `2019-07-14T00:00:33.000Z`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

## M<a name="reservation-details-M"></a>

### reservation/ModificationStatus<a name="reservation-details-M-ModificationStatus"></a>
+ **Description:** Shows whether the RI lease was modified or if it is unaltered\.
  + **Original:** The purchased RI was never modified\.
  + **System:** The purchased RI was modified using the console or API\.
  + **Manual:** The purchased RI was modified using AWS Support assistance\.
  + **ManualWithData:** The purchased RI was modified using AWS Support assistance, and AWS calculated estimates for the RI\.
+ **Line items applicable:** RIFee
+ **Sample values:** `Original`, `System`, `Manual`, `ManualWithData`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

## N<a name="reservation-details-N"></a>

### reservation/NormalizedUnitsPerReservation<a name="reservation-details-N-NormalizedUnitsPerReservation"></a>
+ **Description:** The number of normalized units for each instance of a reservation subscription\.
+ **Line items applicable:** RIFee
+ **Sample values:** `1316`, `54.5`, `319`
+ **Services:**
  + Amazon RDS

### reservation/NumberOfReservations<a name="reservation-details-N-NumberOfReservations"></a>
+ **Description:** The number of reservations that are covered by this subscription\. For example, one RI subscription might have four associated RI reservations\.
+ **Line items applicable:** Fee, RIFee, Refund, Credit
+ **Sample values:** `5`, `50`, `500`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

## R<a name="reservation-details-R"></a>

### reservation/RecurringFeeForUsage<a name="reservation-details-R-RecurringFeeForUsage"></a>
+ **Description:** The recurring fee amortized for usage time, for Partial Upfront RIs and No Upfront RIs\. Because All Upfront RIs don't have recurring fee payments greater than `0`, the value for All Upfront RIs is `0`\.
+ **Line items applicable:** DiscountedUsage
+ **Sample values:** `0.139`, `0.729`, `0.018`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon ElastiCache
  + Amazon RDS

### reservation/ReservationARN<a name="reservation-details-R-ReservationARN"></a>
+ **Description:** The Amazon Resource Name \(ARN\) of the RI that this line item benefited from\. This is also called the "RI Lease ID"\. This is a unique identifier of this particular AWS Reserved Instance\. The value string also contains the AWS service name and the Region where the RI was purchased\.
+ **Line items applicable:** Fee, RIFee, DiscountedUsage, Refund, Credit
+ **Sample values:** `arn:aws:ec2:us-east-1:074108124787:reserved-instances/1d3fbc13-f181-4c40-9dd6-12b345678de9`, `arn:aws:ec2:us-east-1:499958231354:reserved-instances/be41234c3-b5c0-403e-a80c-1cfd12345678`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

## S<a name="reservation-details-S"></a>

### reservation/StartTime<a name="reservation-details-S-StartTime"></a>
+ **Description:** The start date of the term of the associated Reserved Instance\.
+ **Line items applicable:** RIFee
+ **Sample values:** `2018-07-29T02:56:10.000Z`, `2017-08-21T15:58:47.000Z`, `2019-02-01T22:01:34.000Z`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/SubscriptionId<a name="reservation-details-S-SubscriptionId"></a>
+ **Description:** A unique identifier that maps a line item with the associated offer\. We recommend you use the RI ARN as your identifier of an AWS Reserved Instance, but both can be used\.
+ **Line items applicable:** Fee, RIFee, DiscountedUsage, Refund, Credit and Usage
+ **Sample values:** `123456789`, `111122222`, `333344444`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

## T<a name="reservation-details-T"></a>

### reservation/TotalReservedNormalizedUnits<a name="reservation-details-T-TotalReservedNormalizedUnits"></a>
+ **Description:** The total number of reserved normalized units for all instances for a reservation subscription\. AWS computes total normalized units by multiplying the `reservation/NormalizedUnitsPerReservation` with `reservation/NumberOfReservations`\.
+ **Line items applicable:** DiscountedUsage
+ **Sample values:** `40320`, `3647.99`, `17928.77`
+ **Services:**
  + Amazon EC2
  + Amazon RDS

### reservation/TotalReservedUnits<a name="reservation-details-T-TotalReservedUnits"></a>
+ **Description:** `TotalReservedUnits` populates for both Fee and RIFee line items with distinct values\.
  + Fee line items: The total number of units reserved, for the total quantity of leases purchased in your subscription for the entire term\. 

    This is calculated by multiplying the `NumberOfReservations` with `UnitsPerReservation`\. For example, 5 RIs x 744 hours per month x 12 months = 44,640\.
  + RIFee line items \(monthly recurring costs\): The total number of available units in your subscription, such as the total number of Amazon EC2 hours in a specific RI subscription\.

    For example, 5 RIs x 744 hours = 3,720\.
+ **Line items applicable:** Fee, RIFee, Refund, Credit
+ **Sample values:** `26208`, `98.19`, `15796`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

## U<a name="reservation-details-U"></a>

### reservation/UnitsPerReservation<a name="reservation-details-U-UnitsPerReservation"></a>
+ **Description:** `UnitsPerReservation` populates for both Fee and RIFee line items with distinct values\.
  + Fee line items: The total number of units reserved for the subscription, such as the total number of RI hours purchased for the term of the subscription\. 

    For example 744 hours per month x 12 months = 8,928 total hours/units\.
  + RIFee line items \(monthly recurring costs\): The total number of available units in your subscription, such as the total number of Amazon EC2 hours in a specific RI subscription\.

    For example, 1 unit x 744 hours = 744\.
+ **Line items applicable:** Fee, RIFee, Refund, Credit
+ **Sample values:** `334.0`, `486.72`, `18455`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon DynamoDB
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/UnusedAmortizedUpfrontFeeForBillingPeriod<a name="reservation-details-U-UnusedAmortizedUpfrontFeeForBillingPeriod"></a>
+ **Description:** The amortized\-upfront\-fee\-for\-billing\-period\-column amortized portion of the initial upfront fee for All Upfront RIs and Partial Upfront RIs\. Because there are no upfront payments for No Upfront RIs, the value for No Upfront RIs is `0`\.
+ **Line items applicable:** RIFee
+ **Sample values:** `6.05`, `1.97`, `0.17`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/UnusedNormalizedUnitQuantity<a name="reservation-details-U-UnusedNormalizedUnitQuantity"></a>
+ **Description:** The number of unused normalized units for a size\-flexible regional RI that you didn't use during this billing period\.
+ **Line items applicable:** RIFee
+ **Sample values:** `25.00`, `3.50`, `274.33`
+ **Services:**
  + Amazon RDS

### reservation/UnusedQuantity<a name="reservation-details-U-UnusedQuantity"></a>
+ **Description:** The number of RI hours that you didn't use during this billing period\.
+ **Line items applicable:** RIFee line item
+ **Sample values:** `209.65110408`, `191.00000000`, `176.00000000`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/UnusedRecurringFee<a name="reservation-details-U-UnusedRecurringFee"></a>
+ **Description:** The recurring fees associated with your unused reservation hours for Partial Upfront and No Upfront RIs\. Because All Upfront RIs don't have recurring fees greater than `0`, the value for All Upfront RIs is `0`\.
+ **Line items applicable:** RIFee
+ **Sample values:** `0.02971114`, `0.19190000`, `1.37280000`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS

### reservation/UpfrontValue<a name="reservation-details-U-UpfrontValue"></a>
+ **Description:** The upfront price paid for your AWS Reserved Instance\. For No Upfront RIs, this value is `0`\.
+ **Line items applicable:** RIFee
+ **Sample values:** `150.00`, `1000.00`, `2000.00`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon Redshift
  + Amazon ElastiCache
  + Amazon RDS