# Detailed Billing Report<a name="DetailedBillingReport"></a>

**Important**  
The Detailed Billing Report will be unavailable at a later date\. We strongly recommend that you use the [Cost and Usage Report](billing-reports-costusage.md) instead\.

Detailed billing reports are similar to AWS Cost and Usage reports\. They contain similar information about your charges, but calculate the individual line items differently\. If you sign up for both the detailed billing report and the AWS Cost and Usage reports, the line items will not match\. When the reports are finalized at the end of the month, the total cost should align\.

AWS stores the detailed billing reports in Amazon S3 as CSV files using the following naming convention:

```
AWS account number-aws-billing-detailed-line-items-yyyy-mm.csv.zip
```

AWS recreates the detailed billing report multiple times a day, overwriting the report\. When AWS overwrites a report, the line items might be in a different order than they were in the previous report\. At the end of the month, AWS creates a final report\. For the next month, AWS creates a new report file instead of overwriting the final report from the previous month\. Reports for previous months remain in your S3 bucket until you delete them\.