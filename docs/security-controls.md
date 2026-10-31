# Security Controls

## Network segmentation

The lab uses separate Security Groups for the load balancer, application tier, database tier, bastion/access components, and interface endpoints. The intended model is least privilege: allow only required protocols and sources between tiers.

Network ACLs provide an additional subnet-level control. Because NACLs are stateless, return traffic requires explicit rules. The report reserves a low rule number for the incident-response quarantine deny rule.

## Administrative access

Application instances were documented without public IP addresses and without SSH key pairs. AWS Systems Manager Session Manager was used for administrative access, supported by an EC2 IAM role and required service endpoints.

## Database isolation

The RDS database was placed in isolated database subnets. The report documents application-tier access to MySQL on port 3306 and no internet route from the database subnet route table.

## Edge controls

- CloudFront Origin Access Control (OAC) restricts direct access to the private S3 origin.
- AWS WAF provides web-request filtering and rate-based protection according to the plan available during the lab.
- AWS Shield Standard is included as an edge DDoS protection layer.
- Route 53 health checks and failover were configured/documented for a maintenance destination.

## Detection and governance

- CloudTrail records account activity.
- GuardDuty generates security findings; sample findings in the report are explicitly test data, not proof of real attacks.
- Security Hub was enabled with security standards; the report notes that the compliance score was still generating in the captured evidence.
- VPC Flow Logs and Athena support network activity analysis.
- CloudWatch dashboards and alarms support monitoring.
- EventBridge and Lambda implement an automated quarantine path.

## Security caveats to disclose

The final public documentation should distinguish implemented controls from conceptual notes and deferred tasks. Firewall Manager was deferred by design. Direct Connect was documented conceptually but not deployed. The report also contains detailed lab identifiers and VPN private-key material, so the original PDF must not be published without thorough sanitization.
