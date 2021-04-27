# AWS\-Generated Cost Allocation Tags<a name="aws-tags"></a>

The AWS generated tags `createdBy` is a tag that AWS defines and applies to supported AWS resources for cost allocation purposes\. To use the AWS generated tags, a management account owner must activate it in the Billing and Cost Management console\. When a management account owner activates the tag, the tag is also activated for all member accounts\. After the tag is activated, AWS starts applying the tag to resources that are created after the AWS generated tags was activated\.  The AWS generated tags is available only in the Billing and Cost Management console and reports, and doesn't appear anywhere else in the AWS console, including the AWS Tag Editor\. The `createdBy` tag does not count towards your tags per resource limit\.

The `createdBy` tag uses the following key\-value definition:

```
key = aws:createdBy
```

```
value = account-type:account-ID or access-key:user-name or role session name
```

Not all values include all of the value parameters\. For example, the value for a AWS generated tag for a root account doesn't always have a user name\.

Valid values for the *account\-type* are `Root`, `IAMUser`, `AssumedRole`, and `FederatedUser`\.

If the tag has an account ID, the *account\-id* tracks the account number of the root account or federated user who created the resource\. If the tag has an access key, then the *access\-key* tracks the IAM access key used and, if applicable, the session role name\.

The *user\-name* is the user name, if one is available\.

Here are some examples of tag values:

```
Root:1234567890
Root: 111122223333 :exampleUser
IAMUser: AIDACKCEVSQ6C2EXAMPLE :exampleUser
AssumedRole: AKIAIOSFODNN7EXAMPLE :exampleRole
FederatedUser:1234567890:exampleUser
```

For more information about IAM users, roles, and federation, see the [IAM User Guide](https://docs.aws.amazon.com/IAM/latest/UserGuide/)\.

AWS\-generated cost allocation tags are applied on a best\-effort basis\. Issues with services that AWS generated tags depend on, such as CloudTrail, can cause a gap in tagging\. 

The `createdBy` tag is applied only to the following services and resources after the following events\.


| AWS Product | API or Console Event | Resource Type | 
| --- | --- | --- | 
| AWS CloudFormation \(AWS CloudFormation\) |  `CreateStack`  |  Stack  | 
| AWS Data Pipeline \(AWS Data Pipeline\) |  `CreatePipeline`  |  Pipeline  | 
| Amazon Elastic Compute Cloud \(Amazon EC2\) |  `CreateCustomerGateway`  |  Customer gateway  | 
|    |  `CreateDhcpOptions`  |  DHCP options  | 
|    |  `CreateImage`  |  Image  | 
|    |  `CreateInternetGateway`  |  Internet gateway  | 
|    |  `CreateNetworkAcl`  |  Network ACL  | 
|    |  `CreateNetworkInterface`  |  Network interface  | 
|    |  `CreateRouteTable`  |  Route table  | 
|    |  `CreateSecurityGroup`  |  Security group  | 
|    |  `CreateSnapshot`  |  Snapshot  | 
|    |  `CreateSubnet`  |  Subnet  | 
|    |  `CreateVolume`  |  Volume  | 
|    |  `CreateVpc`  |  VPC  | 
|    |  `CreateVpcPeeringConnection`  |  VPC peering connection  | 
|    |  `CreateVpnConnection`  |  VPN connection  | 
|    |  `CreateVpnGateway`  |  VPN gateway  | 
|    |  `PurchaseReservedInstancesOffering`  |  Reserved\-instance  | 
|    |  `RequestSpotInstances`  |  Spot\-instance\-request  | 
|    |  `RunInstances`  |  Instance  | 
| Amazon ElastiCache \(ElastiCache\) |  `CreateSnapshot`  |  Snapshot  | 
|    |  `CreateCacheCluster`  |  Cluster  | 
| AWS Elastic Beanstalk \(Elastic Beanstalk\) |  `CreateEnvironment`  |  Environment  | 
|    |  `CreateApplication`  |  Application  | 
| Elastic Load Balancing \(Elastic Load Balancing\) |  `CreateLoadBalancer`  |  Loadbalancer  | 
| Amazon S3 Glacier \(S3 Glacier\) |  `CreateVault`  |  Vault  | 
| Amazon Kinesis \(Kinesis\) |  `CreateStream`  |  Stream  | 
| Amazon Relational Database Service \(Amazon RDS\) |  `CreateDBInstanceReadReplica`  |  Database  | 
|    |  `CreateDBParameterGroup`  |  ParameterGroup  | 
|    |  `CreateDBSnapshot`  |  Snapshot  | 
|    |  `CreateDBSubnetGroup`  |  SubnetGroup  | 
|    |  `CreateEventSubscription`  |  EventSubscription  | 
|    |  `CreateOptionGroup`  |  OptionGroup  | 
|    |  `PurchaseReservedDBInstancesOffering`  |  ReservedDBInstance  | 
|    |  `CreateDBInstance`  |  Database  | 
| Amazon Redshift \(Amazon Redshift\) |  `CreateClusterParameterGroup`  |  ParameterGroup  | 
|    |  `CreateClusterSnapshot`  |  Snapshot  | 
|    |  `CreateClusterSubnetGroup`  |  SubnetGroup  | 
|    |  `CreateCluster`  |  Cluster  | 
| Amazon Route 53 \(Route 53\) |  `CreateHealthCheck`  |  HealthCheck  | 
|    |  `CreatedHostedZone`  |  HostedZone  | 
| Amazon Simple Storage Service \(Amazon S3\) |  `CreateBucket`  |  Bucket  | 
| AWS Storage Gateway \(AWS Storage Gateway\) |  `ActivateGateway`  |  Gateway  | 

**Note**  
The `CreateDBSnapshot` tag isn't applied to the snapshot backup storage\.

## AWS Marketplace vendor\-provided tags<a name="marketplace-isv-tags"></a>

Certain AWS Marketplace vendors can create tags and associate them with your software usage\. These tags will have the prefix `aws:marketplace:isv:`\. To use the tags, a management account owner must activate the tag in the Billing and Cost Management console\. When a management account owner activates the tag, the tag is also activated for all member accounts\. Similar to `aws:createdBy` tags, these tags appear only in the Billing and Cost Management console and does not count towards your tags per resource limit\. You can find the tag keys that apply to the product on the [AWS Marketplace](http://aws.amazon.com/marketplace/) product pages\.