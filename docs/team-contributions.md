# Team Contributions and Task Ownership

This page summarizes the workstream ownership recorded in the final project report. Task ranges refer to the report's T1–T68 task plan.

## Ramy Ahmed — Team Lead / VPC Foundation

**Assigned scope:** T1–T12 plus backend API and health endpoint fix.

- Configured billing alarms at the documented thresholds.
- Built the production and shared-services VPC foundations.
- Created the production public, private application, and isolated database subnets across two Availability Zones, plus shared-services private subnets.
- Configured the Internet Gateway, cost-optimized NAT Gateway, and custom route tables.
- Deployed the application EC2 instances and shared bastion, managed through AWS Systems Manager rather than public SSH.
- Deployed the Application Load Balancer and target group.
- Configured a Multi-AZ Amazon RDS lab database in isolated database subnets.
- Created the pilot-light DR VPC skeleton in the second Region with no running compute.
- Fixed `/api/` and `/health/` paths on the application instances and verified HTTP 200 responses through the ALB.

## Roa — Security and Segmentation

**Assigned scope:** T13–T26.

- Created and attached the EC2 Systems Manager IAM role.
- Designed tier-specific Security Groups and applied resource assignments.
- Configured stateless Network ACLs and return-traffic rules.
- Documented and ran network segmentation checks.
- Enabled CloudTrail, GuardDuty, and Security Hub for the lab.
- Supported interface endpoint and peering security rules.
- Prepared AWS Direct Connect concepts and an architecture diagram; Direct Connect itself was **not deployed** in the lab because it requires a physical/partner connection.
- **Scope exception:** T25 (Firewall Manager) was deferred by design according to the report. Endpoint cleanup and final teardown were documented in the cleanup workstream.

## Shrouk — Connectivity and Hybrid Networking (with Yehia support)

**Assigned scope:** T27–T41.

- Created and verified VPC Peering between production and shared-services VPCs.
- Added route-table entries for the required peering paths while keeping the database route table isolated.
- Configured an S3 Gateway Endpoint and interface endpoints for private AWS service access.
- Built and tested a Transit Gateway hub and its attachments.
- Configured a Site-to-Site VPN using a simulated customer gateway; the report records the tunnels as down by design in this lab.
- Verified Client VPN access, including a successful connectivity run after rebuilding the lab environment.
- Performed connectivity troubleshooting and cost cleanup for the workstream.

## Mariam — Edge Security and Delivery

**Assigned scope:** T42–T54.

- Stored the static website in a private S3 bucket.
- Configured CloudFront Origin Access Control (OAC) for private S3 origin access.
- Set up CloudFront routing for static content and `/api/*` / `/health/*` paths to the application origin.
- Configured AWS WAF protections and documented XSS testing.
- Configured/documented Route 53 health-check failover to a maintenance experience.
- Documented AWS Shield Standard, CloudFront versus Global Accelerator, and DDoS considerations.
- Coordinated with Ramy to resolve backend route responses during end-to-end testing.
- Recorded plan and pricing limitations that affected which WAF rules were available in the final lab configuration.

## Yehia — Monitoring, Incident Response, and DR

**Assigned scope:** T55–T67, with support on connectivity tasks and shared final cleanup.

- Configured SNS notifications, VPC Flow Logs, and Athena-based analysis.
- Built a partitioned Athena table and four documented threat-hunting queries.
- Configured a CloudWatch dashboard and alarms.
- Built an EventBridge-to-Lambda auto-quarantine workflow.
- Configured traffic mirroring and ran a live incident-response simulation.
- Prepared the incident-response runbook and disaster-recovery plan.
- Documented the final report and supported cost-aware resource teardown.

## Shared responsibility — T68 final teardown

All five members participated in the dependency-ordered cleanup documented in the report. The report states that lab resources across both Regions were removed after verification to avoid ongoing charges.
