# aws-certified-cloud-practitioner-new

## AWS Glossary: Acronym & Terminology
**IAM**: Identity and Access Managment <br />
**EC2**: Elastic Compute Cloud <br />
**EBS**: Elastic Block Store <br />
**AMI**: Amazon Machine Image <br />
**ELB**: Elastic Compute Cloud <br />
**ASG**: Elastic Compute Cloud <br />


## The five characteristics of Cloud Computing
- **On-demand selft service:**
  - User can provision resources and use them without human interaction from the service provider
- **Broad network access:**
  - Resources available over the network, and can be accessed by diverse client platforms
- **Multi-tenancy and resource pooling**
  - Multiple customers can share the same infrastructure and applications with security and privacy
  - Multiple customers are serviced from the same physical resources
- **Rapid elasticity and scalability**
  - Automatically and quickly acquire and dispose resources when needed
  - Quickly and easily scale based on demand
- **Measure service:**
  - Usage is measured, users pay correctly for what they have used
 
## Six Advantage of Cloud Computing
- **Trade capital expense(CAPEX) for operational expense(OPEX)**
  - Pay On-Demand: don't own hardware
  - Reduced Total Cost of Ownership(TCO) & Operational Expense(OPEX)
- **Benefit from massive economies of scale**
  - Prices are reduced as AWS is more efficient due to large scale
- **Stop guessing capacity**
  - Scale base on actual measured usage
- **Increase speed and agility**
- **Stop spending money running and maintaining data centers**
- **Go global in minutes: leverage the AWS global infrastructure**

## Problems solved by the cloud
- **Flexibility:** change resource types when needed
- **Cost-Effectiveness:** pay as you go, for what you use
- **Scalability:** accomodate larger loads by making hardware stronger or adding additional nodes
- **Elasticity:** ability to scale out and scale-in when needed
- **High-availability and fault-tolerance:** build across data centers
- **Agilibility:** rapidly develop, test and launch software applications

## The five characteristics of Cloud Computing
- **Infrastructure as a Services (IaaS)** - Amazon EC2 (Applications, Data, Runtime, Middleware, O/S)
  - Provide building blocks for cloud IT
  - Provides networking, computers, data storage space
  - Highest level of flexibility
  - Easy parallel with traditional on-premises IT
- **Platform as a Services (PaaS)** - Elastic Beanstalk (Applications)
  - Removes the need for your organization to manage the underlying infrastructure
  - Focus on the deployment and management of your applications
- **Software as a Service (SaaS)** - Many AWS Services (ex: Rekognition for Machine Lerning)
  - Completed product that is run and managed by the service provider
 
## Pricing of the Cloud 
AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model, which solves the expensives issue of traditional IT.
- **Compute**: Pay for compute time
- **Storage**: Pay for data stored in the Cloud.
- **Data transfer OUT of the cloud:** Data transfer IN is free

## AWS Cloud History 
2002: Internally launched<br />
2003: Amazon infrastructure is one of their core strength. Idea to market<br />
2004: Launched publicly with SQS<br />
2006: Re-laucnhed publicly with SQS, S3 & EC2<br />
2007: Launched in Europe<br />

## AWS Global Infrastructure
###AWS Regions
  **Compliance** With data governance and legal requirements: data never leaves a region without your explicit permission.<br />
  **Proximity** to customers: Reduced latency.<br />
  **Available** services within a Region: new services and new features aren't available in every Region.<br />
  **Pricing**: pricing varis region to region and is transparent in the service pricing page
  
###AWS Availability Zones
- Each region has many availability zones (usually 3, min is 3, max is 6).
- Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity.
- They're separate from each other, so that thery're isolated from disasters
- They're connected with high bandwidth, ultra-low latency networking
###AWS Data Centers
###AWS Edge Locations/Points of Presence

## AWS Global Services
- Identity and Access Management (IAM)
- Route 53 (DNS service)
- CloudFront (Content Delivery Network)
- WAF (Web Application Firewall)

## Shared Responsibility Model diagram
- CUSTOMER = Resonsibility for the security **IN** the cloud
- AWS - Resonsibility for the security **OF** the cloud

## AWS Acceptable Use Policy
- No Illegal, Harmful, or Offensive Use or Content
- No Security Violations
- No Network Abuse
- No E-Mail or Other Message Abuse

# IAM Section
## IAM: Users & Groups
- Users are people within your organization, and can be grouped
- Groups only contain users, not other groups
- Users don’t have to belong to a group, and user can belong to multiple groups

## IAM: Permissions
- Users or Groups can be assigned JSON documents called policies
- These policies define the permissions of the users
- In AWS you apply the least privilege principle: don’t give more permissions than a user needs 

## IAM Policies Structure
JSON document that outlines permissions for users or groups

- Consists of
  - Version: policy language version, always include “2012-10-17”
  - Id: an identifier for the policy (optional) • Statement: one or more individual statements (required)
- Statements consists of
  - Sid: an identifier for the statement (optional)
  - Effect: whether the statement allows or denies access(Allow, Deny)
  - Principal: account/user/role to which this policy applied to
  - Action: list of actions this policy allows or denies
  - Resource: list of resources to which the actions applied to
  - Condition: conditions for when this policy is in effect(optional)
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/0df9d0a7-3839-445a-8886-cc34c07b5aae)

## MFA deveces options in AWS
- Virtual MFA device
- Universal 2nd Factor (U2F) Security Key
- Hardware Key Fob MFA Device

## How can users access AWS ?
- To access AWS, you have three options:
  - AWS Management Console (protected by password + MFA)
  - AWS Command Line Interface (CLI): protected by access keys
  - AWS Software Developer Kit (SDK) - for code: protected by access keys
- Access Keys are generated through the AWS Console
- Users manage their own access keys
- Access Keys are secret, just like a password. Don’t share them
- Access Key ID ~= username
- Secret Access Key ~= password

## IAM Rols for Services
- Some AWS services will need to perform  action on your behalf
- To do so, we will assign permission to AWS services with IAM roles
- When you assume a role, it provides you with temporary security credentials for your role session.
- You can use roles to delete access to users, applications or services that don't normally have access to your AWS resources

## IAM Security Tools
- IAM Credentials Report (account-level)
- IAM Access Advisor (user-level)

# EC2 - Elastic Compute Cloud
- Instances: Virtual Servers
- Amazon Machine Images: Preconfigured templates for your instances that package the components you need for your server.
- Instance types: Various configurations of CPU, memory, storage, networking capacity, and graphics hardware for your instances.
- Key pairs: Secure login information for your instances. AWS stores the public key and you store the private key in a secure place.
- Instance store volumes: Storage volumes for temporary data that is deleted when you stop, hibernate, or terminate your instance.
- Amazon EBS volumes: Persistent storage volumes for your data using Amazon Elastic Block Store (Amazon EBS).
- Security groups: A virtual firewall that allows you to specify the protocols, ports, and source IP ranges that can reach your instances, and the destination IP ranges to which your instances can connect.
- Tags: Metadata that you can create and assign to your Amazon EC2 resources.

## EC2 Instances Purchasing Options
- On-Demand Instances – short workload, predictable pricing, pay by second
  - Reserved (1 & 3 years)
  - Reserved Instances – long workloads
- Convertible Reserved Instances – long workloads with flexible instances
- Savings Plans (1 & 3 years) –commitment to an amount of usage, long workload
- Spot Instances – short workloads, cheap, can lose instances (less reliable)
- Dedicated Hosts – book an entire physical server, control instance placement
- Dedicated Instances – no other customers will share your hardware
- Capacity Reservations – reserve capacity in a specific AZ for any duration
