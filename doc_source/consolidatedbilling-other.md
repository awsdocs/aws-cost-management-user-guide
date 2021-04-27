# Billing examples for specific services<a name="consolidatedbilling-other"></a>

There are a few other things to know about how consolidated billing works with specific services in AWS\.

## Amazon EC2 reserved instances<a name="consolidatedbilling-ec2"></a>



For an Amazon EC2 Reserved Instances example, suppose that Bob and Susan each have an account in an organization\. Susan has five Reserved Instances of the same type, and Bob has none\. During one particular hour, Susan uses three instances and Bob uses six, for a total of nine instances on the organization's consolidated bill\. AWS bills five instances as Reserved Instances, and the remaining four instances as regular instances\. 

Bob receives the cost benefit from Susan's Reserved Instances only if he launches his instances in the same Availability Zone where Susan purchased her Reserved Instances\. For example, if Susan specifies `us-west-2a` when she purchases her Reserved Instances, Bob must specify `us-west-2a` when he launches his instances to get the cost benefit on the organization's consolidated bill\. However, the actual locations of Availability Zones are independent from one account to another\. For example, the `us-west-2a` Availability Zone for Bob's account might be in a different location than the location for Susan's account\.

## Amazon RDS reserved DB instances<a name="consolidatedbilling-rds"></a>

For an Amazon RDS Reserved DB Instances example, suppose that Bob and Susan each have an account in an organization\. Susan has five Reserved DB Instances, and Bob has none\. During one particular hour, Susan uses three DB Instances and Bob uses six, for a total of nine DB Instances on the consolidated bill\. AWS bills five as Reserved DB Instances, and the remaining four as On\-Demand DB Instances \(for Amazon RDS Reserved DB Instance charges, see the [pricing page](https://aws.amazon.com/rds/pricing/)\)\. Bob receives the cost benefit from Susan's Reserved DB Instances only if he launches his DB Instances in the same region where Susan purchased her Reserved DB Instances\.

Also, all of the relevant attributes of Susan's Reserved DB Instances should match the attributes of the DB Instances launched by Bob as described in [Reserved DB Instances](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_WorkingWithReservedDBInstances.html)\. For example, let's say Susan purchased a Reserved DB Instance in `us-west-2` with the following attributes:
+ DB Engine: Oracle
+ DB Instance Class: `m1.xlarge`
+ Deployment Type: Multi\-AZ

This means that Bob must launch his DB Instances in `us-west-2` with the exact same attributes to get the cost benefit on the organization's consolidated bill\. 

## Amazon ElastiCache reserved node instances<a name="consolidatedbilling-elasticache"></a>

For an Amazon ElastiCache Reserved Nodes example, suppose Bob and Susan each have an account in an organization\. Susan has five Reserved Nodes, and Bob has none\. During one particular hour, Susan uses three nodes and Bob uses six\. This makes a total of nine nodes used on the consolidated bill\. 

AWS bills five as Reserved Nodes\. AWS bills the remaining four as On\-Demand nodes\. \(For Amazon ElastiCache Reserved Nodes charges, see [Amazon ElastiCache Pricing](https://aws.amazon.com/elasticache/pricing/)\.\) Bob receives the cost benefit from Susan's Reserved Nodes only if he launches his On\-Demand nodes in the same region where Susan purchased her Reserved Nodes\.

Also, to receive the cost benefit of Susan’s Reserved Nodes, all attributes of Bob's nodes must match the attributes of the nodes launched by Susan\. For example, let's say Susan purchased Reserved Nodes in `us-west-2` with the following attributes: 
+ Cache engine: Redis
+ Node type: `cache.r3.large`

Bob must launch his ElastiCache nodes in `us-west-2` with the same attributes to get the cost benefit on the organization's consolidated bill\.

## Amazon Elasticsearch Service reserved instances<a name="consolidatedbilling-elastisearch"></a>

For an Amazon Elasticsearch Service Reserved Nodes example, suppose Bob and Susan each have an account in an organization\. Susan has five Reserved Instances, and Bob has none\. During one particular hour, Susan uses three instances and Bob uses six\. This makes a total of nine instances used on the consolidated bill\.

AWS bills five as Reserved Instances\. AWS bills the remaining four as On\-Demand instances\. \(For Amazon Elasticsearch Service Reserved Instance charges, see [Amazon Elasticsearch Service Pricing](https://aws.amazon.com/elasticsearch-service/pricing/)\.\) Bob receives the cost benefit from Susan's Reserved Instances only if he launches his On\-Demand instances in the same region where Susan purchased her Reserved Instances\.

To receive the cost benefit of Susan’s Reserved Instances, Bob also must use the same instance type that Susan reserved\. For example, let's say Susan purchased `m4.large.elasticsearch` instances in `us-west-2`\. Bob must launch his Amazon Elasticsearch Service domains in `us-west-2` with the same instance type to get the cost benefit on the organization's consolidated bill\.