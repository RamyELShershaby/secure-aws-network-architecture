# Limitations, Exceptions, and Lessons Learned

Professional project documentation should make limitations explicit instead of presenting every planned feature as deployed.

## Documented exceptions

- **Firewall Manager (T25):** deferred by design according to the report.
- **AWS Direct Connect:** concept document only; no physical or partner circuit was provisioned.
- **Site-to-Site VPN:** configured with a simulated customer gateway; tunnels were down by design.
- **Client VPN:** initial reachability failed; a successful test was documented after rebuilding the lab.
- **Security Hub:** enabled with the required standards, but the captured report notes that scores were still generating.
- **GuardDuty:** sample findings were generated for validation; these are not real incidents.
- **WAF plan constraints:** rule availability and operating mode differed between account plans during the lab. The report describes this as a configuration/scope limitation.
- **Evidence gaps:** the security report explicitly notes some evidence gaps. Keep them visible in the final presentation.
- **Lifecycle:** the lab resources were deleted after testing to avoid ongoing charges. The public repository is documentation/evidence, not a live environment.

## Lessons learned to highlight

- Security Groups and stateless NACLs must be designed together, including return traffic.
- Routing, security rules, and endpoint DNS all matter when troubleshooting private connectivity.
- Cross-workstream handoffs are essential: edge routing depends on working backend API and health endpoints.
- PrivateLink and peering solve different connectivity problems and should be documented separately.
- VPN tunnel state depends on the far-end device; a simulated customer gateway cannot substitute for a live site-to-site peer.
- Automated quarantine should have guardrails, audit trails, and a rollback path.
- Evidence should be captured as part of testing, then redacted before publication.
- Cost controls and teardown are part of cloud engineering, not an afterthought.

## Review before publication

Confirm all claims against the final report and evidence. If a feature was planned, documented conceptually, or partially tested, label it that way.
