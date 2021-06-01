# Security

1. [Shared Responsibility Model](#2.1-Shared-Responsibility-Model)
2. [AWS Cloud Security and Compliance Concepts](#2.2-Security-and-Compliance)
3. [AWS Access Management Capabilities](#2.3-AWS-Access-Management-Capabilities)
4. [Resources for Security Support](#2.4-Resources-for-Security-Support)

---

## 2.1 Shared Responsibility Model

* AWS responsible for physical security of facilities & infrastructure including: database, storage, networking resources
* Customer responsible for software, data and access on top of infrastructure layer
* AWS responsbile for security **of** the cloud, customer responsible for security **in** the cloud 

![Shared Responsbility Model](https://d2908q01vomqb2.cloudfront.net/c5b76da3e608d34edb07244cd9b875ee86906328/2020/12/28/Shared-Responsibility-by-Service-Type.png)

---

## 2.2 Security and Compliance

* Customers only pay for services they use. This means customers can have security they need without upfront costs, and at a lower cost than on-premises.

### Infrastructure Security

* Network firewalls built into Amazon VPC

* In transit encryption using Transport Layer Security (TLS) across *all* services
* Can have private or dedicated connections into data centre 

### Infrastructure Resilience

* Services are built from ground up to be resilient against DDoS attacks
* Services can be scaled automatically for traffic load
* Autoscaling, CloudFront, Route 53 used to prevent DDoS 

### Data Encryption

* At rest encrpytion for EBS, S3, Glacier, RDS (Oracle & SQL), Redshift
* AWS KMS can be used to manage keys (by customers or by AWS)
* Server side encryption of messages queues in SQS
* AWS CloudHSM (hardware security module) used to generate and use encryption keys on AWS cloud. Dedicated hardware based crytographic key storage
* Use APIs to integrate AWS security into any applications

### Standards & Best Practices

* Amazon Inspector automatically assesses applictions for vulnerabilities or deviations form best practices -> impacted networks, OS, attached storage
* Use Deployment tools to manage creation & decommissioning of AWS resources according to organisational standards
* AWS Config enables users to assess, audit and evaluate configuration of AWS resources. It identifies, tracks and manages changes to resources over time
* AWS CloudFormation can be used to create standard, preconfigured environments 

### Monitoring & Logging

* AWS CloudTrail offers deep visibility into API calls -> who, what, when and from where calls were made
* Log aggregation options allow the streamlining of investigations and compliance reporting
* Amazon CloudWatch can alert when specific events occur or thresholds are exceeded

### Identity and Access Control

* AWS Identity and Access Management (IAM) allows individual user accounts with permissions across AWS resources to be created
* AWS MFA (multi-factor authentication) available for privileged accounts, options for hardware-based authenticators 
* AWS Directory Serices allows users to integrate and federate with corporate directories in order to reduce administrative overhead and improve end-user experience  

### Security Support

* AWS Trusted Advisor helps optimise AWS infrastructure, improve security/performance, reduce overall costs & monitor service limits. Offers real time insight
* Technical Account Manager (TAM) offers proactive support and advocacy. 

### Compliance Assurance Programs

* AWS covers many certifications & regulations to frameworks
* UK -> Cyber Essentials Plus, G-Cloud, UK Cloud Security Principles
* US -> DoD, SRG, FIPS
* ISO 9001, CISPE, GLBA, EU Data Protection Directive, FFIEC, NIST

---

## 2.3 AWS Access Management Capabilities

* AWS IAM enables you to securely control access to AWS services and resources for users
* Users and groups can be created with permissions allowing or denying their access to AWS resources/services
* AWS IAM comes at no additional charge

### AWS Identity and Access Management (IAM)

Allows you to:

* manage IAM users and their access. Users can be created, individual security credentials such as access keys, passwords, MFA devices can be assigned to them or temporary security credentials can be provided. 
* manage IAM roles and their permissions. Roles can be created and their permissions for various operations can be controlled. Restrictions can be put in place on which entities are allowed to assume the role. Service-linked roles can be used to delegate permissions to AWS services, which can create and manage AWS resources. 
* manage federated users and their permissions. Identity federation allows existing identities (users, groups, roles in an enterprise) to access AWS Management Console, call AWS APIs, access resources. An IAM user does not need to be created for each identity

### Access & Federation

* Can grant permission to people to administer and use resources in an AWS account without having to share passwords/access keys
* Identity management solutions that support SAML 2.0 can be used to allow access to users who have identities/passwords elsewhere to AWS account

### Granular Permissions

* Different permissions can be granted to different people for different resources 
* IAMa allows specific conditions such as time of day to control *how* a user uses AWS. Other conditions include originating IP address, whether they're using SSL, or if they're authenticated with an MFA authentication device 

### Securing Application Access

* Can use IAM features to securely give applications on EC2 instances the credentials they need in order to access other AWS resources such as S3 buckets, RDS/DynamoDB databases

### Multi Factor Authentication

* Can add two-factor authentication to account and individual users for extra security. A code must be provided from a specially configured device when accessing the account

---

## 2.4 Resources for Security Support

### AWS Support

* Provides tools and resource to help ensure your AWS enviornment is built and operated to be secure, highly available, efficient and cost effective
* Provides real-time insight through AWS Trusted Advisor -> inspects AWS environment and finds ways to save money, improve system performance/reliability or close security gaps
* Provides support and advocacy through Technical Account Manager (TAM). TAM is single point of contact who provides technical expertise across full range of AWS services. TAM works closely with users to deliver proactive guidance and early awareness of new feautures/recommendations
* Full range of AWS Trusted Advisor checks is available to Business and Enterpreise Level Support. Technical Account Managers are included with Enterprise Support

### Professional Services

* AWS Professional Services & AWS Partner Network help users create more comprehensive solutions to security problems, from strategic advice, deployments, & re-engineering.

Support offered include:

* Enterprise Security Architecure. Evaluate the nature of workloads you are deploying in AWS, as well as security needs. Define an architecture and set of security controls that will protect data and workloads according to best practices
* Policies and Controls-Mapping. Provide detailed recommendations on how to satisfy requirements and demonstrate compliance. Based upon own security policy and any third party or regulatory mandates
* Security Operations Playbook. Define correct organisational structures and processes to ensure security controls working correctly. Detect and respond to security issues that arise within AWS environment
* Business Unit Workshops. Work with IT and Business Leaders across organisation to understand their plans and strategies around Cloud adoption, educate them on the best way to satisfy their requirements while minimising risk to organisation, and devise an organisation wide security framework for deploying workloads on AWS.

---
