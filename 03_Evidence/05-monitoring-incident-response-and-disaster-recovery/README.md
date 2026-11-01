# Monitoring, Incident Response and Disaster Recovery

## Evidence 01
![Screenshot](01-target-group-prod-tg-baseline-health.png)

Original Caption:
Figure 1.1 — Target Group (prod-tg) Baseline Health Verification

## Evidence 02
![Screenshot](02-amazon-sns-topic-security-alerts-confirmed.png)

Original Caption:
Figure 1.2 — Amazon SNS Topic (security-alerts) & Confirmed Email Subscription

## Evidence 03
![Screenshot](03-vpc-flow-logs-prod-vpc-flow.png)

Original Caption:
Figure 1.3 — VPC Flow Logs (prod-vpc-flow-logs) Enabled on Production VPC

## Evidence 04
![Screenshot](04-s3-bucket-storage-of-partitioned-vpc.png)

Original Caption:
Figure 1.4 — S3 Bucket Storage of Partitioned VPC Flow Log Objects

## Evidence 05
![Screenshot](05-cloudwatch-operational-dashboard-prod-network-dashboard.png)

Original Caption:
Figure 1.5 — CloudWatch Operational Dashboard (prod-network-dashboard)

## Evidence 06
![Screenshot](06-cloudwatch-security-availability-alarms.png)

Original Caption:
Figure 1.6 — CloudWatch Security & Availability Alarms

## Evidence 07
![Screenshot](07-aws-lambda-auto-quarantine-function-auto.png)

Original Caption:
Figure 1.7 — AWS Lambda Auto-Quarantine Function (auto-quarantine-instance)

## Evidence 08
![Screenshot](08-iam-execution-role-lambda-quarantine-role.png)

Original Caption:
Figure 1.8 — IAM Execution Role (lambda-quarantine-role)

## Evidence 09
![Screenshot](09-quarantine-security-group-sg-quarantine-sg.png)

Original Caption:
Figure 1.9 — Quarantine Security Group (sg quarantine / sg-0482c6acfff859286)

## Evidence 10
![Screenshot](10-cloudwatch-log-stream-verification-aws-lambda.png)

Original Caption:
Figure 1.10 — CloudWatch Log Stream Verification (/aws/lambda/auto-quarantine-instance)

## Evidence 11
![Screenshot](11a-amazon-eventbridge-rule-guardduty-to-quarantine.png)

![Screenshot](11b-amazon-eventbridge-rule-guardduty-to-quarantine.png)

Original Caption:
Figure 1.11 — Amazon EventBridge Rule (guardduty-to-quarantine) Event Pattern & Targets

## Evidence 12
![Screenshot](12a-vpc-traffic-mirror-target-session-creation.png)

![Screenshot](12b-vpc-traffic-mirror-target-session-creation.png)

![Screenshot](12c-vpc-traffic-mirror-target-session-creation.png)

Original Caption:
Figure 1.12 — VPC Traffic Mirror Target, Session Creation & Teardown (prod-ec2a-mirror)

## Evidence 13
![Screenshot](13-vxlan-encapsulated-packet-capture-on-collector.png)

Original Caption:
Figure 1.13 — VXLAN Encapsulated Packet Capture on Collector Instance (prod-ec2-b)

## Evidence 14
![Screenshot](14a-step-8-t56-athena-external-table.png)

![Screenshot](14b-step-8-t56-athena-external-table.png)

Original Caption:
Figure 1.14 — Step 8 (T56): Athena External Table Validation (vpc_logs.flow_logs)

## Evidence 15
![Screenshot](15a-step-9-t57-query-1-rejected.png)

![Screenshot](15b-step-9-t57-query-1-rejected.png)

Original Caption:
Figure 1.15 — Step 9 (T57 - Query 1): Rejected Traffic Analysis (Port Scans & NACL Blocks)

## Evidence 16
![Screenshot](16-step-9-t57-query-2-top.png)

Original Caption:
Figure 1.16 — Step 9 (T57 - Query 2): Top Outbound Data Transfers (Exfiltration Detection)

## Evidence 17
![Screenshot](17a-step-9-t57-query-3-unusual.png)

![Screenshot](17b-step-9-t57-query-3-unusual.png)

Original Caption:
Figure 1.17 — Step 9 (T57 - Query 3): Unusual Port Access (Lateral Movement & Ephemeral Ports)

## Evidence 18
![Screenshot](18a-step-9-step-10b-t57-query.png)

![Screenshot](18b-step-9-step-10b-t57-query.png)

![Screenshot](18c-step-9-step-10b-t57-query.png)

Original Caption:
Figure 1.18 — Step 9 & Step 10B (T57 - Query 4 & IR Detection): Suspicious C2 / Mining Ports

## Evidence 19
![Screenshot](19a-step-10c-triage-scoping-malicious-c2.png)

![Screenshot](19b-step-10c-triage-scoping-malicious-c2.png)

Original Caption:
Figure 1.19 — Step 10C (Triage): Scoping Malicious C2 Connections from prod-ec2-a

## Evidence 20
![Screenshot](20-step-10d-isolate-immediate-containment-via.png)

Original Caption:
Figure 1.20 — Step 10D (Isolate): Immediate Containment via sg-quarantine Attachment

## Evidence 21
![Screenshot](21-step-10e-preserve-instance-metadata-export.png)

Original Caption:
Figure 1.21 — Step 10E (Preserve): Instance Metadata Export & EBS Forensic Snapshot

## Evidence 22
![Screenshot](22-step-10f-contain-subnet-level-blackholing.png)

Original Caption:
Figure 1.22 — Step 10F (Contain): Subnet-Level Blackholing via Private NACL Rule #50

## Evidence 23
![Screenshot](23-step-10g-recover-security-group-restoration.png)

Original Caption:
Figure 1.23 — Step 10G (Recover): Security Group Restoration, Target Health & Live App Verification

## Evidence 24
![Screenshot](24-step-10h-notify-incident-resolution-broadcast.png)

Original Caption:
Figure 1.24 — Step 10H (Notify): Incident Resolution Broadcast via Amazon SNS
