# Connectivity and Hybrid Networking

## Evidence 01
![Screenshot](01-peering-settings-requester-prod-vpc-10.png)

Original Caption:
Figure: Peering settings: requester prod-vpc (10.0.0.0/16).

## Evidence 02
![Screenshot](02-accepter-shared-vpc-10-1-0.png)

Original Caption:
Figure: Accepter shared-vpc (10.1.0.0/16) and Name tag.

## Evidence 03
![Screenshot](03-request-created-pending-acceptance.png)

Original Caption:
Figure: Request created: Pending acceptance.

## Evidence 04
![Screenshot](04-accept-vpc-peering-connection-request.png)

Original Caption:
Figure: Accept VPC peering connection request.

## Evidence 05
![Screenshot](05-peering-connection-status-active.png)

Original Caption:
Figure: Peering connection status: Active.

## Evidence 06
![Screenshot](06-rt-private-adding-10-1-0.png)

Original Caption:
Figure: rt-private: adding 10.1.0.0/16 → peering connection.

## Evidence 07
![Screenshot](07-rt-private-routes-updated-successfully.png)

Original Caption:
Figure: rt-private: routes updated successfully.

## Evidence 08
![Screenshot](08-rt-public-adding-the-peering-route.png)

Original Caption:
Figure: rt-public: adding the peering route.

## Evidence 09
![Screenshot](09-rt-public-routes-updated-successfully.png)

Original Caption:
Figure: rt-public: routes updated successfully.

## Evidence 10
![Screenshot](10-rt-shared-adding-10-0-0.png)

Original Caption:
Figure: rt-shared: adding 10.0.0.0/16 → peering connection.

## Evidence 11
![Screenshot](11-rt-shared-routes-10-0-0.png)

Original Caption:
Figure: rt-shared routes: 10.0.0.0/16 → pcx (Active) and local.

## Evidence 12
![Screenshot](12-selecting-the-s3-service-of-type.png)

Original Caption:
Figure: Selecting the S3 service of type Gateway (not Interface, not s3express).

## Evidence 13
![Screenshot](13-route-tables-selected-rt-private-rt.png)

Original Caption:
Figure: Route tables selected: rt-private, rt-db, rt-public.

## Evidence 14
![Screenshot](14-prod-s3-gateway-created-available.png)

Original Caption:
Figure: prod-s3-gateway created: Available.

## Evidence 15
![Screenshot](15-route-tables-tab-of-the-endpoint.png)

Original Caption:
Figure: Route tables tab of the endpoint.

## Evidence 16
![Screenshot](16-example-ssmmessages-private-dns-enabled-and.png)

Original Caption:
Figure: Example (ssmmessages): Private DNS enabled and the two private subnets.

## Evidence 17
![Screenshot](17-example-security-group-sg-endpoints-selected.png)

Original Caption:
Figure: Example: security group Sg-endpoints selected.

## Evidence 18
![Screenshot](18-kms-endpoint-created-available.png)

Original Caption:
Figure: kms endpoint created: Available.

## Evidence 19
![Screenshot](19-secretsmanager-endpoint-created-available.png)

Original Caption:
Figure: secretsmanager endpoint created: Available.

## Evidence 20
![Screenshot](20-all-7-endpoints-in-prod-vpc.png)

Original Caption:
Figure: All 7 endpoints in prod-vpc (1 Gateway + 6 Interface): Available.

## Evidence 21
![Screenshot](21-creating-shared-endpoints-sg-in-shared.png)

Original Caption:
Figure: Creating shared-endpoints-sg in shared-vpc.

## Evidence 22
![Screenshot](22-shared-endpoints-sg-created.png)

Original Caption:
Figure: shared-endpoints-sg created.

## Evidence 23
![Screenshot](23-shared-ssm-endpoint-vpc-shared-vpc.png)

Original Caption:
Figure: shared-ssm-endpoint: VPC shared-vpc with Private DNS enabled.

## Evidence 24
![Screenshot](24-all-10-endpoints-available-7-in.png)

Original Caption:
Figure: All 10 endpoints Available (7 in prod-vpc + 3 in shared-vpc).

## Evidence 25
![Screenshot](25-all-three-instances-running-2-2.png)

Original Caption:
Figure: All three instances running (2/2 status checks).

## Evidence 26
![Screenshot](26-fleet-manager-prod-ec2-a-prod.png)

Original Caption:
Figure: Fleet Manager: prod-ec2-a, prod-ec2-b and shared-bastion are Online (SSM works through the endpoints).

## Evidence 27
![Screenshot](27-first-attempt-curl-from-the-bastion.png)

Original Caption:
Figure: First attempt: curl from the bastion timed out (root cause in Section 9, issue 2).

## Evidence 28
![Screenshot](28-after-the-fix-curl-returns-the.png)

Original Caption:
Figure: After the fix: curl returns the application page through the peering. ICMP ping is blocked by design.

