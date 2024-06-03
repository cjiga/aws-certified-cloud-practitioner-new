# aws-certified-cloud-practitioner-new

## AWS Glossary: Acronym & Terminology
**IAM**: Identity and Access Managment <br />
**EC2**: Elastic Compute Cloud <br />
**EBS**: Elastic Block Store <br />
**AMI**: Amazon Machine Image <br />
**EFS**: Elastic File System <br />
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
- Instance types: Various configurations of CPU, memory, storage, networking capacity, and graphics hardware for your instances.
- Key pairs: Secure login information for your instances. AWS stores the public key and you store the private key in a secure place.
- Security groups: A virtual firewall that allows you to specify the protocols, ports, and source IP ranges that can reach your instances, and the destination IP ranges to which your instances can connect.
- Tags: Metadata that you can create and assign to your Amazon EC2 resources.

## EC2 - User Data
- It is possible to bootstrap our instace using an EC2 User data script.
- Boostrapping means launching commands when a machine starts.
- That script is only run once at the instance first start.
- The EC2 User Data Script runs with the root user

## EC2 - Instance Type
- **General purpose**: Great for diversity of workloads such as web servers or code repositories
- **Compute optimized**: Great for compute-intesive task that require high performance processors
- **Memory optimized**: Fast performance for workloads that process large data sets in memory
- **Accelerate computing**:
- **Storage optimized**: Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage
- **HPC optimized**:

## EC2 - Instance Type naming convention
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/118dc449-3d8c-4480-a7e9-39cdd72a6e7e)


## EC2 - Security Groups
- Security groups are acting as a “firewall” on EC2 instances
- If you don't specify a security group, Amazon EC2 uses the default security group for the VPC.
- They regulate:
  - Access to Ports
  - Authorised IP ranges
  - IPv4 and IPv6
  - Control of inbound network (from other to the instance)
  - Control of outbound network (from the instance to other)
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/cad78c8f-ea1f-42f4-a0eb-193e45a66249)

## Classic Ports to know
- 22 = SSH (Secure Shell) - log into a Linux instance
- 21 = FTP (File Transfer Protocol) – upload files into a file share
- 22 = SFTP (Secure File Transfer Protocol) – upload files using SSH
- 80 = HTTP – access unsecured websites
- 443 = HTTPS – access secured websites
- 3389 = RDP (Remote Desktop Protocol) – log into a Windows instance

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

## Which purchasing option is right for me?
- On demand: coming and staying in resort whenever we like, we pay the full price
- Reserved: like planning ahead and if we plan to stay for a long time, we may get a good discount.
- Savings Plans: pay a certain amount per hour for certain period and stay in any room type (e.g.,King, Suite, Sea View, …)
- Spot instances: the hotel allows people to bid for the empty rooms and the highest bidder keeps therooms. You can get kicked out at any time
- Dedicated Hosts: We book an entire building of the resort
- Capacity Reservations: you book a room for a period with full price even you don’t stay in it

## Metadata
- Instance metadata is data about your instance that you can use to configure or manage the running instance. 
- Metadata is divided into categories, for example, host name, events, and security groups.

# EC2 - Instance Storage Section
- Amazon EBS volumes: Persistent storage volumes for your data using Amazon Elastic Block Store (Amazon EBS).
- Amazon Machine Images: Preconfigured templates for your instances that package the components you need for your server.
- Instance store volumes: Storage volumes for temporary data that is deleted when you stop, hibernate, or terminate your instance.

## EBS Volume
- It’s a network drive (i.e. not a physical drive)
  - It uses the network to communicate the instance, which means there might be a bit of latency
  - It can be detached from an EC2 instance and attached to another one quickly
- It’s locked to an Availability Zone (AZ)
  - An EBS Volume in us-east-1a cannot be attached to us-east-1b
  - To move a volume across, you first need to snapshot it
- Have a provisioned capacity (size in GBs, and IOPS)
  - You get billed for all the provisioned capacity
  - You can increase the capacity of the drive over time
 
## EBS Snapshots
- Make a backup (snapshot) of your EBS volume at a point in time
- Not necessary to detach volume to do snapshot, but recommended
- Can copy snapshots across AZ or Region

## AMI Overview
- AMI are a customization of an EC2 instance
  - You add your own software, configuration, operating system, monitoring…
  - Faster boot / configuration time because all your software is pre-packaged
- AMI are built for a specific region (and can be copied across regions)
- You can launch EC2 instances from:
  - A Public AMI: AWS provided
  - Your own AMI: you make and maintain them yourself
  - An AWS Marketplace AMI: an AMI someone else made (and potentially sells)
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/9c324ddb-3cbf-41d4-8e31-fb707a5f9bf5)

## EC2 Image Builder
- Used to automate the creation of Virtual Machines or container images
- => Automate the creation, maintain, validate and test EC2 AMIs
- Can be run on a schedule (weekly, whenever packages are updated, etc…)
- Free service (only pay for the underlying resources)
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/b36c14de-0b30-4d21-b8b3-993d0c443648)

## EC2 Instance Store
- EBS volumes are network drives with good but “limited” performance
- If you need a high-performance hardware disk, use EC2 Instance Store
- Better I/O performance
- EC2 Instance Store lose their storage if they’re stopped (ephemeral)
- Good for buffer / cache / scratch data / temporary content
- Risk of data loss if hardware fails
- Backups and Replication are your responsibility

## EFS – Elastic File System
- Manage NFS (Netword File System) that can be mounted on 100s of EC2
- EFS works with Linux EC2 instances in multi-AZ
- Highly available, scalable, expensive (3x gp2), pay per use, no capacity planning
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/eb00c5a2-ea22-4d33-9075-3f0d0c632718)

## EBS vs EFS
![image](https://github.com/cjiga/aws-certified-cloud-practitioner-new/assets/904293/56f2acb3-0957-4d74-a2c9-3e8648fb5a09)


