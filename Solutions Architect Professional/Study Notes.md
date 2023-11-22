**AWS Glue** - Job bookmarks allow jobs to resume if interrupted

**Route 53** - Remember that an Active-Active Failover uses all available resources all the time without a primary nor a secondary resource.

**S3 Select** enables applications to retrieve only a subset of data from an object by using simple SQL expressions. You can perform S3 Select to query only the necessary data inside the CSV files based on the bucket’s name and the object’s key.

Use **AppSync** with DynamoDB to make it easy for you to build collaborative apps that keep shared data updated in real-time. AWS AppSync allows your applications to access exactly the data they need. Create a flexible API to securely access, manipulate, and combine data from multiple sources. Pay only for requests to your API and for real-time messages delivered to connected clients.

To preseve **EBS volumes** on Terminate, set the value of `DeleteOnTermination`attribute of the EBS volumes to `False`.

**Glacier** **Expedited retrievals** allow you to quickly access your data when occasional urgent requests for a subset of archives are required. For all but the largest archives (250 MB+), data accessed using Expedited retrievals are typically made available within 1–5 minutes. **Provisioned capacity** ensures that your retrieval capacity for expedited retrievals is available when you need it.

**A _delete marker_ in Amazon S3** is a placeholder (or marker) for a versioned object that was specified in a simple `DELETE` request. A simple `DELETE` request is a request that doesn't specify a version ID. Because the object is in a versioning-enabled bucket, the object is not deleted. Delete Marker != Permanently Deleted

**RDS storage autoscaling** = Minimal performance impact. Increasing disk space - although this will solve the problem of low disk space, increasing the allocated storage might cause performance degradation during the change.

**VPC CIDR range:** The allowed block size in VPC is between a /16 netmask (65,536 IP addresses) and /28 netmask (16 IP addresses) and not /27 netmask.

**S3 Transfer Acceleration** leverages Amazon CloudFront’s globally distributed AWS Edge Locations. As data arrives at an AWS Edge Location, data is routed to your Amazon S3 bucket over an optimized network path.

**NACL rules** are evaluated starting with the lowest numbered rule. As soon as a rule matches traffic, it’s applied immediately regardless of any higher-numbered rule that may contradict it.

Fundamentally, **Base64 is used to encode binary data as printable text**. This allows you to transport binary over protocols or mediums that cannot handle binary data formats and require simple text.

**AWS Well Architected Tool** (AWS WA Tool) is a service in the cloud that provides a consistent process for measuring your architecture using AWS best practices. AWS WA Tool helps you throughout the product lifecycle by:
- Assisting with documenting the decisions that you make
- Providing recommendations for improving your workload based on best practices
- Guiding you in making your workloads more reliable, secure, efficient, and cost-effective

**AWS Data Pipeline (deprecated service)** is a web service that helps you reliably process and move data between different AWS compute and storage services, as well as on-premises data sources, at specified intervals. With AWS Data Pipeline, you can regularly access your data where it’s stored, transform and process it at scale, and efficiently transfer the results to AWS services such as Amazon S3, Amazon RDS, Amazon DynamoDB, and Amazon EMR.

**Amazon SWF** provides useful guarantees around task assignments. It ensures that a task is never duplicated and is assigned only once.

**Amazon Redshift Spectrum** Amazon Redshift also includes Redshift Spectrum, allowing you to directly run SQL queries against exabytes of unstructured data in Amazon S3.

**An Elastic Fabric Adapter (EFA)** is a network device that you can attach to your **Linux** Amazon EC2 instance to accelerate High Performance Computing (HPC) and machine learning applications. Elastic Fabric Adapter (EFA) are not supported on Windows instances. Use ENA instead. Amazon EC2 provides enhanced networking capabilities through the Elastic Network Adapter (ENA).

**CloudWatch alarm actions:** You can create alarms that automatically stop, terminate, reboot, or recover your EC2 instances using Amazon CloudWatch alarm actions.

