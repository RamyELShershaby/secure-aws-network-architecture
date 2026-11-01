# Disaster Recovery Plan

## Strategy

The report documents a pilot-light disaster-recovery network skeleton in a second AWS Region. The design keeps network foundations prepared while avoiding continuously running compute during the lab's idle state.

## Documented elements

- A separate DR VPC in `us-west-2`.
- Matching subnet and route-table structure for a future recovery workload.
- Cross-Region recovery planning and Route 53 failover concepts.
- A recovery plan and operational notes authored in the monitoring/incident-response workstream.

## Scope boundary

This was a lab design and pilot-light skeleton. Do not describe it as a fully exercised, automatic cross-Region production failover unless additional evidence supports that claim.

## Recommended runbook sections

1. Declare the incident and assign an incident lead.
2. Confirm the primary Region is unavailable or unsuitable.
3. Validate recovery dependencies, permissions, network routes, and required data.
4. Provision or activate recovery compute and application dependencies.
5. Validate health endpoints and security controls.
6. Shift traffic only after approval and successful validation.
7. Monitor the recovery environment and communicate status.
8. Document failback criteria and the post-incident review.

