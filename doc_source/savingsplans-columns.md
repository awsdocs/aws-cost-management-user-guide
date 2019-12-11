# Savings Plans Details<a name="savingsplans-columns"></a>

The SavingsPlan columns provide details about the ComputeSavingsPlans\. SavingsPlan columns are visible if you have purchased Savings Plans\. For more information about Savings Plans, see [What are Savings Plans?](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html) in the *Savings Plans User Guide*\.

 [A](#sp-A) \| B \| C \| D \| [E](#sp-E) \| F \| G \| H \| [I](#sp-I) \| J \| K \| L \| M \| N \| [O](#sp-O) \| [P](#sp-P) \| Q \| [R](#sp-R) \| [S](#sp-S) \| [T](#sp-T) \| [U](#sp-U) \| VWXYZ 

## A<a name="savingsplans-details-A"></a>

### savingsPlan/AmortizedUpfrontCommitmentForBillingPeriod<a name="savingsplans-details-A-AmortizedUpfrontCommitmentForBillingPeriod"></a>
+ **Description:** The amount of upfront fee a Savings Plan subscription is costing you for the billing period\. The initial upfront payment for **All Upfront Savings Plan** and **Partial Upfront Savings Plan** amortized over the current month\. For **No Upfront Savings Plan**, the value is 0\.
+ **Line items applicable:** SavingsPlanRecurringFee
+ **Services:**
  + Amazon EC2
  + Fargate

## E<a name="savingsplans-details-E"></a>

### savingsPlan/EndTime<a name="savingsplans-details-E-EndTime"></a>
+ **Description:** The expiration date for the Savings Plan agreement\.
+ **Line items applicable:** SavingsPlanUpfrontFee
+ **Services:**
  + Amazon EC2
  + Fargate

## I<a name="savingsplans-details-I"></a>

### savingsPlan/InstanceTypeFamily<a name="savingsplans-details-I-InstanceTypeFamily"></a>
+ **Description:** The instance family that is associated with the specified usage\.
+ **Line items applicable:** Usage
+ **Sample values:** `m4`, `g2`
+ **Services:**
  + Amazon EC2
  + Fargate

## O<a name="savingsplans-details-O"></a>

### savingsPlan/OfferingType<a name="savingsplans-details-O-OfferingType"></a>
+ **Description:** Describes the type of Savings Plan purchased\.
+ **Line items applicable:** SavingsPlanUpfrontFee
+ **Sample values:** `ComputeSavingsPlan`, `EC2InstanceSavingsPlan`
+ **Services:**
  + Amazon EC2
  + Fargate

## P<a name="savingsplans-details-P"></a>

### savingsPlan/PaymentOption<a name="savingsplans-details-P-PaymentOption"></a>
+ **Description:** The payment options available for your Savings Plan\.
+ **Line items applicable:** SavingsPlanUpfrontFee
+ **Sample values:** `PartialUpfront`, `AllUpfront`, `NoUpfront`
+ **Services:**
  + Amazon EC2
  + Fargate

### savingsPlan/PurchaseTerm<a name="savingsplans-details-P-PurchaseTerm"></a>
+ **Description:** Describes the duration, or term, of the Savings Plan\.
+ **Line items applicable:** SavingsPlanUpfrontFee
+ **Sample values:** `1yr`, `3yr`
+ **Services:**
  + Amazon EC2
  + Fargate

## R<a name="savingsplans-details-R"></a>

### savingsPlan/RecurringCommitmentForBillingPeriod<a name="savingsplans-details-R-RecurringCommitmentForBillingPeriod"></a>
+ **Description:** The monthly recurring fee for your Savings Plan subscriptions\. For example, the recurring monthly fee for a **Partial Upfront Savings Plan** or **No Upfront Savings Plan**\.
+ **Line items applicable:** SavingsPlanRecurringFee
+ **Services:**
  + Amazon EC2
  + Fargate

### savingsPlan/Region<a name="savingsplans-details-R-Region"></a>
+ **Description:** The AWS Region \(geographic area\) that hosts your AWS services\. You can use this field to analyze spend across a particular AWS Region\.
+ **Line items applicable:** Usage, SavingsPlanUpfrontFee
+ **Sample values:** `eu-west-3`, `us-west-1`, `us-east-1`, `ap-northeast-2`, `sa-east-1`
+ **Services:**
  + Amazon EC2
  + Fargate

## S<a name="savingsplans-details-S"></a>

### savingsPlan/SavingsPlanArn<a name="savingsplans-details-S-SavingsPlanARN"></a>
+ **Description:** The unique Savings Plan identifier\.
+ **Line items applicable:** SavingsPlanUpfrontFee
+ **Services:**
  + Amazon EC2
  + Fargate

### savingsPlan/SavingsPlanEffectiveCost<a name="reservation-details-S-SavingsPlanEffectiveCost"></a>
+ **Description:** The proportion of the Savings Plan monthly commitment amount \(Upfront and recurring\) that is allocated to each usage line\.
+ **Line items applicable:** Usage
+ **Services:**
  + Amazon EC2
  + Fargate

### savingsPlan/SavingsPlanRate<a name="savingsplans-details-S-SavingsPlanRate"></a>
+ **Description:** The Savings Plan rate for the usage\.
+ **Line items applicable:** Usage
+ **Services:**
  + Amazon EC2
  + Fargate

### savingsPlan/StartTime<a name="savingsplans-details-S-StartTime"></a>
+ **Description:** The start date of the Savings Plan agreement\.
+ **Line items applicable:** SavingsPlanUpfrontFee
+ **Services:**
  + Amazon EC2
  + Fargate

## T<a name="savingsplans-details-T"></a>

### savingsPlan/TotalCommitmentToDate<a name="savingsplans-details-T-TotalCommitmenToDate"></a>
+ **Description:** The total amortized upfront commitment and recurring commitment to date, for that hour\.
+ **Line items applicable:** SavingsPlanRecurringFee
+ **Services:**
  + Amazon EC2
  + Fargate

## U<a name="savingsplans-details-U"></a>

### savingsPlan/UsedCommitment<a name="savingsplans-details-U-UsedCommitment"></a>
+ **Description:** The total dollar amount of the Savings Plan commitment used\. \(SavingsPlanRate multiplied by usage\)
+ **Line items applicable:** Usage
+ **Services:**
  + Amazon EC2
  + Fargate