# Secure AWS Network Architecture

> A secure and scalable AWS network architecture project focused on network segmentation, controlled connectivity, VPC Peering, application delivery, monitoring, detection, and incident response.

## 📌 Project Status

**Status:** 🚧 In Progress — Project Initialization

This repository is the central workspace for the **Secure AWS Network Architecture** project.

The implementation will be developed progressively according to the project plan, with each team member responsible for a defined technical workstream.

---

## 🎯 Project Overview

The project demonstrates how a secure AWS cloud environment can be designed with clear network segmentation, controlled connectivity, application delivery, monitoring, and security validation.

The proposed architecture consists of **two AWS VPCs** connected through **VPC Peering**:

* **VPC A:** Main Application Environment
* **VPC B:** Separate Services Environment

The infrastructure and VPC foundation are centrally managed to ensure that dependent workstreams can be implemented and tested on a consistent environment.

---

## 🏗️ Proposed Architecture

### VPC A — Main Application Environment

**CIDR:** `10.0.0.0/16`

Planned subnets:

* Public Subnet — `10.0.1.0/24`
* Private App Subnet — `10.0.2.0/24`
* Private Data Subnet — `10.0.3.0/24`

### VPC B — Services Environment

**CIDR:** `10.1.0.0/16`

Planned subnets:

* Private Subnet 1 — `10.1.1.0/24`
* Private Subnet 2 — `10.1.2.0/24`

### VPC Connectivity

The two VPCs will be connected using **VPC Peering** to provide private communication between the environments.

> CIDR ranges and resource configurations are proposed values and may be adjusted during implementation according to AWS Academy Sandbox limitations.

---

## ☁️ Planned AWS Services & Components

The project may include the following AWS components:

* Amazon VPC
* Public & Private Subnets
* Route Tables
* Internet Gateway
* NAT Gateway
* Amazon EC2
* Application Load Balancer (ALB)
* Target Groups
* Security Groups
* Network ACLs
* VPC Peering
* VPC Flow Logs
* Amazon CloudWatch
* Amazon Athena
* AWS WAF
* Amazon S3
* Amazon CloudFront
* Amazon RDS

Some services may remain design-only if they are unavailable or restricted within the AWS Academy Sandbox.

---

## 🔐 Security Focus

The project focuses on:

* Network segmentation
* Controlled routing
* Security Groups
* Network ACLs
* VPC Peering security
* WAF controls where supported
* VPC Flow Logs
* Network monitoring
* Detection use cases
* Incident response
* Security validation and testing

---

## 👥 Team

| Member         | Role                                              |
| -------------- | ------------------------------------------------- |
| **Ramy Ahmed** | Infrastructure & Network Architecture             |
| **Roa**        | Network Security & Segmentation                   |
| **Mariam**     | Application Delivery & Edge Security              |
| **Shrouk**     | VPC Peering & Hybrid Connectivity                 |
| **Yehia**      | Network Monitoring, Detection & Incident Response |

---

## 🔄 Project Phases

### Phase 1 — Planning & Design

* Define network architecture
* Finalize CIDR and subnet structure
* Define security requirements
* Define connectivity requirements
* Define monitoring and incident-response requirements

### Phase 2 — Infrastructure Foundation

* Create VPCs
* Create public and private subnets
* Configure route tables
* Configure Internet/NAT connectivity
* Deploy required EC2 resources
* Apply baseline security controls

### Phase 3 — VPC Peering & Connectivity

* Configure VPC Peering
* Configure routing between VPCs
* Validate private connectivity
* Document hybrid connectivity alternatives

### Phase 4 — Application Delivery & Security

* Configure ALB and Target Groups
* Integrate the application environment
* Validate application traffic
* Configure additional services where supported

### Phase 5 — Monitoring, Detection & Incident Response

* Enable VPC Flow Logs
* Analyze network traffic
* Develop detection use cases
* Perform a controlled incident-response exercise
* Document the Incident Response Runbook

### Phase 6 — Final Validation & Presentation

* Validate all workstreams
* Capture implementation evidence
* Finalize documentation
* Prepare the final architecture
* Prepare the project presentation and demonstration

---

## 📦 Expected Deliverables

The project is expected to produce:

* Final AWS architecture diagram
* CIDR and subnet addressing plan
* VPC and routing documentation
* VPC Peering configuration and connectivity test results
* Security Group and NACL rule matrix
* Application / ALB / Target Group validation evidence
* Monitoring and VPC Flow Logs evidence
* Detection use cases and log analysis
* Incident Response Runbook
* Hybrid connectivity design comparison
* Project documentation
* Final presentation and demonstration

---

## ⚠️ AWS Academy Sandbox Considerations

AWS service availability and permissions will be verified during implementation.

Some services may be restricted by the AWS Academy Sandbox. If a service cannot be deployed, the project will document the intended architecture and the corresponding limitation rather than claiming successful implementation.

Cost-sensitive resources will be monitored and removed when no longer required.

**No AWS credentials, passwords, access keys, or other sensitive information should ever be stored in this repository.**

---

## 📈 Project Progress

| Area                   | Status         |
| ---------------------- | -------------- |
| Project Planning       | 🟢 Completed   |
| Repository Setup       | 🟢 Completed   |
| Architecture Design    | 🟡 In Progress |
| VPC Infrastructure     | ⚪ Not Started  |
| Security Configuration | ⚪ Not Started  |
| VPC Peering            | ⚪ Not Started  |
| Application Delivery   | ⚪ Not Started  |
| Monitoring & Detection | ⚪ Not Started  |
| Incident Response      | ⚪ Not Started  |
| Final Documentation    | ⚪ Not Started  |
| Final Presentation     | ⚪ Not Started  |

---

## 👨‍💻 Team Coordination

The project follows a dependency-based implementation approach.

Infrastructure-dependent tasks will be validated after the required AWS resources are available. For example, meaningful network log analysis requires the VPC infrastructure, logging configuration, and generated traffic to be available first.

The Team Leader coordinates the infrastructure foundation and technical handoffs between the different workstreams.

---

**Project:** Secure AWS Network Architecture
**Team Leader:** Ramy Ahmed
**Status:** In Progress
