# Evidence and Test Results

Store only reviewed, sanitized evidence here.

Suggested structure:
```text
evidence/
├── screenshots/
│   ├── 01-network-foundation/
│   ├── 02-security-segmentation/
│   ├── 03-hybrid-connectivity/
│   ├── 04-edge-security/
│   └── 05-monitoring-ir-dr/
└── test-results/
    ├── segmentation-tests.md
    └── connectivity-tests.md
```

For each item, record:
- Test or task ID.
- Objective and expected result.
- Actual result.
- Date/run context if useful.
- Limitations or evidence gaps.

Before committing, inspect both the image and its metadata. Redact account IDs, ARNs, resource IDs, IPs, endpoints, email addresses, credentials, certificates, private keys, and unrelated account details. Do not commit raw VPN configuration files.