## Evidence 29
![Screenshot](29-from-prod-ec2-a-aws-s3.png)

Original Caption:
Figure: From prod-ec2-a: aws s3 ls succeeds with no public IP.

## Evidence 30
![Screenshot](30-nslookup-of-the-s3-endpoint-from.png)

Original Caption:
Figure: nslookup of the S3 endpoint from prod-ec2-a (the gateway endpoint works at routing level, not DNS).

## Evidence 31
![Screenshot](31-rt-private-the-s3-prefix-list.png)

Original Caption:
Figure: rt-private: the S3 prefix list (pl-63a5400a) routes to the gateway endpoint, which is more specific than

## Evidence 32
![Screenshot](32-rebuilt-environment-rt-private-routes-s3.png)

Original Caption:
Figure: Rebuilt environment: rt-private routes (S3 prefix list and peering).

## Evidence 33
![Screenshot](33-rebuilt-environment-rt-shared-private-routes.png)

Original Caption:
Figure: Rebuilt environment: rt-shared-private routes 10.0.0.0/16 to the peering.

## Evidence 34
![Screenshot](34-rebuilt-environment-vpc-endpoints-available.png)

Original Caption:
Figure: Rebuilt environment: VPC endpoints Available.

## Evidence 35
![Screenshot](35-rebuilt-environment-ssm-session-on-shared.png)

Original Caption:
Figure: Rebuilt environment: SSM session on shared-bastion, ping 0% loss and curl to prod-ec2-a (10.0.10.123:8080) over the peering.

## Evidence 36
![Screenshot](36-prod-tgw-created-available.png)

Original Caption:
Figure: prod-tgw created: Available.

## Evidence 37
![Screenshot](37-two-vpc-attachments-available-and-associated.png)

Original Caption:
Figure: Two VPC attachments Available and associated with the TGW route table.

## Evidence 38
![Screenshot](38-tgw-route-table-both-cidrs-propagated.png)

Original Caption:
Figure: TGW route table: both CIDRs propagated and Active.

## Evidence 39
![Screenshot](39-rt-private-10-1-0-0.png)

Original Caption:
Figure: rt-private: 10.1.0.0/16 now targets the Transit Gateway.

## Evidence 40
![Screenshot](40-rt-shared-10-0-0-0.png)

Original Caption:
Figure: rt-shared: 10.0.0.0/16 now targets the Transit Gateway.

## Evidence 41
![Screenshot](41-curl-from-the-bastion-to-prod.png)

Original Caption:
Figure: curl from the bastion to prod-ec2-a succeeds with the peering routes replaced by the TGW. Path: bastion (10.1.10.130) → rt-shared → TGW → prod attachment → prod-ec2-a.

## Evidence 42
![Screenshot](42-prod-vgw-attached-to-prod-vpc.png)

Original Caption:
Figure: prod-vgw attached to prod-vpc.

## Evidence 43
![Screenshot](43-creating-the-customer-gateway-onprem-cgw.png)

Original Caption:
Figure: Creating the customer gateway onprem-cgw (203.0.113.10, ASN 65000).

## Evidence 44
![Screenshot](44-vpn-connection-settings-static-routing-local.png)

Original Caption:
Figure: VPN connection settings: static routing, local CIDR 192.168.0.0/16.

## Evidence 45
![Screenshot](45-prod-vpn-created-available-attached-to.png)

Original Caption:
Figure: prod-vpn created: Available (attached to the VGW).

## Evidence 46
![Screenshot](46-t35-tunnel-details-both-tunnels-are.png)

Original Caption:
Figure: T35 – Tunnel details: both tunnels are Down (expected: the customer gateway is simulated) while provisioning status is Available.

## Evidence 47
![Screenshot](47-t35-static-routes-of-the-vpn.png)

Original Caption:
Figure: T35 – Static routes of the VPN connection.

## Evidence 48
![Screenshot](48-t35-download-configuration-dialog-generic-generic.png)

Original Caption:
Figure: T35 – Download configuration dialog (Generic / Generic / Vendor Agnostic / IKEv1).

## Evidence 49
![Screenshot](49-detaching-the-vgw-delete-stays-disabled.png)

Original Caption:
Figure: Detaching the VGW: delete stays disabled until the detachment completes.

## Evidence 50
![Screenshot](50-aws-vpn-client-profile-prod-client.png)

Original Caption:
Figure: AWS VPN Client: profile prod-client-vpn is Connected (first attempt).

## Evidence 51
![Screenshot](51-client-vpn-endpoint-prod-client-vpn.png)

Original Caption:
Figure: Client VPN endpoint prod-client-vpn: Available, with two connections listed.

## Evidence 52
![Screenshot](52-endpoint-details-tcp-443-split-tunnel.png)

Original Caption:
Figure: Endpoint details (TCP 443, split tunnel, security group) and the target network association: Associated.

