# Reservation Details<a name="enhanced-reservation-columns"></a>

You can use the reservation columns to find out more about a reserved resource\. The columns include but are not limited to the following:

** reservation/AvailabilityZone**  
The Availability Zone of the resource that is associated with this line item\.

** reservation/NumberOfReservations**  
The number of reservations that are covered by this subscription\. For example, one Reserved Instance \(RI\) subscription might have four associated RI reservations\.

** reservation/ReservationARN**  
The ARN of the Reserved Instance \(RI\) that this line item benefited from\.

** reservation/TotalReservedUnits**  
The total number of reserved units in the subscription\. In the case of a Reserved Instance \(RI\), this is the total number of hours across all RIs in this subscription\. This is calculated by multiplying the `NumberOfReservations` by the `UnitsPerReservation.`

** reservation/UnitsPerReservation**  
The number of usage units reserved by a single reservation in a given subscription, such as how many hours a single Amazon EC2 RI has reserved\.