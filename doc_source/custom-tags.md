# User\-Defined Cost Allocation Tags<a name="custom-tags"></a>

User\-defined tags are tags that you define, create, and apply to resources\. After you have created and applied the user\-defined tags, you can activate by using the Billing and Cost Management console for cost allocation tracking\. Cost Allocation Tags appear on the console after you've enabled Cost Explorer, Budgets, AWS Cost and Usage Reports, or legacy reports\. After you activate the AWS services, they appear on your cost allocation report\. You can then use the tags on your cost allocation report to track your AWS costs\. Tags are not applied to resources that were created before the tags were created\.

**Note**  
As a best practice, reactivate your cost allocation tags when moving organizations\. When an account moves to another organization as a member, previously activated cost allocation tags for that account lose their "active" status and need to be activated again by the new management account\.
As a best practice, do not include sensitive information in tags\.
Only a management account in an organization and single accounts that aren't members of an organization have access to the **Cost Allocation Tags** manager in the Billing and Cost Management console\.

## Applying User\-Defined Cost Allocation Tags<a name="allocation-how"></a>

For ease of use and best results, use the AWS Tag Editor to create and apply user\-defined tags\. The Tag Editor provides a central, unified way to create and manage your user\-defined tags\. For more information, see [Working with Tag Editor](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html) in the [AWS Resource Groups User Guide](https://docs.aws.amazon.com/ARG/latest/userguide/welcome.html)\.

For supported services, you can also apply tags to resources using the API or the AWS Management Console\. Each AWS service has its own implementation of tags\. You can work with these implementations individually or use Tag Editor to simplify the process\. For a full list of services that support tags, see [Supported Resources for Tag\-based Groups](https://docs.aws.amazon.com/ARG/latest/userguide/supported-resources.html#supported-resources-console-tagbased) and [Resource Groups Tagging API Reference](https://docs.aws.amazon.com/resourcegroupstagging/latest/APIReference/Welcome.html)\.

After you create and apply user\-defined tags, you can [activate them](activating-tags.md) for cost allocation\. If you activate your tags for cost allocation, it's a good idea to devise a set of tag keys that represent how you want to organize your costs\. Your cost allocation report displays the tag keys as additional columns with the applicable values for each row, so it's easier to track your costs if you use a consistent set of tag keys\. 

Some services launch other AWS resources that the service uses, such as Amazon EMR launching an EC2 instance\. If the supporting service \(EC2\) supports tagging, you can tag the supporting resources \(such as the associated Amazon EC2 instance\) for your report\. For a full list of resources that can be tagged, use the Tag Editor to search\. For more information about how to search for resources using Tag Editor, see [ Searching for Resources to Tag](https://docs.aws.amazon.com/ARG/latest/userguide/find-resources-to-tag.html )\.

**Note**  
AWS Marketplace line items are tagged with the associated Amazon EC2 instance tag\.