## Evidence 53
![Screenshot](53-connections-tab-two-client-sessions-from.png)

Original Caption:
Figure: Connections tab: two client sessions from the 10.100.0.0/22 pool.

## Evidence 54
![Screenshot](54-powershell-unstable-first-carrier-75-loss.png)

Original Caption:
Figure: PowerShell: unstable first carrier (75% loss to 8.8.8.8), then ping to 10.0.10.123 with 0% loss over the tunnel.

## Evidence 55
![Screenshot](55-powershell-http-request-to-10-0.png)

Original Caption:
Figure: PowerShell: HTTP request to 10.0.10.123:8080 returns StatusCode 200.

## Evidence 56
![Screenshot](56-full-windows-desktop-proof-active-openvpn.png)

Original Caption:
Figure: Full Windows Desktop Proof — Active OpenVPN Tray Icon & PowerShell HTTP 200 Verification — Complete desktop capture showing the active OpenVPN GUI connection indicator in the Windows system tray alongside the PowerShell terminal receiving HTTP 200 OK from the private EC2 server 10.0.10.123.

## Evidence 57
![Screenshot](57-browser-access-to-http-10-0.png)

Original Caption:
Figure: Browser access to http://10.0.10.123:8080 through the Client VPN.

## Evidence 58
![Screenshot](58-production-private-route-table-rtb-002e3e2730b093207.png)

Original Caption:
Figure 1: Production Private Route Table (rtb-002e3e2730b093207) — Active route directing 10.1.0.0/16 traffic across VPC Peering connection pcx-078460e96c5a00631 and S3 traffic via Gateway Endpoint vpce-0d4ecf22223991677.

## Evidence 59
![Screenshot](59-shared-services-private-route-table-rtb.png)

Original Caption:
Figure 2: Shared Services Private Route Table (rtb-04dba9e8bc78d1324) — Active symmetric route directing 10.0.0.0/16 traffic back to prod-vpc via pcx-078460e96c5a00631.

## Evidence 60
![Screenshot](60-provisioned-vpc-endpoints-in-us-east.png)

Original Caption:
Figure 3: Provisioned VPC Endpoints in us-east-1 — All seven VPC Endpoints (1 Gateway Endpoint for S3 and 6 Interface Endpoints for SSM) showing Status = Available.

## Evidence 61
![Screenshot](61-cross-vpc-connectivity-verification-via-ssm.png)

Original Caption:
Figure 4: Cross-VPC Connectivity Verification via SSM Session Manager — Successful ICMP ping (0% packet loss, ~0.2ms latency) and HTTP curl response ('<h1>Hello from Prod-EC2-A (10.0.10.123) - Reached Privately!</h1>') from shared-bastion to prod-ec2-a.

## Evidence 62
![Screenshot](62-local-windows-powershell-diagnosing-packet-loss.png)

Original Caption:
Figure 5: Local Windows PowerShell — Diagnosing Packet Loss & Pinging Private Server (10.0.10.123) — Initial pings to 8.8.8.8 showing 25%–75% packet loss prior to hotspot bypass, followed by 0% packet loss (4/4 received, ~305ms average RTT) when pinging the private EC2 instance 10.0.10.123 over the active Client VPN tunnel.

## Evidence 63
![Screenshot](63-local-windows-powershell-http-200-ok.png)

Original Caption:
Figure 6: Local Windows PowerShell — HTTP 200 OK Response over Client VPN — Executing Invoke-WebRequest / curl against http://10.0.10.123:8080 from the local Windows PowerShell terminal, returning StatusCode 200 OK and '<h1>Hello from Prod-EC2-A (10.0.10.123) - Reached Privately!</h1>'.

## Evidence 64
![Screenshot](64-local-desktop-web-browser-accessing-private.png)

Original Caption:
Figure 7: Local Desktop Web Browser — Accessing Private EC2 Web Server (http://10.0.10.123:8080) — Direct browser verification on the local machine rendering the private web page hosted on 10.0.10.123 inside prod-private-a over the encrypted VPN tunnel.

## Evidence 65
![Screenshot](65-aws-console-both-client-vpn-connections.png)

Original Caption:
Figure 8: AWS Console — Both Client VPN Connections Active Simultaneously (Simulation + Local Laptop) — The Client VPN Endpoint (cvpn-endpoint-053c30ff1d8369afa) Connections tab confirming two concurrent Active sessions using client1.vpn.local: Client IP

## Evidence 66
![Screenshot](66-full-windows-desktop-proof-active-openvpn.png)

Original Caption:
Figure 9: Full Windows Desktop Proof — Active OpenVPN Tray Icon & PowerShell HTTP 200 Verification — Complete desktop capture showing the active OpenVPN GUI connection indicator in the Windows system tray alongside the PowerShell terminal receiving HTTP 200 OK from the private EC2 server 10.0.10.123.
