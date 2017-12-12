# User\-Defined Tag Restrictions<a name="allocation-tag-restrictions"></a>

The following basic restrictions apply to tags:

+ Maximum key length: 128 Unicode characters

+ Maximum value length: 256 Unicode characters

+ Case sensitive

+ Maximum number of tags per resource: 50

+ Maximum active tag keys for Billing and Cost Management reports: 500

+ Reserved prefix—`aws:`

  AWS\-generated tag names and values are automatically assigned the `aws:` prefix, which you cannot assign\. User\-defined tag names have the prefix `user:` in the Cost Allocation Report\.

+ Use each key only once for each resource\. If you attempt to use the same key twice on the same resource, your request will be rejected\.

+ You cannot tag a resource at the same time you create it\. Tagging requires a separate action after the resource is created\.

+ You cannot backdate the application of a tag\. This means that tags only start appearing on your cost allocation report after you apply them, and do not appear on earlier reports\.

+ Allowed characters are letters, whitespace, and numbers, plus the following special characters: \+ \- = \. \_ : /
**Note**  
If you need characters outside this allowed set, you can apply standard base\-64 encoding to your tag\.