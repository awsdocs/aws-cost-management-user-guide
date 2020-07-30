# User\-Defined Tag Restrictions<a name="allocation-tag-restrictions"></a>

For basic tag restrictions, see [Tag Restrictions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html#tag-restrictions) in the Amazon EC2 User Guide\.

The following restrictions apply to user\-defined tags for Cost Allocation:
+ The reserved prefix is `aws:`\.

  AWS generated tag names and values are automatically assigned the `aws:` prefix, which you can't assign\. User\-defined tag names have the prefix `user:` in the cost allocation report\.
+ Use each key only once for each resource\. If you attempt to use the same key twice on the same resource, your request will be rejected\.
+ In some services, you can tag a resource when you create it\. For more information, see the documentation for the service where you want to tag resources\.
+ You can't backdate the application of a tag\. This means that tags only start appearing on your cost allocation report after you apply them and don't appear on earlier reports\.
+ If you need characters outside of those listed in [Tag Restrictions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html#tag-restrictions), you can apply standard base\-64 encoding to your tag\. Billing and Cost Management does not encode or decode your tag for you\.
+ User\-defined tags on non\-metered services can be activated \(for example, Account Tagging\)\. However, these tags will not populate in the Cost Management suite because these services are not metered\.