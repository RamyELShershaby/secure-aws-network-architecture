# Monitoring, Threat Hunting, and Incident Response

## Telemetry

The documented monitoring stack includes:
- VPC Flow Logs for network-flow visibility.
- Amazon Athena with a partitioned table and four threat-hunting queries.
- CloudWatch dashboards and alarms.
- SNS notifications.
- CloudTrail for AWS API activity.
- GuardDuty and Security Hub for security findings and posture visibility.

## Automated quarantine

The report documents an EventBridge-to-Lambda response path intended to quarantine a suspected EC2 instance by applying a deny rule in a Network ACL. The runbook should explain the event trigger, validation conditions, action taken, verification, rollback, and human approval/escalation points.

Automated containment can interrupt legitimate traffic. In a production design, use narrowly scoped rules, least-privilege Lambda permissions, audit logging, alerting, and a documented recovery procedure.

## Traffic mirroring and simulation

Traffic Mirroring was configured as a lab exercise and later removed during teardown. The report also documents a live incident-response simulation and an operational runbook.

## Sample findings versus real incidents

GuardDuty sample findings are test fixtures. They should be labeled as sample data in the README, screenshots, and presentation and must not be described as real detected attacks.

## Suggested evidence

- Sanitized CloudWatch dashboard screenshot.
- Sanitized Athena query and result screenshots.
- A redacted alert sample.
- A high-level incident-response flow diagram.
- A test log showing the quarantine action and the rollback/recovery procedure.

Never commit access tokens, secrets, private keys, or raw logs containing sensitive personal or infrastructure details.
