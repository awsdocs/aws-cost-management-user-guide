# AWS Free Tier limits<a name="free-tier-limits"></a>

All services that offer a AWS Free Tier have limits on what you can use without being charged\. Many services have multiple types of limits\. For example, Amazon EC2 has limits on both the type of instance you can use and how many hours you can use in one month\. Amazon S3 has a limit on how much storage you can use and on how often you can call certain operations each month\. For example, the AWS Free Tier covers the first 20,000 times you retrieve a file from Amazon S3, but you're charged for additional file retrievals\. Each service has limits that are unique to that service\.

Some of the most common limits are by time, such as hourly or by the minute, or by requests, which are the requests you send to the service, also known as API operations\. For more information about AWS Free Tier limits, see [AWS Free Tier](http://aws.amazon.com/free/)\.

**Topics**
+ [Hourly usage in the AWS Free Tier](#hourly-limits)
+ [Amazon Machine Images](#ami-limits)

## Hourly usage in the AWS Free Tier<a name="hourly-limits"></a>

Some services, such as Amazon EC2, Amazon RDS, and Elastic Load Balancing, charge for usage on an hourly basis\. The AWS Free Tier for these services provides you with a monthly allotment of hours for the first 12 months\. For example, the AWS Free Tier for Amazon EC2 provides you with 750 hours usage of Linux \(any combination of `t1.micro`, `t2.micro`, and `t3.micro` instances\), plus 750 hours usage of Windows \(any combination of `t1.micro`, `t2.micro`, and `t3.micro` instances\)\. How you divide this allotment is up to you\. In this example, you can run 750 hours of a Linux `t2.micr`o, or `t1.micro` instance with 750 hours of a Windows `t2.micro`, or `t1.micro` instance each month for the first 12 months\. In Regions where `t2.micro` is not available, the `t3.micro` equivalent is supported under AWS Free Tier\. For example, you can use one Linux instance continuously for a month, or 10 Linux instances for 75 hours a month\.

In some cases, leaving your resources running maximizes your AWS Free Tier benefits\. For example, when an Amazon EC2 instance enters into running state, a full instance hour is charged\. This will occur every time an instance changes into running state, even in the same hour\. Instances stop being billed when they are stopped, but are billed for full last hour during which they are running\. AWS bills Amazon EC2 instances in instance hours\. An instance is billed as soon as it enters the `running` state, and when an instance enters the `shutting down`, `stopped` or `terminated` we stop billing for the instance\. For more information about changing instance states, see [Stop and start your instance](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Stop_Start.html) in the *Amazon EC2 User Guide for Linux Instances*\.

**Note**  
Several services measure usage in seconds\. See each service page's details to see how your service is measured and billed\.  
Resources related to the instance might continue to be billed, even if the instance is stopped or terminated\. Some examples of these resources include Elastic IPs that were detached but never released, and Amazon Elastic Block Store \(Amazon EBS\) volumes that might have been associated to the instance but not deleted\.  
If you run Linux instances, you will be billed per second\. For example, if you run your Amazon Linux instance for 30 seconds, you'll be charged for 30 seconds\.

For more information, see [Amazon EC2 Pricing](https://aws.amazon.com/ec2/pricing/)\.

## Amazon Machine Images<a name="ami-limits"></a>

When you start an Amazon EC2 instance, you must select an Amazon Machine Image \(AMI\) that is eligible for the AWS Free Tier\. Because of licensing restrictions, some AMIs aren't eligible for the AWS Free Tier\.

**Important**  
Third\-party applications or services from AWS Marketplace aren't eligible for the AWS Free Tier\.

AMIs that are eligible for the AWS Free Tier are marked in the Amazon EC2 Launch Wizard as **Free tier eligible**\. The AWS Free Tier allotment for Linux and Microsoft Windows instances is counted separately\. You can run 750 hours of a Linux `t3.micro`, `t2.micro`, or `t1.micro` instance plus 750 hours of a Windows `t3.micro`, `t2.micro`, or `t1.micro` instance each month for the first 12 months\.

For more information, see [Amazon EC2 pricing](https://aws.amazon.com/ec2/pricing/)\.