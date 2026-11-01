# Cost Management and Final Cleanup

## Cost-aware design choices

The report describes several measures used to keep the lab within its budget:
- A single zonal NAT Gateway rather than a more expensive multi-AZ NAT design.
- An S3 Gateway Endpoint to keep S3 access off the NAT path.
- A pilot-light DR VPC with no running compute while idle.
- Same-session deployment, testing, and teardown for hourly-billed hybrid resources such as Transit Gateway and VPN components.
- Billing alarms and a dependency-ordered final teardown.

The report gives a target budget of approximately $55–$75 from a $200 allocation. These are historical project figures, not current AWS price guidance.

## Final teardown

The final report states that the team executed a dependency-ordered teardown across both Regions after evidence capture and verification, with a reported final active billing state of $0.00 for the lab resources.

The teardown included hybrid VPN and Transit Gateway components, PrivateLink resources and endpoints, traffic-mirroring resources, EC2 instances and associated artifacts, load balancing, RDS, edge services, monitoring resources, and supporting IAM/network resources.

## Before reproducing the project

AWS pricing and service behavior can change. Review current pricing and account-specific free-tier/credit conditions before recreating the lab. Do not deploy all components from this report without a cost estimate and teardown checklist.
