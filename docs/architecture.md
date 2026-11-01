# Architecture Overview

## Design goals

The architecture follows the project principle:

**Secure → Segment → Connect → Monitor → Detect → Remediate → Recover**

The lab combines a production-style multi-tier network with shared services, private connectivity, edge delivery, monitoring, and a pilot-light DR design.

## Network layout

| Environment | Region | Documented CIDR | Purpose |
|---|---|---:|---|
| Production VPC | `us-east-1` | `10.0.0.0/16` | Web application and database tiers |
| Shared Services VPC | `us-east-1` | `10.1.0.0/16` | Shared access and connectivity testing |
| Pilot-light DR VPC | `us-west-2` | `10.2.0.0/16` | Disaster-recovery network skeleton |
| Simulated on-premises | Lab simulation | `192.168.0.0/16` | Hybrid connectivity exercises |

These are private network ranges, but the original report contains additional identifying AWS values. Public copies should omit unnecessary account IDs, resource IDs, ARNs, endpoints, and public IPs.

## Production tiers

- **Public subnets:** host the internet-facing ALB and NAT Gateway placement.
- **Private application subnets:** host EC2 application instances without public IP addresses.
- **Isolated database subnets:** host the RDS database; the database route table was documented with only the local route.
- **Shared private subnets:** host shared access components and private endpoint connectivity.

The production subnets span two Availability Zones. The lab used an ALB target group forwarding HTTP traffic to the application instances on port 8080.

## Request path

1. Users resolve the application name through Route 53.
2. CloudFront serves static website content from a private S3 origin using OAC.
3. Requests matching `/api/*` and `/health/*` are routed to the ALB origin.
4. The ALB distributes application requests to private EC2 targets.
5. Application-to-database access is constrained by security rules and network placement.

The final report records successful HTTP 200 verification for the API and health paths during testing.

## VPC connectivity

- **VPC Peering:** provides direct routed connectivity between production and shared-services VPCs for approved CIDRs.
- **VPC Endpoints:** provide private access to supported AWS services; the S3 Gateway Endpoint avoids routing S3 traffic through NAT.
- **AWS PrivateLink:** exposes the application privately to the shared-services VPC through an internal Network Load Balancer and endpoint service.
- **Transit Gateway:** demonstrates a hub-based connectivity pattern for multiple VPC and hybrid attachments.
- **Site-to-Site VPN and Client VPN:** demonstrate hybrid and remote-client access patterns.
- **Direct Connect:** documented as a design concept only, not physically provisioned.

## Monitoring and response

VPC Flow Logs feed analysis through Athena. CloudWatch dashboards and alarms support visibility; GuardDuty and Security Hub add security findings and posture checks. The documented EventBridge-to-Lambda workflow can quarantine a suspected instance by applying a deny rule in the relevant network ACL, subject to the response logic and safeguards described in the report.

## Disaster recovery

The DR environment is documented as a pilot-light network skeleton in a second Region with zero running compute in the lab's idle state. This is a design and lab exercise, not evidence of a fully active production failover deployment.

## Diagram

Add a sanitized, readable diagram as `diagrams/architecture.png`. Do not use a screenshot that exposes AWS account IDs, public IPs, ARNs, private keys, or console account details.
