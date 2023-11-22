### Questions

1. What is AWS AppSync?
2. What order are NACL rules evaluated in? What happens when a rule is matched?
3. How long do Glacier Expedited Retrievals take?
4. What is the difference between Launch Templates and Launch configurations?
5. What CIDR ranges are supported in a VPC
6. What does Redshift Spectrum allow?
7. What is the default retention for an SQS queue?
8. What is the default EC2 Autoscaling cooldown period?
9. What is the difference between Geolocation and Geoproximity routing?
10. What type of VIF is needed for a VPN connection over DX?
11. What is the difference between awsvpc and Bridge network mode in ECS?
12. Does AWS Compute optimiser work on ec2 instances or lambdas or both?
13. EFS General Purpose vs Max IO differences
14. When should you use an NLB over an ALB? (5 reasons)
15. What is the max lambda execution time?
16. EC2RescueTool is used to recovery dodgy EC2 instances. Can it be used to recover EC2 instances in an automated way?
17. Do you need to re-provision an entire cluster placement group to add one instance?
18. Can reserved instances be provisioned in multiple AZs?
19. Can a DX be linked to a transit gateway in a different region?
20. Which of the following has security groups? NLB, ALB
21. What are the sizes of RCU and WCUs in DynamoDB?
22. What is AWS AppStream?
23. How does a WAF rate based rule work?
24. Would Pilot Light DR have a running database in secondary region or a snapshot?
25. In a RAM share, do we share subnets or prefix list?
26. Can a RDS instance be un-encrypted in place via a snapshot or read replica?
27. What is a good place to get pre-defined WAF rules?
**28. What AWS services should be used to enable alerting of reserved instance usage?**
29. Does Athena support ODBC?
30. Does a WAF Web ACL provide DDoS attack mitigation?
31. Can an S3 pre-signed URL provide access to multiple files?
**32. What are two ways to improve performance with Athena?**
33. What does ECS instance draining do? Does it affect existing running tasks?
34. What is the ECS task role? What is the ECS execution role?
**35. What is the difference between a regional and edge optimised API Gateway endpoint?**
36. Are AMI images region specific?
37. What is the difference between SS3-S3, SSE-KMS and SSE-C?
38. Can CloudFront improve performance of dynamically generated content?
39. Do we need an endpoint to get to EFS?
40. Do AWS VPCs support multicast?
41. Are Elastic IPs configured per AZ or per account / per region?
42. When is data on an instance store volume lost?
**43. For which AWS services should a R53 Alias record be used?**
44. For which AWS services should A and CNAME records be used?
**45. What is CloudFront origin failure?**
**46. What is a 504 error from CloudFront?**
47. What are the problems with a low maxReceiveCount value in an SQS queue?
48. What is AWS CloudSearch? How is it different to Kendra?
49. What service has a managed rule to check if EC2 instances are using an approved AMI?
50. Do we need to use CloudFront add caching in front of API Gateway?
**51. How do you stop instances from being terminated in an ASG?**
52. Can CloudHSM be deployed to multiple AZs?
53. Do SCPs affect service linked roles?
**54. How do we disable RI sharing in an AWS organisation?**
55. What is an inbound resolver used for?
56. What is an outbound resolver used for?
57. Can AWS Rekognition run on an AWS outpost?
58. How many messages per second can an SQS FIFO queue handle?
59. What is a Layer, and Custom Receipe in an OpsWork Stack?
60. What is reserved concurrency for a Lambda?
61. What is provisioned concurrency in Lambda?
62. What is the header for S3 API calls that should be encrypted?
63. What type of certificate is supported between Viewers and CF?
64. What type of certificate is supported between CF and ELB?
65. What type of certificate is supported between CF and non-elb resources?
66. How much of a delay can there be with S3 Cross Region replication?
67. What do you need in order to successfully use cross region Redshift copy feature?
68. Does the PowerUsers IAM policy allow Organization view permissions?
69. What do you need to connect VPCs in multiple regions to a DX?
70. What two methods does SES support to establish a TLS connection?
71. Do we use Compute Optimiser or Migration hub to estimate EC2 VM size before a migration?
72. Does Athena have built in integration with AWS Migration Hub?
73. Is it a good idea to use Cross Region Replication to improve performance for global users?
74. What is S3 storage lens?
75. How can CloudWatch custom error response be used to show an error page from an S3 bucket when S3 isn't where the main application is hosted?
76. Can an SQS queue be used as the input for a step function?
77. Does Glacier have a built in search function to help retrieve data?
78. When should you use AWS Global Accelerator over CloudFront?
79. What is the IO limit for GP2/GP4 EBS volumes?
80. What is the IO limit for IO1/IOS EBS volumes?
81. What's the difference between Cluster, Spread and Partition placement groups?
82. What are AWS Config conformance packs?
83. Can you have RDS backups and AWS backups turned on for the same RDS instance?
84. Can you use SMS to migrate physical servers?
85. What is the retrieval time window for Glacier Flexible Retrieval?
86. What is the retrieval time window for Glacier Deep Archive?
87. What Glacier tier is Intelligent Tiering Archive Access equivalent to?
88. How much does it cost to store parameters in Systems Manager Parameter Store?
89. Does Session Manager offer port forwarding?
90. Does Session Manager offer connection auditing?
91. Can you assign an IAM role to a CloudFront distribution?
92. Does RDS storage autoscaling affect performance?
93. What is the storage capacity of a SnowCone in NFS and SSD mode?
94. What is the storage capacity of a Snowball Edge in HDD and NVMe mode?
95. Which Redis flavour supports a multi-threaded architecture?
96. What is a Target Tracking policy?
97. What is a Step Scaling policy?
98. What is a Resource Group?
99. Can you use SCPs to enforce tag use in an organization?
100. What is the bandwidth limit for a single tunnel of a site-to-site VPN connection?

