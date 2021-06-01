# Technology 

1. [Deploying and Operating in AWS](#methods-of-deploying-and-operating-in-the-aws-cloud)
2. [AWS Globabl Infrastructure](#aws-global-infrastructure)
3. [Core AWS Services](#core-aws-services)
4. [Resources for Technology Support](#resources-for-technology-support)

---

## Methods of Deploying and Operating in the AWS cloud

* Main principles: Automate, Automate, Automate 

### Elastic Beanstalk

* High level deployment, get app to the web in minutes
* Capacity provisioning, load balancing, application health monitoring are all managed
* Platform configuration defines infrastructure and software stack to use for environment 
* Elastic Beanstalk provisions AWS resources, including EC2 instances, CloudWatch alarms, load balancers, security groups, etc

### CloudFormation

* CloudFormation helps model and set up AWS resources, users can focus on application running in AWS
* Templates describe all resources that are desired
* CloudFormation manages provisioning and configuring resources 

### OpsWorks

* Configuration management services
* Helps configure and operate applications in a cloud enterprise by using Chef
* AWS OpsWorks Stacks / AWS OpsWorks for Chef Automate

#### OpsWorks Stacks

* Deploy and monitor applications in stacks
* Does not require nor create Chef servers, performs some functions of Chef server 
* Monitors instance health, provisions new instances -> Auto Healing and Auto Scaling

#### OpsWorks for Chef Automate

* Allows creation of AWS-managed Chef servers that include Chef Automate premium features, and use of Chef DK / Chef tooling to manage them
* Manages both Chef automate Server and Chef Server software on single instance

### CodeCommit

* Fully-managed source control service
* Hosts secure and highly scalable Git repos
* Integrates wiht CodePipeline and CodeDeploy to streamline development and release process

### CodePipeline

* CI/CD service for fast & reliable application/infrastructure updates
* Builds, tests, and deploys code every time there is a code change, based on release process models defined

### CodeDeploy 

* Automates code and software deployments to any instance (EC2 or instances on-premises)
* Allows for rapid release of new features, helps avoid downtime during app deployment, and handles complexity of updating applications 

### Elastic Container Server (ECS)

* Highly scalable, high performance container management service
* Supports Docker containers
* Run applications on cluster of EC2 instances 
* Removes need to install, operate and scale own cluster management infrastructure 

### Non-AWS Solutions

#### Infrastructure as Code

* Terraform
* Salt Stack
* Ansible

#### Configuration Management

* Chef
* Puppet
* Ansible

#### Continious Integration

* Jenkins
* TeamCity


#### Hosted Version Control Repos

* GitHub
* GitLab
* BitBucket

### General Principles 

#### Good Practice

* Provision infrastucture from code
* Deploy artifacts automatically from version control
* Configuration managed from code & applied automatically
* Scale infrastructure automatically 
* Monitor every aspect of pipeline and infrastructure (CloudWatch)
* Logging for every action (CloudWatch Logs & CloudTrail)
* Use variables, no hard coded values
* Use tagging with automation to provide more insights on what has been provisioned

#### Updating Stack

* Update AMIs and then deploy new environment from them
* Use CI tools to deploy code to existing environments
* Blue/green method -> Blue = production environment, green = new version. On upgrade, redirect traffic from blue to green

---

## AWS Global Infrastructure

* AWS cloud spans 80 Availability Zones within 25 geographic regions
* Plans for 18 more availability zones and 6 more AWS regions 

### Regions and Availability Zones

* A region is a physical location with multiples AZs 
* AZs consist of one or more discrete data centres, with redundant power and networking, housed in separate facilities located on stable flood plains 
* AZs ensure production applications and databases are highly available, fault tolerance, and scalable

### High Availability through Multiple Availability Zones

* Can deploy applications across multiple AZs within same region to ensure fault tolerance and low latency
* AZs connected to each other with fast and private fiber-optic network -> enables apps to automatically fallover between AZs without interruption

### Improving Avilability by Deploying in Multiple Regions

* Increase redundancy and fault tolerance by replicatng data between regions
* Can use both private and public networks to provide additional layer of business continuity & provide low latency access worldwide

### Compliance and Data Residency Requirements

* Retain complete control & ownership over region data is physically located 

### Edge Locations

* AWS sites deployed in major cities/highly populated areas
* CloudFront, Lambda@Edge use edge locations to cache data and reduce latency for end user access
* Edge locations used as a global Content Delivery Network

---

## Core AWS Services

* **Compute**: EC2, Lambda
* **Storage**: S3
* **Database**: RDS
* VPC, Route 53, SNS, SQS, ELB
* CLI, SDKs, AWS Trusted Advisor, AWS Cost Calculator

### EC2 

* secure, reliable, resizable compute capacity in the cloud

#### Instance Types

##### General Purpose

* **T2**: burstable performance -> baseline level of CPU performance with ability to burst above baseline
* **M4**: latest generation, balance of compute, memory and network resources 

##### Compute Optimised

* **C4**: latest generation, highest performing processors and lowest price/compute performance in EC2

##### Memory Optimised

* **X1**: large-scale, enterprise-class, in-memory apps & high performance databases, lowest price per GiB of RAM
* **R4**: memory intensive applications, better price per GiB than R3. RAM sizes step below X1s

##### Accelerated Computing

* **P2**: general purpose GPU compute applications 
* **G3**: graphic intensive applications, step below P2s
* **F1**: customisable hardware acceleration with field programmable gate arrays (FPGAs)

##### Storage Optimised

* **I3**: high I/O instances. Includes High Storage Instances with Non-Volatile Memory express (NVMe) SSD backed instance storage -> optimised for low latency, high random I/O performance, high sequential read throughput, high IOPS at low cost 
* **D2**: dense storage instances, up to 48TB of HDD based local storage. High disk throughput, lowest price per disk throughput performance on EC2

#### Pricing 

* free to try, can pay for On-Demand, Reserved Instances, Spot Instances, Per-Second billing
* can pay for Dedicated Hosts, which provide EC2 instance capacity on physical servers dedicated for your use

##### On-Demand

* pay for computing capacity per hour or per second, depends on which instances being ran. No long term committments or upfront payments needed

##### Spot Instances

* can bid on spare EC2 compute capacity for up to 90% off On-Demand price. For applications with flexible start/end times, apps that are only feasible at very low compute prices, or users with urgent compute needs for large amounts of additional capacity 

##### Reserved Instances

* up to 75% discount from On-Demand. For applications with a steady state or predictable usage, can commit to 1 or 3 year period. 

##### Per-Second Billing

* pay only for what is used. Takes cost of usused minutes and seconds in an hour off bill, can focus on improving application instead of maximising usage to the hour 

#### Security Groups 

* virtual firewall that controls traffic for one or more instances
* one or more security groups are associated with an instance upon launch
* rules decide which traffic allowed to or from associated instances
* rules can be modified at any time, new rules automatically applied to all instances associated with security group


### S3

* object storage designed to retrieve any amount of data from anywhere
* 11 9s of durability, comprehensive security and compliance capabilities
* gives customers flexibility in how they manage data for cost optimisation, access control & compliance 
* only cloud storage solution with query-in-place functionality

#### Storage Classes

* different storage classes with different intended use cases. 
* lifecycle transitions can be used to move data between given classes, given specified events

##### S3 Standard

* general-purpose storage of frequently accessed data
* low latency and high throughput for wide variety of use cases
* no retrieval fee, minimum object size or minimum storage duration

##### S3 Standard - Infrequent Access

* long-lived, infrequently accessed data, rapid access to data retained
* high durability, throughput, low latency 
* low price per GB of storage, low GB retrieve fee 

##### Amazon Glacier

* long-term archive
* secure, durable & extremely low-cost storage for data archiving
* can reliably store any amount of data at a price competitive with on=premises solutions
* provides three options for access to archives, from minutes to several hours


### RDS 

* Amazon Relational Database Service 
* easy to set up, operate & scale a relational database in the cloud 
* provides cost-efficiency & resizable capacity while automating time-consuming admin tasks such as hardware provisioning, database setup, patching & backups
* provides several database instance types -> optimised for memory, performance or I/O
* provides six database engines 
	1. Amazon Aurora
	2. PostgreSQL
	3. MySQL
	4. MariaDB
	5. Oracle
	6. Microsoft SQL Server
* encryption at rest and in transist, using keys managed through KMS 
* backups are automated, user-initated snapshots are availabile, database software updated automatically 


### AWS Database Migration Service

* source database remains fully operational during migration -> minimizes downtime 
* can migrate data to and from most widely used commerical & open-source database engines 
* homogenous migrations such as Oracle to Oracle
* heterogenous migrations such as Oracle -> Amazon Aurora, Microsofr SQL Server -> MySQL
* allows data to be streamed to Redshift/Dynamo DB/S3 from sources such as Aurora, PostgreSQL, MySQL, MariaDB, Oracle, SAP ASE, SQL Server, MongoDB
	* enables consolodation and analysis of data in petabyte-scale data warehouse
* can be used for continuous replication with high-availability


### AWS Schema Conversion Tool

* makes heterogenous database migrations predictable by automatically converting source database schema & database code objects to a format compatible with target database 
* objects that cannot be automatically coverted are clearly marked so they can be manually converted to complete the migration 
* application source code can be scanned for embedded SQL statements, which are converted as part ofa database schema conversion project 
* source database can be on-premises, in Amazon RDS or EC2
* target database can be Amazon RDS or EC2 


### Lambda

* lets you run code without provisioning or managing servers
* only pay for compute time consumed, no charge when code is not running 
* can run code for virtually any type of application, all with zero administration 
* automatically scales application by running code in response to triggers
* code runs in parallel and processes each trigger individually, scales precisely with size of workload
* charged for every 100ms code executes, and the number of times code is triggered 


### Route 53 

* highly available and scalable cloud DNS web service
* can configure DNS health checks to route traffic to healthy endpoints, or to independently monitor health of application and its endpoints
* Route 53 Traffic flow allows traffic to be managed globablly through variety of routing types
	1. Latency Based Routing
	2. Geo DNS
	3. Geoproximity
	4. Weighted Round Robin 
* routing types can be combined with DNS Failover to enable low-latency, fault-tolerant architectures
* Route 53 Traffic Flow's visual editor allows you to manage how end-users are routed to application endpoints, whether in a single region or distrubted around the globe 
* provides Domain Name Registration, can purchase and manage domain names and Route 53 will automatically configured DNS settings for domains 
* integrated with Elastic Load Balancing (ELB)


### SNS

* Simple Notification Service 
* pub/sub messaging and mobile notifications for microservices, distributed systems, and serverless applications 
* SNS mobile notifications make it simple and cost effective to send push notifcatinos to iOS, Android, Fire OS, Windows, & Baidu-based devices 
* supports HTTP/HTTPS, Email/Email-JSON, SQS queues, Lambda functions


### Amazon DevPay

* simple-to-use online billing & account management service
* allows businesses to sell applcations that are built in, or run on top of AWS 


### Amazon QuickSight

* fast business analytics service
* use to build visualisations, perform ad hoc analysis, quickly get business insights from data
* can access data from multiple sources, uplaod files or connect to AWS data sources or external databases 


### SQS

* fully managed message queuing service
* can decouple & scale microservices, distributed systems, serverless applications 
* eliminates complexity & overhead associated with managing and operating message oriented middleware
* send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available 
* **Standard queues** offer maximum throughput, best-effort ordering & at-least-once delivery
* **SQS FIFO** queues guarantee messages processed EXACTLY once, and in EXACT ORDER as they were sent 


---

## Resources for Technology Support

* three different support plans: Developer Support, Business Support, Enterprise Support

### AWS Support Ticket 

* can create a ticket if on a support plan
* faster to get support via console & create request

### Technical Account Manager 

* primary point of contact
* provides guidance, architectural review, ongoing communication to keep account holder informed and well informed as they plan, deploy & proactively optimise solutions
* dedicated voice within AWS that serves as technical point of contact & advocate
* proactive guidance & best practices to help optimise AWS environment 
* orchestration and access to breadth and depth of technical expertise across full range of AWS 

### Trusted Advisor 

* online resource that helps provision resources following best practices
* helps reduce costs, increase performance & fault tolerance, improve security 
* four core checks availabile to all AWS customers, full use of AWS Trusted Advisor available to Business/Enterprise support 

### AWS Whitepapers

* comprehensive list of technical AWS whitepapers, topics such as architecture, security & economics 
* authored by AWS Team, independent analysts, AWS Community (Customers or Partners)

### AWS Service Health Dashboard

* general view of health of all AWS Services
* status.aws.amazon.com

### AWS Personal Health Dashboard

* personal view of healh of AWS services used by you 

---