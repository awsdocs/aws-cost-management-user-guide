# User\-Defined Tag Restrictions<a name="allocation-tag-restrictions"></a>

The following basic restrictions apply to tags:
+ The maximum key length is 128 Unicode characters\.
+ The maximum value length is 256 Unicode characters\.
+ Tags are case sensitive\.
+ The maximum number of tags per resource is 50\.
+ The maximum active tag keys for Billing and Cost Management reports is 500\.
+ The reserved prefix is `aws:`\.

  AWS generated tag names and values are automatically assigned the `aws:` prefix, which you can't assign\. User\-defined tag names have the prefix `user:` in the cost allocation report\.
+ Use each key only once for each resource\. If you attempt to use the same key twice on the same resource, your request will be rejected\.
+ In some services, you can tag a resource when you create it\. For more information, see the documentation for the service where you want to tag resources\.
+ You can't backdate the application of a tag\. This means that tags only start appearing on your cost allocation report after you apply them and don't appear on earlier reports\.
+ Allowed characters are Unicode letters, whitespace, and numbers, plus the following special characters: \+ \- = \. \_ : /
**Note**  
If you need characters outside this allowed set, you can apply standard base\-64 encoding to your tag\. Billing and Cost Management does not encode or decode your tag for you\.