# Reservation Details<a name="enhanced-reservation-columns"></a>

You can use the reservation columns to find out more about a reserved resource\. The columns include but are not limited to the following:

** reservation/AmortizedUpfrontCostForUsage**  
The initial upfront payment for All Upfront RIs and Partial Upfront RIs amortized for usage time\. Because there are no upfront payments for No Upfront RIs, the value for a No Upfront RI is `0`\.

** reservation/AmortizedUpfrontFeeForBillingPeriod**  
The initial upfront payment for All Upfront RIs and Partial Upfront RIs, amortized over this month\. Because there are no upfront fees for No Upfront RIs, the value for No Upfront RIs is `0`\.  
This tells you how much the upfront fee for this reservation costs you for this billing period\. 

** reservation/AvailabilityZone**  
The Availability Zone of the resource that is associated with this line item\.

** reservation/EffectiveCost**  
The total effective cost of your usage with RI rates applied\. This is calculated by taking the `amortizedUpfrontCostForUsage` and adding it to the `recurringFeeForUsage`\.

** reservation/NormalizedUnitsPerReservation**  
The number of normalized units for each instance of a reservation subscription\.

**reservation/NumberOfReservations**  
The number of reservations that are covered by this subscription\. For example, one RI subscription might have four associated RI reservations\.

** reservation/RecurringFeeForUsage**  
For Partial Upfront RIs and No Upfront RIs, this is the recurring fee amortized for usage time\. Because All Upfront RIs don't have recurring fee payments greater than `0`, the value for All Upfront RIs is `0`\.

** reservation/ReservationARN**  
The Amazon Resource Name \(ARN\) of the RI that this line item benefited from\.

** reservation/SubscriptionId**  
A unique ID that provides additional information about your RI leases\. You should use the reservation ARN as your primary RI identifier\.

** reservation/TotalReservedNormalizedUnits**  
The total number of reserved normalized units for all instances for a reservation subscription\. AWS computes total normalized units by multiplying the `reservation/NormalizedUnitsPerReservation` by the `reservation/NumberOfReservations`\.

** reservation/TotalReservedUnits**  
The total number of reserved units in a subscription\. For an RI, this is the total number of hours across all RIs in this subscription\. This is calculated by multiplying the `NumberOfReservations` by the `UnitsPerReservation`\.

** reservation/UnitsPerReservation**  
The number of usage units reserved by a single reservation in a given subscription, such as how many hours a single Amazon EC2 RI has reserved\.

** reservation/UnusedAmortizedUpfrontFeeForBillingPeriod**  
The amortized portion of the initial upfront fee for All Upfront RIs and Partial Upfront RIs\. Because there are no upfront payments for No Upfront RIs, the value for No Upfront RIs is `0`\.

** reservation/UnusedNormalizedUnitQuantity**  
The number of unused normalized units for a size\-flexible regional RI that you didn't use during this billing period\.

** reservation/UnusedQuantity**  
The number of RI hours that you didn't use during this billing period\.

** reservation/UnusedRecurringFee**  
The recurring fees associated with your unused reservation hours for Partial Upfront and No Upfront RIs\.  
Because All Upfront RIs don't have recurring fees greater than `0`, the value for All Upfront RIs is `0`\.