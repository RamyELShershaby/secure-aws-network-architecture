# Testing and Validation

This page summarizes tests documented in the final report. It should be read as a record of the lab run, not a claim that the resources remain online.

## Security segmentation tests

The security workstream reports eight tests with expected outcomes:

| Test | Expected result | Reported result |
|---|---|---|
| Internet to private EC2 address | Blocked | Not reachable |
| ALB to application target on port 8080 | Allowed | Reachable; target group healthy |
| ALB to application target on port 22 | Blocked | Not reachable |
| Application EC2 to RDS on port 3306 | Allowed | TCP check open |
| Shared bastion to RDS on port 3306 | Blocked | Not reachable |
| Application EC2 to internet via NAT on HTTPS | Allowed | HTTP/2 200 |
| RDS to internet | Blocked | Not reachable |
| Systems Manager Session Manager to EC2 | Allowed | Session opened |

The report notes evidence gaps for some checks; keep those qualifications rather than describing the test set as stronger than the source supports.

## Application path tests

The report documents HTTP 200 responses for `/api/` and `/health/` during end-to-end testing through the ALB. CloudFront routing and edge behavior were also tested after the application paths were fixed.

## PrivateLink test

The report records a successful TCP connection to the private endpoint on port 8080 and an HTTP 200 response from the application through the endpoint DNS name.

## VPN tests

- Site-to-Site VPN: configured against a simulated customer gateway; tunnel state was down by design.
- Client VPN: a successful test was recorded after the lab was rebuilt, including connectivity and browser/HTTP access to the private application.

## WAF testing

The edge workstream documents an XSS test request blocked with HTTP 403 in the tested maintenance-distribution path. WAF managed-rule availability and operating mode varied with the account plan; see the limitations page.

## Evidence publishing rules

For each screenshot, include a concise caption, the test objective, expected outcome, actual outcome, and any caveat. Redact all account IDs, ARNs, endpoint identifiers, public IPs, email addresses, certificates, private keys, and other secrets.