### Answers

1. A way to manage Serverless GraphQL APIs... alternative to API Gateway for this use case
2. Lowest to highest... rule processing stops
3. 1-5 minutes
4. LC are the 'old' way, can't use them to spin up an instance manually, can't update them at all (unlike LT which can be versioned), LT provides more EC2 options, recommend to use LTs
5. /16 to /28
6. Querying directly from an S3 bucket
7. 4 days
8. 5 minutes
9. Geolocation is based on location of users (e.g. block countries), Geoproximity is based on location of resources (performance)
10. Public VIF
11. awsvpc allocates ENI to task and primary IPv4 address, behaves like EC2 instance, Bridge mode uses docker's virtual bridge networking, e.g. host port 80 maps to 3000 on container
12. EC2 instances and Lambda
13. Max IO is previous gen, has higher latencies per operation, not recommended over GP mode
14. NLB when dealing with millions of connections, or if dealing with non HTTP(s) traffic, or if we need SSL passthrough, PrivateLink, Static IP needed (NLB supports ALB doesn't)
15. 15 minutes
16. Yes
17. No, an instance can join an existing placement group without requiring the whole thing to be restarted
18. No, reserved instances are AZ specific
19. No, DX only goes to TGW for multiple VPCs in same region, otherwise we need a VPGW
20. ALBs only
21. 4KB and 1KB respectively
22. Streaming virtual desktops
23. A rate-based rule counts incoming requests and rate limits requests when they are coming at too fast a rate
24. Running database
25. Prefix list
26. No the instance needs to be recreated and the data re-imported to disable encryption
27. AWS Marketplace
28. AWS Budgets
29. Yes
30. No, need Shield Standard or Advanced for this
31. No, only to a single file
32. Store data in columnar format (e.g. Parquet or ORC), Use Apache Hive partitioning using a key that includes a date
33. Stops new tasks being scheduled on a node, doesn't affect existing ones
34. Task role relates to the running container (executing your actual code), execution role relates to getting the container running (e.g. pulling an image)
35. Regional doesn't go through CloudFront (it's for clients in the same region) while edge-optimized does go through CF
36. Yes
37. SSE-C uses a customer provided key, SSE-KMS uses a KMS managed key, SSE-S3 uses a KMS managed key
38. Yes, performance can be improved for both static and dymanic content 
39. No it's accessible in the VPC
40. No, has to be done at OS layer
41. Per account, per region
42. Data is lost on instance failure, termination and when instance is stopped
43. ELB, CloudFront, and S3
44. EC2 and RDS respectively
45. We create an origin group and set up a primary and secondary origin. If the primary origin is unavailable the secondary takes over
46. 504 means traffic is blocked to the origin by a firewall or security group, or if the origin isn't accessible on the internet
47. A failure might occur due to intermittent connectivity issues, and get sent straight to DLQ despite there being no actual operational issues
48. Cloudsearch is based on keyword engine, Kendra is Enterprise search targetted toward searching unstructured data
49. AWS Config
50. No, API Gateway has its own caching abilities
51. Advanced Configurations -> Suspended Processes -> Terminate
52. No, single AZ only
53. No, they don't
54. Disable it in Billing and Cost Management console for which ever accounts we don't want to share with
55. On-prem into AWS dns resolution
56. Internal AWS DNS resolution to an external DNS provider
57. No
58. 3000 per second
59. Layer is one environment, Custom recipe is 
60. Reserved concurrency creates a pool of requests that can only be used by its function, and also prevents its function from using unreserved concurrency
61. Provisioned concurrency initializes a requested number of execution environments so that they are prepared to respond to your function's invocations
62. x-amz-server-side​-encryption​-customer-algorithm
63. 3rd party or ACM issued
64. 3rd party of ACM issued
65. 3rd party
66. 15 minutes
67. Snapshot copy grant for the master key
68. Yes
69. VGW in each VPC, VIF to DGW, DX connected to DGW
70. STARTTLS and TLS wrapper
71. AWS Migration Hub -- Compute Optimizer is for stuff that's already running in the account
72. Yes
73. No use transfer acceleration instead
74. Org wide S3 storage visibility / analytics feature
75. Upload error page to S3 bucket, Add S3 bucket as an additional origin, enable CF custom error response for specific error code
76. No chance
77. Yeah right
78. For non http/https traffic
79. 16000
80. 64000
81. Cluster = same underlying hardware, Spread = Different underlying hardware, Partition = Group instances and spread across different hardware
82. A collection of AWS Config rules and remediation actions that can be easily deployed as a single entity in an account and a Region or across an organization
83. No, you must turn off RDS automated backups to use AWS Backup to manage backups.
84. No SMS doesn't support physical servers, use Application Migration Service instead
85. 3-5 hours
86. Within 12 hours
87. Glacier Flexible Retrieval
88. Free
89. Yes, Session Manager offers the benefit of port forwarding
90. Yes, Session Manager also logs and audits session activity
91. No, you cannot assign an IAM role to a CloudFront distribution
92. No
93. 8TB, 14TB
94. 80HDD or 210TB NVMe
95. Memcached
96. Target tracking policy lets you specify a scaling metric and metric value that your auto scaling group should maintain at all times
97. Step Scaling further improves the features of simple scaling. Step scaling applies “step adjustments” which means you can set multiple actions to vary the scaling depending on the size of the alarm breach
98. A way of searching for AWS resources by Tags and enforcing Tag Policies
99. Yes
100. 1.25Gbps