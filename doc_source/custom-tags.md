# User\-Defined Cost Allocation Tags<a name="custom-tags"></a>

User\-defined tags are tags that you define, create, and apply to resources\. After you have created and applied them, you can activate them on the Billing and Cost Management console for cost allocation tracking\. After you activate them, they appear on your cost allocation report\. You can then use the tags on your cost allocation report to track your AWS costs\. Tags are not applied to resources that were created before the tags were created\.

**Note**  
Only master accounts in an organization and single accounts that aren't members of an organization have access to the **Cost Allocation Tags** manager in the Billing and Cost Management console\.

## Applying User\-Defined Cost Allocation Tags<a name="allocation-how"></a>

For ease of use and best results, use the AWS Tag Editor to create and apply user\-defined tags\. The Tag Editor provides a central, unified way to create and manage your user\-defined tags\. For more information, see [Working with Tag Editor](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/tag-editor.html) in [Getting Started with the AWS Management Console](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/getting-started.html)\.

For supported services, you can also apply tags to resources using the API or the AWS Management Console\. Each AWS service has its own implementation of tags\. You can work with these implementations individually or use Tag Editor to simplify the process\. The following is a partial list of services that support tags\. For a full list, see [API Reference](https://docs.aws.amazon.com/awsconsolehelpdocs/index.html)\.


| AWS Product | For More Information, See\.\.\. | 
| --- | --- | 
|  Amazon API Gateway  |  [Set up Tags for an API Stage in API Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-tags.html) in the *API Gateway Developer Guide*\.  | 
| Amazon AppStream 2\.0 |  [Tagging Your Amazon AppStream 2\.0 Resources](https://docs.aws.amazon.com/appstream2/latest/developerguide/tagging-basic.html) in the *Amazon AppStream 2\.0 Developer Guide*\.  | 
|  Amazon Athena  |  [Tagging Workgroups](https://docs.aws.amazon.com/athena/latest/ug/tags.html) in the *Amazon Athena User Guide*\.  | 
|  AWS CloudFormation  |  [Resource Tag](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-properties-resource-tags.html) in the *AWS CloudFormation User Guide*\.  | 
|  Amazon Cognito  |  [Adding Cost Allocation Tags to Your User Pool](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-pools-cost-allocation-tagging.html) in the *Amazon Cognito Developer Guide*\.  | 
|  Amazon DynamoDB  |   [Adding Tagging for DynamoDB](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Tagging.html) in the *Amazon DynamoDB Developer Guide*\.  | 
|  Amazon Elastic Block Store \(Amazon EBS\)  |  [Tagging Your Resources](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html) in the *Amazon Elastic Compute Cloud User Guide*\. For information about avoiding unexpected charges associated with your Amazon EBS volumes and snapshots, see [Amazon Elastic Block Store Volumes and Snapshots](checklistforunwantedcharges.md#checkebsvolumes)\.  | 
|  Amazon Elastic Container Service  |  [Tagging Your Amazon ECS Resources](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-using-tags.html) in the *Amazon Elastic Container Service Developer Guide*\.  | 
|  Amazon Elasticsearch Service \(Amazon ES\)  |  [Tagging Amazon Elasticsearch Service Domains](https://docs.aws.amazon.com/elasticsearch-service/latest/developerguide/es-managedomains.html#es-managedomains-awsresourcetagging) in the *Amazon Elasticsearch Service Developer Guide*\.  | 
|  Amazon ElastiCache \(ElastiCache\)  |  [Using Cost Allocation Tags in ElastiCache](https://docs.aws.amazon.com/AmazonElastiCache/latest/UserGuide/Tagging.html) in the *Amazon ElastiCache User Guide*\.  | 
|  Amazon Elastic Compute Cloud \(Amazon EC2\)  |  [Tagging Your Resources](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html) in the *Amazon Elastic Compute Cloud User Guide*\. For information about avoiding unexpected charges associated with your Amazon EC2 instances, see [Amazon EC2 Instances](checklistforunwantedcharges.md#checkec2instances)\.  | 
|  Amazon Elastic File System \(Amazon EFS\)  | [Managing File System Tags](https://docs.aws.amazon.com/efs/latest/ug/manage-fs-tags.html) in the Amazon Elastic File System User Guide\. | 
|  Elastic Load Balancing  |  [Tags for Your Application Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-tags.html) in the *User Guide for Application Load Balancers*, [Tags for Your Network Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/network/load-balancer-tags.html) in the *User Guide for Network Load Balancers*, or [Tag Your Classic Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/add-remove-tags.html) in the *User Guide for Classic Load Balancers*\. For information about avoiding unexpected charges associated with your Elastic Load Balancing load balancers, see [Elastic Load Balancing \(ELB\)](checklistforunwantedcharges.md#checkloadbalancers)\.  | 
|  Amazon EMR  |  [Tagging Amazon EMR Clusters](https://docs.aws.amazon.com/emr/latest/DeveloperGuide/emr-plan-tags.html) in the *Amazon EMR Developer Guide*\.  | 
|  Amazon S3 Glacier  |  [Tagging Your Amazon S3 Glacier Resources](https://docs.aws.amazon.com/amazonglacier/latest/dev/tagging.html) in the *Amazon S3 Glacier Developer Guide*\.  | 
|  AWS Identity and Access Management  |  [Controlling Access Using IAM Tags](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_iam-tags.html) in the *IAM User Guide*\.  | 
|  Amazon Kinesis  |  [Tagging Your Kinesis Streams](https://docs.aws.amazon.com/kinesis/latest/dev/tagging.html) in the *Amazon Kinesis Developer Guide*\.  | 
|  Amazon Lumberyard  |  [Tag](https://docs.aws.amazon.com/lumberyard/latest/userguide/component-tag.html) in the *Amazon Lumberyard User Guide*\.  | 
|  Amazon Redshift  |  [Tagging Resources in Amazon Redshift](https://docs.aws.amazon.com/redshift/latest/mgmt/amazon-redshift-tagging.html) in the *Amazon Redshift Cluster Management Guide*\.  | 
|  Amazon Relational Database Service \(Amazon RDS\)  |  [Tagging Amazon RDS Resources](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_Tagging.html) in the *Amazon Relational Database Service User Guide*\.  For information about avoiding unexpected charges associated with your Amazon RDS databases, see [Storage Services](checklistforunwantedcharges.md#servicestorage)\.  | 
|  Amazon Route 53  |  [Tagging Amazon Route 53 Resources](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/tagging-resources.html) in the *Amazon Route 53 Developer Guide*\.  | 
|  Amazon SageMaker  |  [AddTags](https://docs.aws.amazon.com/sagemaker/latest/dg/API_AddTags.html) in the *Amazon SageMaker Developer Guide*\.  | 
|  Amazon Simple Queue Service  |  [Tagging Your Amazon SQS Queues](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-queue-tags.html) in the *Amazon Simple Queue Service Developer Guide*\.  | 
|  Amazon Simple Storage Service \(Amazon S3\)  |  [Billing and Reporting of Buckets](https://docs.aws.amazon.com/AmazonS3/latest/dev/BucketBilling.html) in the *Amazon Simple Storage Service Developer Guide*\. For information about avoiding unexpected charges associated with your Amazon S3 buckets, see [Storage Services](checklistforunwantedcharges.md#servicestorage)\.  | 
|  Amazon Virtual Private Cloud \(Amazon VPC\)  |  Amazon VPC and Amazon EC2 resources that can be tagged are listed in [Tagging Your Resources](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html) in the *Amazon Elastic Compute Cloud User Guide*\.  | 
|  Amazon EC2 Auto Scaling  |  [Tagging Auto Scaling Groups and Amazon EC2 Instances](https://docs.aws.amazon.com/autoscaling/latest/userguide//ASTagging.html) in the *Amazon EC2 Auto Scaling Developer Guide*\.  | 
|  AWS CloudFormation  |  [Tagging Your Member Resources](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-tagging.html) in the *AWS CloudFormation User Guide*\.  | 
|  AWS Elastic Beanstalk  |  [Tagging Your Environments and Applications](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.tagging.html) in the *AWS Elastic Beanstalk Developer Guide*\. For information about avoiding unexpected charges associated with your Elastic Beanstalk environments, see [Elastic Beanstalk Environments](checklistforunwantedcharges.md#checkelasticbeanstalk)\.  | 
|  AWS Lambda  |  [Tagging Lambda Functions](https://docs.aws.amazon.com/lambda/latest/dg/tagging.html) in the *AWS Lambda Developer Guide*\.  | 
|  Amazon WorkSpaces  |  [Tag a WorkSpace](https://docs.aws.amazon.com/workspaces/latest/adminguide/wsp_tag_workspace.html) in the *Amazon WorkSpaces Administration Guide*\.  | 

After you create and apply user\-defined tags, you can activate them for cost allocation\. If you activate your tags for cost allocation, it's a good idea to devise a set of tag keys that represent how you want to organize your costs\. Your cost allocation report displays the tag keys as additional columns with the applicable values for each row, so it's easier to track your costs if you use a consistent set of tag keys\. 

**Note**  
User\-defined cost allocation tags created by linked accounts can take up to 24 hours to appear in the Billing and Cost Management console\. To speed up the process, you can trigger a manual refresh\. For more information, see [Refreshing User\-Defined Cost Allocation Tags](refresh-cost-alloc-tags.md)

Some services launch other AWS resources that the service uses, such as Amazon EMR or AWS Marketplace launching an EC2 instance\. If the supporting service \(EC2\) supports tagging, you can tag the supporting resources \(such as the associated Amazon EC2 instance\) for your report\. For a full list of resources that can be tagged, use the Tag Editor to search\. For more information about how to search for resources using Tag Editor, see [ Searching for Resources to Tag](https://docs.aws.amazon.com/awsconsolehelpdocs/latest/gsg/searching-resources-to-tag.html)\. 