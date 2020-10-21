# Restrictions on AWS\-Generated Cost Allocation Tags<a name="aws-tag-restrictions"></a>

The following restrictions apply to the AWS generated tags:
+ Only a management account can activate AWS generated tags\.
+ You can't update, edit, or delete AWS generated tags\.
+ AWS\-generated cost allocation tags aren't applied to resources that were created before the tag was activated\.
+ The maximum active tag keys for Billing and Cost Management reports is 500\.
+ AWS generated tags are created using CloudTrail logs\. CloudTrail logs over a certain size cause AWS generated tag creation to fail\.
+ The reserved prefix is `aws:`\.

  AWS generated tag names and values are automatically assigned the `aws:` prefix, which you can't assign\. AWS generated tag names don't count towards the user\-defined resource tag limit of 50\. User\-defined tag names have the prefix `user:` in the cost allocation report\.
+ Null tag values will not appear in Cost Explorer and AWS Budgets\. If there is only one tag value that is also null, the tag key will also not appear in Cost Explorer or AWS Budgets\.