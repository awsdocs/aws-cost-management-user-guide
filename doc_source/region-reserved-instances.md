# Region Reserved Instance Line Items<a name="region-reserved-instances"></a>

Amazon EC2 Reserved Instances \(RIs\) that apply to a region provide Availability Zone flexibility and instance size flexibility\. RIs that provide Availability Zone flexibility provide a discount on usage in any Availability Zone in the region\. RIs that provide instance size flexibility provide a discount on usage, regardless of instance size within that family\. To understand how instance size flexibility provided by your RI is applied to your usage, refer to the **lineItem/NormalizationFactor** and **lineItem/NormalizedUsageAmount** columns\.

**Note**  
Instance size flexibility is supported only by Linux/Unix Reserved Instances with default tenancy that are assigned to a region\. 

For example, let’s say that you purchase one `m4.xlarge` RI in a given region\. This `m4.xlarge` RI can be applied automatically to all `m4` instance usage in the same region\. In the following image, AWS applied the `m4.xlarge` to two separate `m4.large` instances\.

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The two `m4.large` usage line items have different **ResourceID**s, and both received a discount benefit from the single `m4.xlarge` RI\. This is shown by matching the **reservationARN** value across the usage and recurring monthly charge line items\.

The following screenshot shows an account that has subscriptions for two `m4.large` RIs, with one RI in each subscription\. In this example, the account uses a single instance of `m4.xlarge` for an hour and receives a separate discount benefit from each of the two `m4.large` RIs\. 

![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)![\[Image NOT FOUND\]](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/)

The single hour of `m4.xlarge` usage is split into two lines of 0\.5 hours \(both usage lines still retain the same **ResourceID**\) because different RI subscriptions were applied to each portion of that single hour\. The **reservationARN** for each 0\.5 hour matches the corresponding RI subscription\.

For more information about RI purchase options, see [ Billing Benefits and Payment Options](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts-reserved-instances-application.html#reserved-instances-payment-options) in the *Amazon EC2 User Guide for Linux Instances*\.