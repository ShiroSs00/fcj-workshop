---
title: "Week 2 Worklog"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives:

- Learn about IAM (Identity and Access Management) for secure access control.
- Understand VPC (Virtual Private Cloud) and network architecture.
- Practice hands-on IAM and VPC configuration.

### Tasks to be carried out this week:

| Day | Task                                                                                                                                                                                                           | Start Date | Completion Date | Reference Material               |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------- | --------------- | -------------------------------- |
| 1   | - Learn about IAM fundamentals <br>&emsp; + Users <br>&emsp; + Groups <br>&emsp; + Roles <br>&emsp; + Policies <br>&emsp; + Permissions                                                                        | 09/15/2025 | 09/15/2025      | https://docs.aws.amazon.com/iam/ |
| 2   | - Practice IAM: <br>&emsp; + Create IAM users <br>&emsp; + Create IAM groups <br>&emsp; + Attach policies to users and groups <br>&emsp; + Test user permissions                                               | 09/16/2025 | 09/16/2025      | AWS IAM Tutorial                 |
| 3   | - Learn about VPC fundamentals <br>&emsp; + VPC concept and structure <br>&emsp; + CIDR blocks and IP allocation <br>&emsp; + Subnets and availability zones <br>&emsp; + Public and private subnets           | 09/17/2025 | 09/17/2025      | https://docs.aws.amazon.com/vpc/ |
| 4   | - Learn about Security Groups and Network ACLs <br>&emsp; + Security Groups: inbound and outbound rules <br>&emsp; + Network ACLs for additional network security <br>&emsp; + Stateful vs stateless filtering | 09/18/2025 | 09/18/2025      | AWS VPC Security Guide           |
| 5   | - Practice VPC: <br>&emsp; + Create custom VPC with CIDR block <br>&emsp; + Create public and private subnets <br>&emsp; + Configure Security Groups <br>&emsp; + Create Internet Gateway                      | 09/19/2025 | 09/19/2025      | AWS VPC Tutorial                 |
| 6   | - Practice VPC (continued): <br>&emsp; + Set up routing tables and routes <br>&emsp; + Test connectivity between resources <br>&emsp; + Verify security group rules and network configuration                  | 09/20/2025 | 09/20/2025      | AWS VPC Tutorial                 |

### Week 2 Achievements:

- Understood IAM (Identity and Access Management) fundamentals:

  - IAM users for individual user access
  - IAM groups for managing multiple users together
  - IAM roles for service-to-service communication
  - IAM policies and permissions structure
  - Principle of least privilege for security best practices

- Successfully completed IAM hands-on practice:

  - Created IAM users with different access levels
  - Organized users into logical groups
  - Attached AWS managed and inline policies to users and groups
  - Generated and managed access keys for programmatic access
  - Tested IAM policies by logging in as different users
  - Understood policy conditions and resource restrictions
  - Configured password policies and MFA requirements

- Understood VPC (Virtual Private Cloud) fundamentals:

  - VPC concept: isolated network environment within AWS
  - CIDR blocks for IP address space allocation
  - Subnets: dividing VPC into smaller networks
  - Availability zones for high availability and fault tolerance
  - Public and private subnets for different resource types
  - Route tables for directing network traffic

- Understood network security concepts:
  - Security Groups: virtual firewalls for EC2 instances
  - Inbound and outbound rules for traffic control
  - Network ACLs (NACLs) for subnet-level security
  - Stateful vs stateless firewall filtering
  - Default security group behavior
