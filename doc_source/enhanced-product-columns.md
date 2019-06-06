# Product Details<a name="enhanced-product-columns"></a>

The product columns provide metadata about the product that incurred the expense, and the line item\. The product columns are dynamic, and their visibility in Cost and Usage Report depends on the usage of product in the billing period\. 

## Downloading a Product Column Spreadsheet<a name="download"></a>

The following is a subset of product columns and the corresponding definitions\. To download the full list of the columns that can appear in the Cost and Usage Report and the services that the columns apply to, choose [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\.

 [A](#A) \|  [C](#C) \| [D](#D) \| [E](#E) \|  [G](#G) \|  [I](#I) \|  [L](#L) \| [M](#M) \| [N](#N) \| [O](#O) \| [P](#P) \|  [R](#R) \| [S](#S) \| [T](#T) \| [U](#U) \| [V](#V) \|  

## A<a name="product-details-A"></a>

### product/availability<a name="product-details-A-availability"></a>
+ **Description:** Describes the availability of your various AWS storage options\. 
+ **Sample values:** `99.99%`, `99.5%`
+ **Services:**
  + Amazon S3 Glacier
  + Amazon S3
  + AWS Elemental MediaStore
  + AWS RoboMaker

## C<a name="product-details-C"></a>

### product/capacitystatus<a name="product-details-C-capacity"></a>
+ **Description:** Describes the status of your capacity reservations\. 
+ **Sample values:** `UnusedCapacityReservation`, `AllocatedCapacityReservation`, `Used`
+ **Services:**
  + Amazon EC2

### product/clockspeed<a name="product-details-C-clock"></a>
+ **Description:** Describes the operating speed of your AWS instances\. 
+ **Sample values:** `2.4 GHz`, `2.6 GHz`
+ **Services:**
  + Amazon DocumentDB
  + Amazon EC2
  + Amazon MQ
  + Amazon Neptune
  + Amazon RDS
  + AWS Database Migration Service

## D<a name="product-details-D"></a>

### product/dedicatedEbsThroughput<a name="product-details-D-dedicated"></a>
+ **Description:** Describes the dedicated throughput between your instances \(e\.g\., Amazon EC2 instances and Amazon EBS volumes\), with options between 500 and 10,000 megabits per second \(Mbps\) depending on the instance type used\. The dedicated throughput minimizes contention between Amazon EBS I/O and other traffic from your EC2 instance, providing the best performance for your Amazon EBS volumes\.
+ ** Sample values: ** `200 Mbps`, `Upto 5000 Mbps`
+ **Services:**
  + Amazon EC2
  + Amazon Neptune
  + Amazon RDS

### product/durability<a name="product-details-D-durability"></a>
+ **Description:** Describes the durability of objects over a given year\. 
+ **Sample values:** `99.999999999%`, `N/A`, `99.99%`
+ **Services:**
  + Amazon S3 Glacier
  + Amazon S3
  + AWS Elemental MediaStore

## E<a name="product-details-E"></a>

### product/ebsOptimized<a name="product-details-E-ebs"></a>
+ **Description:** Describes whether your Amazon EC2 instances are Amazon EBS–optimized\. 
+ **Sample values:** `Yes`, `No`
+ **Services:**
  + Amazon EC2

### product/ecu<a name="product-details-E-ecu"></a>
+ **Description:** Describes the EC2 Compute Unit \(ECU\) that provides the relative measure of the integer processing power of an Amazon EC2 instance\. 
+ **Sample values:** `9`, `100`, `variable`
+ **Services:**
  + Amazon EC2
  + Amazon ES
  + Amazon GameLift
  + Amazon Redshift

### product/enhancedNetworkingSupported<a name="product-details-E-enhanced"></a>
+ **Description:** Describes whether your instance supports enhanced networking\. Enhanced networking uses single root I/O virtualization \(SR\-IOV\) to provide high\-performance networking capabilities on supported instance types\. 
+ **Sample values:** `Yes`, `No`
+ **Services:**
  + Amazon DocumentDB
  + Amazon EC2
  + Amazon Neptune
  + Amazon RDS
  + AWS Database Migration Service

## G<a name="product-details-G"></a>

### product/gpu<a name="product-details-G-gpu"></a>
+ **Description:** Describes the number of GPUs\. 
+ **Sample values:** `16`, `32` 
+ **Services:**
  + Amazon SageMaker
  + Amazon EC2

### product/gpuMemory<a name="prodcut-details-G-gpuMem"></a>
+ **Description:** Describes your GPU memory details\. 
+ **Sample values:** `16`, `32`
+ **Services:**
  + Amazon SageMaker
  + Amazon EC2

## I<a name="product-details-I"></a>

### product/instanceFamily<a name="product-details-I-instanceFamily"></a>
+ **Description:** Describes your Amazon EC2 instance family\. Amazon EC2 provides you with a large number of options across 10 different instance types, each with one or more size options, organized into distinct instance families optimized for different types of applications\. 
+ **Sample values:** `General Purpose`, `Memory Optimized`, `Accelerated Computing` 
+ **Services:**
  + Amazon EC2
  + Amazon RDS
  + Amazon ES
  + Amazon ElastiCache
  + Amazon EMR

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/instanceType<a name="prodcut-details-I-instancetype"></a>
+ **Description:** Describes the instance type, size, and family, which define the CPU, networking, and storage capacity of your instance\. 
+ **Sample values:** `t2.small`, `m4.xlarge`, `t2.micro`, `m4.large`, `t2.large`
+ **Services:**
  + Amazon EC2
  + Amazon RDS
  + Amazon ES
  + Amazon ElastiCache
  + Amazon EMR

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/instanceTypeFamily<a name="product-details-I-instancetypefamily"></a>
+ **Description:** The instance family that is associated with the given usage\. 
+ **Sample values:** `t2`, `m4`, `m3`
+ **Services:**
  + Amazon DocumentDB
  + Amazon RDS

### product/intelAvxAvailable<a name="product-details-I-intelAvx"></a>
+ **Description:** Describes whether your process has the Intel Advanced Vector Extension instruction set\. 
+ **Sample values:** `Yes`, `No`\.
+ **Services:**
  + Amazon EC2

### product/intelAvx2Available<a name="product-details-I-intelAvx2"></a>
+ **Description:** Describes whether your process has the Intel Advanced Vector Extension instruction set two\. 
+ **Sample values:** `Yes`, `No`
+ **Services:**
  + Amazon EC2

### product/intelTurboAvailable<a name="product-details-I-intelturbo"></a>
+ **Description:** Describes whether your core is allowed to use Intel Turbo Technology to increase frequency\. 
+ **Sample values:** `Yes`, `No`
+ **Services:**
  + Amazon EC2

## L<a name="product-details-L"></a>

### product/licenseModel<a name="product-details-L-license"></a>
+ **Description:** Describes the license model for your instance\. 
+ **Sample value:** `license-included`, `bring-your-own-license`, `general-public-license`
+ **Services:**
  + Amazon AppStream
  + Amazon EC2
  + Amazon MQ
  + Amazon Neptune
  + Amazon RDS

### product/location<a name="product-details-L-location"></a>
+ **Description:** Describes the region that your Amazon S3 bucket resides in\.
+ **Sample values:** `Asia Pacific (Mumbai)`, `Asia Pacific (Seoul)`, `Canada (Central)`, `EU (London)`, `US West (Oregon)`
+ **Services:**
  + Amazon EC2
  + AWS Certificate Manager
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/locationType<a name="product-details-L-location"></a>
+ **Description:** Describes the end point of your task\. 
+ **Sample values:** `AWS Region`, `AWS Edge Location`, `Other` 
+ **Services:**
  + Amazon EC2
  + AWS Certificate Manager
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

## M<a name="product-details-M"></a>

### product/maxIopsBurstPerformance<a name="product-details-M-maxiops"></a>
+ **Description:** Describes the max IOPS burst performance of your Amazon EBS volume\. 
+ **Sample value:** `3000 IOPS for volumes <= 1TB`
+ **Services:**
  + Amazon EC2

### product/maxIopsvolume<a name="product-details-M-maxiopsvolume"></a>
+ **Description:** Describes maximum input/output per second of your Amazon EBS volume\. 
+ **Sample value:** `16,000 (maxiops for a General Purpose SSD (gp2))`
+ **Services:**
  + Amazon EC2

### product/maxThroughputvolume<a name="product-details-M-maxthroughput"></a>
+ **Description:** Describes the max network throughput volume of your Amazon EBS volume\. 
+ **Sample values:** `500 MiB/s`, `250 MiB/s`, `1000 MiB/s`, `40 - 90 MB/sec`
+ **Services:**
  + Amazon EC2
  + Amazon SageMaker

## N<a name="product-details-N"></a>

### product/networkPerformance<a name="product-details-N-network"></a>
+ **Description:** Describes the network throughput of your Amazon EC2 instances\. 
+ **Sample values:** `moderate`, `high`, `up to 10 GB`
+ **Services:**
  + Amazon EC2
  + Amazon RDS
  + Amazon ElastiCache
  + Amazon SageMaker
  + AWS Database Migration Service

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/normalizationSizeFactor<a name="product-details-N-normalization"></a>
+ **Description:** Describes the normalization factor of the instance size\. 
+ **Sample values:** `nano - 0.25`, `micro - 0.5`, `medium - 2`, `xlarge - 8`, `16xlarge - 128`
+ **Services:**
  + Amazon DocumentDB
  + Amazon EC2
  + Amazon MQ
  + Amazon Neptune
  + Amazon RDS

## O<a name="product-details-O"></a>

### product/OfferingClass<a name="product-details-O-offering"></a>
+ **Description:** Describes the type of Reserved Instances\. When you purchase a Reserved Instance, you can choose between a Standard or Convertible offering class\. 
+ **Sample values:** `Standard`, `Convertible`
+ **Services:**
  + Amazon DynamoDB
  + Amazon EC2
  + Amazon ElastiCache
  + Amazon ES
  + Amazon RDS
  + Amazon Redshift

### product/operatingSystem<a name="product-details-O-os"></a>
+ **Description:** Describes the operating system of your Amazon EC2 instance\. 
+ **Sample values:** `Amazon Linux`, `Ubuntu`, `Windows Server`, `Oracle Linux`, `FreeBSD`
+ **Services:**
  + Amazon AppStream
  + Amazon EC2
  + Amazon GameLift
  + Amazon Lightsail
  + Amazon WorkSpaces
  + AWS CodeBuild

### product/operation<a name="product-details-O-ops"></a>
+ **Description:** Describes the specific AWS operation that this line item covers\. 
+ **Sample values:** `RunInstances` \(indicates the operation of an Amazon EC2 instance\)
+ **Services:**
  + Amazon EC2
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB
  + Amazon CloudWatch
  + Amazon Redshift

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

## P<a name="product-details-P"></a>

### product/physicalCores<a name="product-details-P-physical"></a>
+ **Description:** Describes the number of physical cores an instance provides\. 
+ **Sample values:** `4`, `8`
+ **Services:**
  + Amazon EC2

### product/physicalProcessor<a name="product-details-P-processor"></a>
+ **Description:** Describes the processor on your Amazon EC2 instance\. 
+ **Sample values: **`High Frequency Intel Xeon E7-8880 v3 (Haswell)`, `Intel Xeon E5-2670`, `AMD EPYC 7571`
+ **Services:**
  + Amazon DocumentDB
  + Amazon EC2
  + Amazon Neptune
  + Amazon RDS
  + AWS Database Migration Service

### product/processorArchitecture<a name="product-details-P-processorarch"></a>
+ **Description:** Describes your processor architecture\. 
+ **Sample values:** `32-bit`, `64-bit`
+ **Services:**
  + Amazon DocumentDB
  + Amazon EC2
  + Amazon Neptune
  + Amazon RDS
  + AWS Database Migration Service

### product/processorFeatures<a name="product-details-P-processorfeature"></a>
+ **Description:** Describes the processor features of your instances\. 
+ **Sample values:** `Intel AVX`, `Intel AVX2`, `Intel AVX512`, `Intel Turbo`
+ **Services:**
  + AWS Database Migration Service
  + Amazon DocumentDB
  + Amazon EC2
  + Amazon Neptune
  + Amazon RDS

### product/ProductFamily<a name="product-details-P-productfamily"></a>
+ **Description:** The category for the type of product\. 
+ **Sample values:** `Alarm`, `AWS Budgets`, `Stopped Instance`, `Storage Snapshot`, `Compute`
+ **Services:**
  + Amazon EC2
  + AWS Certificate Manager
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/ProductName<a name="product-details-P-productname"></a>
+ **Description:** The full name of the AWS service\. Use this column to filter AWS usage by AWS service\. 
+ **Sample values:** `AWS Backup`, `AWS Config`, `Amazon Registrar`, `Amazon Elastic File System`, `Amazon Elastic Compute Cloud`
+ **Services:**

### product/provisioned<a name="product-details-P-provisioned"></a>
+ **Description:** Indicates whether Amazon EBS usage was related to provisioned Amazon EBS storage\. 
+ **Sample values:** `Yes`, `No`
+ **Services:**
  + Amazon EC2
  + Amazon MQ

### product/PurchaseOption<a name="product-details-P-purchase"></a>
+ **Description:** Describes the Amazon EC2 purchasing option\. 
+ **Sample values:** 
  + `On-Demand Instances` – Pay by the second for the instances that you launch
  + `Reserved Instances` – Purchase, at a significant discount, instances that are always available, for a term of one or three years
  + `Scheduled Instances` – Purchase instances that are always available on the specified recurring schedule, for a one\-year term
  + `Spot Instances` – Request unused EC2 instances, which can lower your Amazon EC2 costs significantly
  + `Dedicated Hosts` – Pay for a physical host that is fully dedicated to running your instances and bring your existing per\-socket, per\-core, or per\-VM software licenses to reduce costs
  + `Dedicated Instances` – Pay, by the hour, for instances that run on single\-tenant hardware
  + `Capacity Reservations` – Reserve capacity for your Amazon EC2 instances in a specific Availability Zone for any duration
+ **Services:**
  + Amazon DynamoDB
  + Amazon EC2
  + Amazon ES
  + Amazon ElastiCache
  + Amazon RDS
  + Amazon Redshift

## R<a name="product-details-R"></a>

### product/region<a name="product-details-R-region"></a>
+ **Description:** The geographical area that hosts your AWS services\. Use this field to analyze spend across a particular Region\. 
+ **Sample values:** `eu-west-3`, `us-west-1`, `us-east-1`, `ap-northeast-2`, `sa-east-1`
+ **Services:**
  + Amazon EC2
  + AWS Certificate Manager
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

## S<a name="product-details-S"></a>

### product/sku<a name="product-details-S-sku"></a>
+ **Description:** A unique code for a product\. The SKU is created by combining the `ProductCode`, `UsageType`, and `Operation`\. For size\-flexible RIs, the SKU uses the instance that was used\. For example, if you used a `t2.micro` instance and AWS applied a `t2.small` RI discount to the usage, the line item SKU is created with the `t2.micro`\.
+ **Sample values:** `FFNT87MQSCR328W6`, `VBYCEU494XUAHCA7`
+ **Services:**
  + Amazon EC2
  + AWS Certificate Manager
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/storage<a name="product-details-S-storage"></a>
+ **Description:** Describes the disk storage attached to your instance\. 
+ **Sample values:** `60GB`, `True`, `EBS Only`, `1 x 900 NVMe SSD`, `1 x 150 NVMe SSD`
+ **Services:**
  + Amazon EC2
  + Amazon RDS
  + Amazon Redshift
  + Amazon ES
  + Amazon WorkSpaces

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/storageclass<a name="product-details-S-storageclass"></a>
+ **Description:** Describes the storage class of your Amazon S3 bucket\. 
+ **Sample values:** `Archive`, `General Purpose`, `Infrequent Access`, `Intelligent-Tiering`, `Non-Critical Data`
+ **Services:**
  + AWS Elemental MediaStore
  + AWS Storage Gateway
  + Amazon Cloud Directory
  + Amazon EFS
  + Amazon MQ
  + Amazon S3

## T<a name="product-details-T"></a>

### product/tenancy<a name="product-details-T-tenancy"></a>
+ **Description:** The type of tenancy allowed on the Amazon EC2 instance\. 
+ **Sample values:** `Dedicated`, `Reserved`, `Shared`, `NA`, `Host`
+ **Services:**
  + Amazon EC2
  + Amazon ECS

## U<a name="product-details-U"></a>

### product/usagetype<a name="product-details-U-usage"></a>
+ **Description:** Describes the usage details of the line item\. 
+ **Sample values:** `EU-BoxUsage:c5d.9xlarge`, `EU-BoxUsage:m4.16xlarge`, `SAE1-InstanceUsage:db.t2.medium`, `USW2-AW-SW-19`, `SAE1-BoxUsage:c4.large`, 
+ **Services:**
  + Amazon EC2
  + AWS Certificate Manager
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

## V<a name="product-details-V"></a>

### product/vcpu<a name="product-details-V-vcpu"></a>
+ **Description:** Describes the number of threads concurrently running on a single CPU core\. Amazon EC2 instances support multithreading, which enables multiple threads to run concurrently on a single CPU core\. Each thread is represented as a virtual CPU \(vCPU\) on the instance\.
+ **Sample values:** `8`, `16`, `36`, `72`, `128`
+ **Services:**
  + Amazon EC2
  + Amazon RDS
  + Amazon Redshift
  + Amazon ES
  + Amazon ElastiCache

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 

### product/volumeType<a name="product-details-V-volumetype"></a>
+ **Description:** Describes your Amazon EBS volume types\. 
+ **Sample values:** `Standard`, `General Purpose`, `General Purpose-Aurora`, `Amazon Glacier`, `Amazon SimpleDB – Standard`, 
+ **Services:**
  + Amazon EC2
  + Amazon S3
  + Amazon RDS
  + Amazon DynamoDB
  + Amazon S3 Glacier

    and more\. For the full service list, download [Column\_Attribute\_Service\.zip](samples/Column_Attribute_Service.zip)\. 