**Amazon SQS** automatically deletes messages that have been in a queue for more than the maximum message retention period. The default message retention period is 4 days.
You can increase the message retention period to a maximum of 14 days using the [SetQueueAttributes](http://docs.aws.amazon.com/AWSSimpleQueueService/latest/APIReference/API_SetQueueAttributes.html) action.

**Amazon S3 now provides increased performance** to support at least 3,500 requests per second to add data and 5,500 requests per second to retrieve data, which can save significant processing time for no additional charge. Each S3 prefix can support these request rates, making it simple to increase performance significantly.

**AppSync pipeline resolvers** offer an elegant server-side solution to address the common challenge faced in web applications—aggregating data from multiple database tables. Instead of invoking multiple API calls across different data sources, which can degrade application performance and user experience, AppSync pipeline resolvers enable easy retrieval of data from multiple sources with just a single call.

**AWS Wavelength** combines the high bandwidth and ultralow latency of 5G networks with AWS compute and storage services so that developers can innovate and build a new class of applications.

**Amazon EKS uses IAM to provide authentication** to your Kubernetes cluster, but it still relies on native Kubernetes Role-Based Access Control (RBAC) for authorization.

**AWS AppSync** is a serverless GraphQL and Pub/Sub API service that simplifies building modern web and mobile applications. With AWS AppSync, you can use custom domain names to configure a single, memorable domain that works for both your GraphQL and real-time APIs.

**Amazon CloudWatch Application** Insights facilitates observability for your applications and underlying AWS resources. It helps you set up the best monitors for your application resources to continuously analyze data for signs of problems with your applications.

When you create an **encrypted EBS volume** and attach it to a supported instance type, the following types of data are encrypted:
– Data at rest inside the volume
– All data moving between the volume and the instance
– All snapshots created from the volume
– All volumes created from those snapshots

**AWS Transit Gateway** also enables you to scale the IPsec VPN throughput with equal-cost multi-path (ECMP) routing support over multiple VPN tunnels. A single VPN tunnel still has a maximum throughput of 1.25 Gbps. If you establish multiple VPN tunnels to an ECMP-enabled transit gateway, it can scale beyond the default limit of 1.25 Gbps.

**Application Load Balancers support Weighted Target Groups routing.** With this feature, you will be able to do weighted routing of the traffic forwarded by a rule to multiple target groups.

By default, **CloudTrail event log files are encrypted** using Amazon S3 server-side encryption (SSE).

**Aurora Failover** - If you have an Amazon Aurora Replica in the same or a different Availability Zone, when failing over, Amazon Aurora flips the canonical name record (CNAME) for your DB Instance to point at the healthy replica, which in turn is promoted to become the new primary. Start-to-finish failover typically completes within 30 seconds. If you are running Aurora Serverless and the DB instance or AZ becomes unavailable, Aurora will automatically recreate the DB instance in a different AZ.
If you do not have an Amazon Aurora Replica (i.e., single instance) and are not running Aurora Serverless, Aurora will attempt to create a new DB Instance in the same Availability Zone as the original instance. This replacement of the original instance is done on a best-effort basis and may not succeed, for example, if there is an issue that is broadly affecting the Availability Zone.

**Lambda function URLs** are HTTP(S) endpoints dedicated to your Lambda function. You can easily create and set up a function URL using the Lambda console or API. Once created, Lambda generates a unique URL endpoint for your use.

For clusters running the **Memcached engine,** ElastiCache supports Auto Discovery—the ability for client programs to automatically identify all of the nodes in a cache cluster, and to initiate and maintain connections to all of these nodes.

If you receive a capacity error when launching an instance in a **placement group** that already has running instances, stop and start all of the instances in the placement group, and try the launch again. Restarting the instances may migrate them to hardware that has capacity for all the requested instances.

The scenario requires you to select a cost-effective service that does not have a **minimum storage duration** since the data will only last for 12 hours. Among the options given, only Amazon S3 Standard has the feature of no minimum storage duration.

**IAM database authentication** provides the following benefits:
– Network traffic to and from the database is encrypted using Secure Sockets Layer (SSL).
– You can use IAM to centrally manage access to your database resources, instead of managing access individually on each DB instance.
– For applications running on Amazon EC2, you can use profile credentials specific to your EC2 instance to access your database instead of a password, for greater security

**Amazon Kinesis Data Streams** supports _resharding_, which lets you adjust the number of shards in your stream to adapt to changes in the rate of data flow through the stream. Resharding is considered an advanced operation.

**CloudFront EC2** The scenario uses an EC2 instance as an origin. Take note that we can also use an EC2 instance or a custom origin in configuring CloudFront. To achieve high availability in an EC2 instance, we need to deploy the instances in two or more Availability Zones. You also need to configure the instances to be part of the origin group to ensure that the application is highly available.

In **Amazon Pinpoint,** an _event_ is an action that occurs when a user interacts with one of your applications, when you send a message from a campaign or journey, or when you send a transactional SMS or email message. For example, if you send an email message, several events occur:

**What is the difference between Amazon Inspector and Amazon GuardDuty?** Amazon Inspector provides you with security assessments of your applications settings and configurations on your EC2 instances while Amazon GuardDuty helps with analyzing your entire AWS environment for potential threats.

**AWS CloudTrail** is a service that enables governance, compliance, operational auditing, and risk auditing of your AWS account. CloudTrail provides event history of your AWS account activity, including actions taken through the AWS Management Console, AWS SDKs, command line tools, API calls, and other AWS services. This event history simplifies security analysis, resource change tracking, and troubleshooting.

**AWS Proton** allows you to deploy any serverless or container-based application with increased efficiency, consistency, and control. You can define infrastructure standards and effective continuous delivery pipelines for your organization. Proton breaks down the infrastructure into environment and service (“infrastructure as code” templates).

Objects must be stored for **at least 30 days** in the current storage class before you can transition them to STANDARD_IA or ONEZONE_IA. In this scenario, you can set a lifecycle policy in the bucket to transition to S3 – Standard IA after 30 days or alternatively, you can directly transition your data to Glacier after one week (7 days).

If you recall, data transferred between Amazon EC2, Amazon RDS, Amazon Redshift, Amazon ElastiCache instances, and Elastic Network Interfaces in the same Availability Zone is free. Instead of using the public network to transfer the data, you can use the private network to reduce the overall data transfer costs.

**AWS Lambda** Resource-based policies let you grant usage permission to other AWS accounts on a per-resource basis. You also use a resource-based policy to allow an AWS service to invoke your function on your behalf. Execution roles grant Lambda functions access to other AWS services.

**AWS Snowball** uses secure, rugged devices so you can bring AWS computing and storage capabilities to your edge environments, and transfer data into and out of AWS. The service delivers you Snowball Edge devices with storage and optional Amazon EC2 and AWS IOT Greengrass compute in shippable, hardened, secure cases. With AWS Snowball, you bring cloud capabilities for machine learning, data analytics, processing, and storage to your edge for migrations, short-term data collection, or even long-term deployments. AWS Snowball devices work with or without the internet, do not require a dedicated IT operator, and are designed to be used in remote environments.

**DynamoDB PITR** allows you to create continuous backups of your table and restore it to any specific point in time within a retention period of up to 35 days. In the scenario, you can use PITR to achieve the recovery point objective of one hour by restoring the table to a state just before any corruption occurs.

**In API Gateway, A Regional API** is an API deployed to a specified Region and intended to serve clients, such as EC2 instances, in the same AWS Region. API requests are targeted directly to the Region-specific API Gateway API without going through any CloudFront distribution. For in-Region requests, a Regional endpoint bypasses the unnecessary round trip to a CloudFront distribution.

**Amazon Kinesis Data Streams (KDS)** is a massively scalable and durable real-time data streaming service. KDS can continuously capture gigabytes of data per second from hundreds of thousands of sources. You can use an AWS Lambda function to process records in Amazon KDS. By default, Lambda invokes your function as soon as records are available in the stream. Lambda can process up to 10 batches in each shard simultaneously.

**Aurora Global DB - Switchover** This operation was previously called "managed planned failover." Use this approach for controlled scenarios, such as operational maintenance and other planned operational procedures. Because this feature synchronizes secondary DB clusters with the primary before making any other changes, RPO is 0 (no data loss).

**Intel Hyper-Threading Technology** makes a single physical processor appear as multiple logical processors. Most HPC applications will benefit from disabling hyperthreading.

**AWS Backup** can automatically back up data that is in S3 buckets, Storage Gateway volumes, EBS volumes, EFS file systems, and RDS databases.

**Organizations** is an account-management service in which trusted access allows supported AWS services such as **AWS Config** to perform tasks across accounts in the organization. AWS Config also supports a delegated administrator that can implement conformance packs across multiple accounts and achieve consistent compliance without any unauthorized modifications.

https://docs.aws.amazon.com/organizations/latest/userguide/orgs_integrate_services_list.html

**MemoryDB for Redis** is a durable, in-memory managed database for workloads that require an ultra-fast, primary database. https://docs.aws.amazon.com/memorydb/latest/devguide/what-is-memorydb-for-redis.html

**AWS Replication Agent** is part of AWS Application Migration Service. The AWS Replication Agent performs an initial block-level read of the content of any volume attached to the server and replicates it to the replication server.

**Route 53 Application Recovery Controller** routing controls provide simple on/off switches that give you the ability to direct traffic from one replica to another. These routing controls are based on Route 53 health checks that you configure. The Route 53 health checks become healthy or unhealthy by toggling routing controls. Based on multiple metrics from various application components, you can automate the toggling of these routing controls with CloudWatch alarms and Lambda functions. For more information about Route 53 Application Recovery Controller routing controls, see [Routing Control in Amazon Route 53 Application Recovery Controller](https://docs.aws.amazon.com/r53recovery/latest/dg/routing-control.html).

Virtual Private Gateway (VGW) vs Direct Connect Gateway (DGW) vs Transit Gateway (TGW)

![[Images/vgw_dgw_tgw.png]]

Organizations provides centralized account management in a hierarchical fashion through OUs and policies. **You should create separate security accounts for logging, security tooling, read-only access, and emergency access (break-glass access), especially for advanced organizations.**

Tag policies help standardize tags across resources in an organization's accounts. You can use Resource Groups to detect noncompliant resources and generate a report so that you can make corrections. **You can use SCPs to enforce the use of tags within the organization.** https://docs.aws.amazon.com/ARG/latest/userguide/resource-groups.html

FIFO queues can enhance message transmission between applications when the order of operations and events is critical or when duplicates are not acceptable. **A custom metric to scale based on an acceptable backlog per instance would base the scaling on the system load in the SQS queue.** The custom metric is calculated based on the approximate number of messages, processing latency, and the number of running EC2 instances. This solution provides more accurate scaling. An SQS Queue's ApproximateNumberOfMessagesVisible metric will not change in proportion to the size of the Auto Scaling group that processes messages.