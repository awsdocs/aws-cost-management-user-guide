# Savings Plans<a name="billing-reports-costusage-sp"></a>

You can use AWS Cost and Usage Reports to track your Savings Plans utilization, charges, and allocations\.

## Savings Plans Line Items<a name="cur-sp-lineitems"></a>

Savings Plans is a flexible pricing model that offers low prices on Amazon EC2 and AWS Fargate, in exchange for a commitment to a consistent amount of usage \(measured in $/hour\) for a one\-year or three\-year term\.

The following line items in the AWS Cost and Usage Report help you track and manage your spend with Savings Plans\. 

**Upfront Fee**  
The **SavingsPlanUpfrontFee** line item is added to your bill when you purchase an `All Upfront` or `Partial Upfront` RI\. The following table shows how this one\-time fee appears in the AWS Cost and Usage report \(some columns were omitted for clarity\)\.  
     
**Table 1**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-costusage-sp.html)

 **Savings Plans Recurring Monthly Fee**  
The **SavingsPlanRecurringFee** line item describes the recurring hourly charges that correspond to `No Upfront` or `Partial Upfront` Savings Plans\. Initially, the **SavingsPlanRecurringFee** is added to your bill on the day of purchase and on the first day of each billing period thereafter\.  
The **SavingsPlanRecurringFee** allocated to the hour \(applicable to Hourly cost and usage\) or day \(applicable to Daily cost and usage\) is added to your bill at the hour of purchase\. It is added every hour/day of the billing period subsequently\.  
The following table shows how the recurring hourly charges appear in the report \(some columns were omitted for clarity\)\.  
     
**Table 2**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-costusage-sp.html)

**Savings Plans Discount Benefits**  
The **SavingsPlanCoveredUsage** line item describes the instance usage that received Savings Plans benefits\. A **SavingsPlanCoveredUsage** line item shows an unblended cost of what the On\-Demand charge would have been without the Savings Plan benefit\. This unblended cost is offset by the corresponding **SavingsPlanNegation** line item\.   
In each **SavingsPlanCoveredUsage** line item, you can see how that usage was billed against your Savings Plans hourly commitment by using the **savingsPlan/SavingsPlanRate** and **savingsPlan/SavingsPlanEffectiveCost** fields\.  
You'll see a corresponding **SavingsPlanNegation** for each **SavingsPlanCoveredUsage** line item\. **SavingsPlanNegation** line items offset the unblended cost of **SavingsPlanCoveredUsage**, and grouped at the hourly level by SavingsPlanARN, Operation, Usage Type, and Availability Zone\. Therefore, one **SavingsPlanNegation** line item may correspond to multiple **SavingsPlanCoveredUsage** line items\.  
The following table shows how the covered usage and the negation line items appear in the report \(some columns were omitted for clarity\)\.  
     
**Table 3**    
[\[See the AWS documentation website for more details\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports-costusage-sp.html)
When you have more usage than your Savings Plans commitment can cover, your uncovered usage will still appear as a Usage Line Item and the covered usage will appear as **SavingsPlanCoveredUsage** with the corresponding **SavingsPlanNegation** line items\.