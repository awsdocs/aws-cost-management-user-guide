# Avoiding unexpected charges<a name="checklistforunwantedcharges"></a>

Here are some suggestions to help you avoid unexpected charges on your bill\. The first two items are for those who use the one\-year AWS Free Tier\. The next items address specific features or behaviors within individual services from AWS that can sometimes result in unexpected charges, particularly if you unsubscribe from the service or close your account\.

**Note**  
If you close your account or unsubscribe from a service, make sure that you take the appropriate steps for every region in which you've allocated AWS resources\.

**Topics**
+ [Usage exceeds AWS Free Tier](#checkexceedfree)
+ [AWS Free Tier expired](#checkfreetierexpired)
+ [Bill received after account closure](#checkbillafterclosure)
+ [Disabled regions](#check-disabled-region)
+ [Elastic Beanstalk environments](#checkelasticbeanstalk)
+ [Elastic Load Balancing \(ELB\)](#checkloadbalancers)
+ [Services started in AWS OpsWorks](#opsworks)
+ [Amazon EC2 instances](#checkec2instances)
+ [Amazon Elastic Block Store volumes and snapshots](#checkebsvolumes)
+ [Elastic IP addresses](#checkelasticipaddresses)
+ [Services launched by other services](#servicesnotfree)
+ [Storage services](#servicestorage)

## Usage exceeds AWS Free Tier<a name="checkexceedfree"></a>

If you use the free tier, make sure that your usage does not exceed the limits that are specified at [AWS Free Tier](http://aws.amazon.com/free/)\. You are charged On\-Demand Instance rates for any usage that exceeds the free tier limits\. You can check your AWS Free Tier usage alerts and your free tier usage alerts on the Billing and Cost Management console\.

**Note**  
Free tier usage alerts are available only to the management account in an organization\. They aren't available for individual member accounts in an organization\. 

For more information about tracking your free tier usage, see [Tracking your AWS Free Tier usage](tracking-free-tier-usage.md)\.

## AWS Free Tier expired<a name="checkfreetierexpired"></a>

If you receive unexpected charges after a period of inactivity, your free tier period might have expired\. Any resources that are allocated to your account after your free tier period expires begin to incur charges\. To check for resources in use, open the [AWS Management Console](https://console.aws.amazon.com/console/home?#)\. **Be sure to check each Region where you have allocated resources\.**

For more information about free tier offerings and terms, see [AWS Free Tier](http://aws.amazon.com/free/)\.

## Bill received after account closure<a name="checkbillafterclosure"></a>

Each month’s usage is calculated and billed at the beginning of the following month\. If you close your account but use opt\-in services during the month, you receive a bill for the opt\-in service usage at the beginning of the following month\.

## Disabled regions<a name="check-disabled-region"></a>

If you disable a Region and you still have resources in that Region, you continue to incur charges for those resources\. \(There is no charge for enabling a Region, only charges for the resources that you create in a Region\.\) For more information, see [Enabling and disabling regions](manage-account-payment.md#manage-account-payment-enable-disable-regions)\.

## Elastic Beanstalk environments<a name="checkelasticbeanstalk"></a>

Elastic Beanstalk is designed to ensure that all the resources that you need are running, which means that it automatically relaunches any services that you stop\. To avoid this, you must terminate your Elastic Beanstalk environment before you terminate resources that Elastic Beanstalk has created\. For more information, see [Terminating an Environment](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.terminating.html) in the *AWS Elastic Beanstalk Developer Guide*\. 

## Elastic Load Balancing \(ELB\)<a name="checkloadbalancers"></a>

Like Elastic Beanstalk environments, ELB load balancers are designed to keep a minimum number of Amazon Elastic Compute Cloud \(Amazon EC2\) instances running\. You must terminate your load balancer before you delete the Amazon EC2 instances that are registered with it\. For more information, see [Delete Your Load Balancer](https://docs.aws.amazon.com/elasticloadbalancing/latest/userguide/US_EndLoadBalancing02.html) in the *Elastic Load Balancing User Guide*\. 

## Services started in AWS OpsWorks<a name="opsworks"></a>

If you use the AWS OpsWorks environment to create AWS resources, you must use AWS OpsWorks to terminate those resources or AWS OpsWorks restarts them\. For example, if you use AWS OpsWorks to create an Amazon EC2 instance, but then terminate it by using the Amazon EC2 console, the AWS OpsWorks auto healing feature categorizes the instance as failed and restarts it\. For more information, see [AWS OpsWorks User Guide](https://docs.aws.amazon.com/opsworks/latest/userguide/welcome.html)\.

## Amazon EC2 instances<a name="checkec2instances"></a>

After you remove load balancers and Elastic Load Balancing environments, you can stop or terminate Amazon EC2 instances\. Stopping an instance allows you to start it again later, but you might be charged for storage\. Terminating an instance permanently deletes it\. For more information, see [Instance Lifecycle](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-lifecycle.html) in the *Amazon EC2 User Guide for Linux Instances*, particularly [Stop and Start Your Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html) and [Terminate Your Instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/terminating-instances.html)\.

**Note**  
Amazon EC2 instances serve as the foundation for multiple AWS services\. They can appear in the Amazon EC2 console Instances list even if they were started by other services\. For example, Amazon Relational Database Service \(Amazon RDS\) instances run on Amazon EC2 instances\. If you terminate an underlying Amazon EC2 instance, the service that started it might interpret the termination as a failure and restart the instance\. For example, the AWS OpsWorks service has a feature called *auto healing* that restarts resources when it detects failures\. In general, it is a best practice to delete resources through the services that started them\. 

Additionally, if you create Amazon EC2 instances from an Amazon Machine Image \(AMI\) that is backed by an instance store, check Amazon S3 for the related bundle\. Deregistering an AMI does not delete the bundle\. For more information, see [Deregistering Your AMI](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/deregister-ami.html)\. 

## Amazon Elastic Block Store volumes and snapshots<a name="checkebsvolumes"></a>

Most Amazon EC2 instances are configured so that their associated Amazon EBS volumes are deleted when they are terminated, but it is possible to set up an instance that preserves its volume and the data\. Check the **Volumes** pane in the Amazon EC2 console for volumes that you don’t need anymore\. For more information, see [Deleting an Amazon EBS Volume](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-volume.html) in the *Amazon EC2 User Guide for Linux Instances*\. 

If you have stored snapshots of your Amazon EBS volumes and no longer need them, you should delete them as well\. Deleting a volume does not automatically delete the associated snapshots\. 

For more information about deleting snapshots, see [Deleting an Amazon EBS Snapshot](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-deleting-snapshot.html)\.

**Note**  
Deleting a snapshot might not reduce your organization's data storage costs\. Other snapshots might reference that snapshot's data, and referenced data is always preserved\.   
For example, when you take the first snapshot of a volume with 10 GiB of data, the size of the snapshot is also 10 GiB\. Because snapshots are incremental, the second snapshot that you take of the same volume contains only blocks of data that changed since the first snapshot was taken\. The second snapshot also references the data in the first snapshot\. That is, if you modify 4 GiB of data and take a second snapshot, the size of the second snapshot is 4 GiB\. In addition, the second snapshot references the unchanged 6 GiB in the first snapshot\. For more information, see [ How Incremental Snapshots Work](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html#how_snapshots_work)\.   
The previous example will show two entries in your daily AWS Cost and Usage Reports \(AWS CUR\)\. AWS CUR captures the snapshot usage amount for a single day\. In this example, the usage is 0\.33 GiB \(10 GiB/ 30 days\) for snap\-A, and 0\.1333 GiB \(4 GiB/ 30 days\) for snap\-B\. Using the rate of $0\.05 per GB month, snap\-A costs you 0\.33 GiB x $0\.05 = $0\.0165\. Snap\-B costs you 0\.133 GiB x $0\.05 = $0\.0066, and you are charged $0\.0231 per day for both snapshots\. For more information about AWS Cost and Usage Reports, see the [https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html](https://docs.aws.amazon.com/cur/latest/userguide/what-is-cur.html)\.  


| **lineItem/ Operation** | **lineItem/ ResourceId** | **lineItem/ UsageAmount** | **lineItem/ UnblendedCost** | **resourceTags/ user:usage** | 
| --- | --- | --- | --- | --- | 
| CreateSnapshot | arn:aws:ec2:us\-east\-1:123:snapshot/snap\-A | 0\.33 | 0\.0165 | dev | 
| CreateSnapshot | arn:aws:ec2:us\-east\-1:123:snapshot/snap\-B | 0\.133 | 0\.0066 | dev | 
If you delete the first snapshot \(snap\-A in the first row of the preceding table\), any data that is referenced by the second snapshot \(snap\-B in the second row of the preceding table\) is preserved\. Remember that the second snapshot contains the 4 GiB of incremental data, and references 6 GiB from the first snapshot\. Once you delete snap\-A, the size of snap\-B becomes 10 GiB \(4 changed GiB from the snap\-B and 6 unchanged GiB from snap\-A\)\.  
In you daily AWS CUR, you will then see the usage amount for snap\-B as 0\.33 GiB \(10 GiB/ 30 days\), charged at $0\.0165 per day\. When you delete a snapshot, the charges for the remaining snapshots are recalculated daily, resulting in the possibility that the cost for each snapshot can change daily as well\. For more information, see [Cost Allocation for EBS Snapshots](http://aws.amazon.com/blogs/aws/new-cost-allocation-for-ebs-snapshots/)\.  


| **lineItem/ Operation** | **lineItem/ ResourceId** | **lineItem/ UsageAmount** | **lineItem/ UnblendedCost** | **resourceTags/ user:usage** | 
| --- | --- | --- | --- | --- | 
| CreateSnapshot | arn:aws:ec2:us\-east\-1:123:snapshot/snap\-B | 0\.33 | 0\.0165 | dev | 

## Elastic IP addresses<a name="checkelasticipaddresses"></a>

Any Elastic IP addresses that are attached to an instance that you terminate are unattached, but they are still allocated to you\. If you don’t need that IP address anymore, release it to avoid additional charges\. For more information, see [Releasing an Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html#using-instance-addressing-eips-releasing) in the *Amazon EC2 User Guide for Linux Instances*\. 

## Services launched by other services<a name="servicesnotfree"></a>

A number of AWS services can launch resources, so be sure to check for anything that might have launched through any service that you've used\.

## Storage services<a name="servicestorage"></a>

When you are minimizing costs for AWS resources, keep in mind that many services might incur storage costs, such as Amazon RDS and Amazon S3\. 