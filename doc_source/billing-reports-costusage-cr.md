# On\-Demand Capacity Reservations<a name="billing-reports-costusage-cr"></a>

Capacity Reservations enable you to reserve capacity for your Amazon EC2 instances for any duration in a specific Availability Zone\. This enables you to create and manage capacity reservations separately from the billing discounts offered by Regional Reserved Instances \(RIs\)\. To benefit from billing discounts, you can use Regional RIs in conjunction with Capacity Reservations\. 

## Capacity Reservation Line Items<a name="on-demand-capacity-reservation-lines"></a>

You can use some of the columns defined in the AWS Cost and Usage report data dictionary to track your Capacity Reservations\. You can use the following columns:

 **ResourceId**  
If you included resource IDs when you created your AWS Cost and Usage report, you can use the **ResourceId** column to identify and track your Capacity Reservations\.  
Capacity Reservations always have an `cr-` in their resource ID, and the resource ID has the following format:  

```
arn:aws:ec2:<region>:<account id>:<capacity-reservation>/cr-0be443example1db6f
```
The Capacity Reservation **ResourceId** is captured only for the **UnusedBox,** **UnusedDed**, **Reservation**, and **DedicatedRes** **UsageTypes**\.  
For more information about the **ResourceId**, see [](enhanced-lineitem-columns.md#ResourceId)\.

****UsageAmount****  
The **UsageAmount** column describes how much of a Capacity Reservation you used\. Each Capacity Reservation can have multiple slots for an hour, enabling you to run more than one instance that uses the reservation during an hour\. This mean that it's possible to use more than one instance\-hour in an hour\. **UsageAmount** is calculated by multiplying the number of instance slots covered by the line item with the number of hours covered by the line item\.  
For more information and examples about the **UsageAmount**, see [](#LR-UsageType)\.

**UsageType**  
The **UsageType** column shows how much of a specific reservation you used\. For Amazon EC2, the options are the following:    
 **Reservation**  
For a **UsageType** of **Reservation**, the **UsageAmount** column describes how many instance\-hours of a Capacity Reservation that you reserved\.  
For example, if a report covers one hour and has a Capacity Reservation line item that can cover ten instances, the **Reservation** **UsageAmount** covers the number of instance slots that you reserved\. In this case, that's 10 \(the number of available instance slots\) multiplied by 1 hour \(the time covered by the report\) for a total of 10\. For a report that covers 1 day, the **UsageAmount** would be 10 multiplied by 24, for a total of 240\.  
 **DedicatedRes**  
For a **UsageType** of **DedicatedRes**, the **UsageAmount** column describes how many instance\-hours of a dedicated Capacity Reservation that you reserved\.  
 **UnusedBox**  
 For a **UsageType** of **UnusedBox**, the **UsageAmount** column describes how many instance\-hours of a Capacity Reservation that you reserved but didn't use\.  
For example, suppose a report covers 1 hour and has a Capacity Reservation line item that can cover 10 instances\. If you didn't use eight instance\-slots during the time period covered by the report, the **UnusedBox** **UsageAmount** covers the number of instance hours that you reserved but didn't use\. In this case, that's eight \(the number of unused instance slots\) multiplied by 1 hour \(the time covered by the report\) for a total of eight\. For a report that covers 1 day, the **UsageAmount** is eight multiplied by 24, for a total of 192\.  
 **UnusedDed**  
 For a **UsageType** of **UnusedDed**, the **UsageAmount** column describes how many instance\-hours of a dedicated Capacity Reservation that you reserved but didn't use\.  
 **BoxUsage**  
For a **UsageType** of **BoxUsage**, the **UsageAmount** column describes how many instance\-hours of an instance that you used\.  
For example, suppose a report covers 1 hour and has a Capacity Reservation line item that can cover 10 instances\. If you use two instance\-slots during the time period covered by the report, the **BoxUsage** **UsageAmount** covers the number of instance hours that you reserved and used\. In this case, that's two \(the number of used instance slots\) multiplied by 1 hour \(the time covered by the report\) for a total of two\. For a report that covers 1 day, the **UsageAmount** is two multiplied by 24, for a total of 48\.
For more information about the **UsageType**, see [](enhanced-lineitem-columns.md#UsageType)\.

**UnblendedRate**  
For Capacity Reservations with a **UsageType** of **Reservation** or **DedicatedRes**, the **UnblendedRate** is `0`\. This is because the costs for the Capacity Reservation are associated with the instance that provides the capacity instead of with the Capacity Reservation itself\.   
For more information about the **UnblendedRate**, see [](enhanced-lineitem-columns.md#UnblendedRate)\.

**UnblendedCost**  
For Capacity Reservations with a **UsageType** of **Reservation** or **DedicatedRes**, the **UnblendedCost** is `0`\. This is because the costs for the Capacity Reservation are associated with the instance that provides the capacity instead of with the Capacity Reservation itself\.   
For more information about the **UnblendedCost**, see [](enhanced-lineitem-columns.md#UnblendedCost)\.

**BlendedRate**  
For Capacity Reservations with a **UsageType** of **Reservation** or **DedicatedRes**, the **BlendedRate** is `0`\. This is because the costs for the Capacity Reservation are associated with the instance that provides the capacity instead of with the Capacity Reservation itself\.   
For more information about the **BlendedRate**, see [](enhanced-lineitem-columns.md#BlendedRate)\.

**UnblendedCost**  
For Capacity Reservations with a **UsageType** of **Reservation** or **DedicatedRes**, the **UnblendedCost** is `0`\. This is because the costs for the Capacity Reservation are associated with the instance that provides the capacity instead of with the Capacity Reservation itself\.   
For more information about the **UnblendedCost**, see [](enhanced-lineitem-columns.md#UnblendedCost)\.