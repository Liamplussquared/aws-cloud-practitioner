# Cloud Concepts

1. [Define the AWS Cloud and its value proposition](#1.1-Define-the-AWS-Cloud-and-its-value-proposition)
2. [Identify aspects of AWS Cloud economics](#1.2-Identify-aspects-of-AWS-Cloud-economics)
3. [List the different cloud architecture design principles](#1.3-List-the-different-cloud-architecture-design-principles)

---

## 1.1 Define the AWS Cloud and its value proposition

### AWS Cloud 

* **Cloud computing** is the on-demand delivery of IT resources over the internet with a pay-as-you-go pricing.

* Instead of maintaining physical data centres and servers, one can access computing power, storage, content delivery, and databases on an as-needed basis from a cloud provider. 

* 25 launched regions with over 80 availability zones. 


### AWS Value Proposition 

* **Agility**:
	* broad range of technologies allow faster innovation and building
	* can deploy solutions in matter of minutes -> experimentation 

* **Elasticity**:
	* easily scale resources up or down to fit demand 
	* wasted capacity eliminated

* **Flexiblity**:
	* can select exact services needed (OS, programming language, database, etc)
	* low cost of entry, broad set of products

* **Security**:
	* AWS uses end-to-end approach to secure and harden infrastructure
	* acquired many certifications 
	* **shared responsibility model**

### Advantages of Cloud Computing

1. Variable expense rather than capital expense
2. Economies of scale
3. Stop guessing capacity 
4. Increase speed and agility
5. Save costs on running & maintaining data centres
6. Go global in minutes

---

## 1.2 Identify aspects of AWS Cloud economics

### Pay-As-You-Go Pricing

* low variable expenses rather than large capital expenses 

### Tiered Pricing (Use more, pay less)

* the more sotrage and data transfer used, the less paid per gigabyte 
* volume discounts and custom pricing available for high volume projects w/ unique requirements

### Cost Optimization 

* **AWS Cost Explorer** allows AWS costs and usage to be visualised and managed 
* default reports used as starting place for analysis, filtering and grouping capabilities allow you to dive deeper into cost and usage data

### AWS Trusted Advisor

* fully managed service that provides guidance to follow AWS best practices 
* optimise AWS infrastructure, improve security/performance, reduce overall costs, monitor service limits
* scans AWS insfrastructure and compares to AWS best practices in five categories (Cost Optimisation, Performance, Security, Fault tolerance, Service limits)

---

## 1.3 List the different cloud architecture design principles

### Well-Architected Framework

* build secure, high performing, resilient & efficient infrastructure 

* **Five Pillars**
	1. operational excellence
		* deliver business value, continually improve processes and procedures
	2. security
		* protecting information and systems
	3. reliability
		* prevent & quickly recover from failures
	4. performance efficiency 
		* using IT & computing resources efficiently
	5. cost optimisation
		* avoid unneeded costs

### Core Principles

* Elasticity
* Scalability

### Remove SPOF 

* single point of failure
* introduce redundancy, i.e multiple resources for same task
* automate detection/reaction to failure

--- 




