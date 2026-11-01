# Connectivity and Hybrid Networking

## VPC Peering

A peering connection was created between the production and shared-services VPCs. Route-table entries were added for the relevant peer CIDRs. The database route table was intentionally left without a peering route to preserve isolation.

## VPC Endpoints

The report documents:
- An S3 Gateway Endpoint associated with the relevant production route tables.
- Interface endpoints for Systems Manager and related messaging, logging, key-management, and secrets-management services.
- Additional Systems Manager endpoints in the shared VPC to allow the shared bastion to register without an internet gateway or NAT.

The exact endpoint list and final state should be checked against the sanitized evidence before publication.

## AWS PrivateLink

An internal Network Load Balancer, endpoint service, and consumer interface endpoint were used to provide private application access from the shared-services VPC. The report records a successful TCP connectivity check and HTTP 200 response through the endpoint DNS name.

## Transit Gateway

The project configured a Transit Gateway hub and attachments to demonstrate scalable hub-and-spoke connectivity. The lab resources were removed during final cleanup.

## Site-to-Site VPN

The VPN was configured with a simulated customer gateway and a static on-premises CIDR. The report records the tunnels as down by design because the customer gateway was simulated rather than a live on-premises VPN device.

## Client VPN

The report records an initial failed reachability test, followed by a successful verification after rebuilding the lab environment. The successful run included connectivity checks and browser/HTTP access to the private production server through the VPN tunnel.

## AWS Direct Connect

Direct Connect was a concepts-only deliverable. It was not deployed because the lab did not have the required physical colocation or partner circuit and the associated cost was outside the lab's cost constraints.

