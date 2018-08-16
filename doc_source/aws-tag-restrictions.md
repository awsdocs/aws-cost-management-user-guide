# AWS\-Generated Cost Allocation Tag Restrictions<a name="aws-tag-restrictions"></a>

The following restrictions apply to the AWS generated tagss:
+ AWS generated tags can only be activated by master accounts\.
+ You can't update, edit, or delete AWS tags\.
+ AWS\-generated cost allocation tags are not applied to resources that were created before the tag was activated\.
+ Maximum active tag keys for Billing and Cost Management reports: 500\.
+ AWS generated tags are created using CloudTrail logs\. CloudTrail logs over a certain size cause AWS generated tag creation to fail\.
+ Reserved prefix—`aws:`\.

  AWS\-generated tag names and values are automatically assigned the `aws:` prefix, which you can't assign\. AWS\-generated tag names do not count towards the tag limit of 50\. User\-defined tag names have the prefix `user:` in the Cost Allocation Report\.