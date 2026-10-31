# Scripts

Only add scripts that are part of the project and have been reviewed for safe publication.

Before committing:
- Remove hard-coded credentials, tokens, private keys, account identifiers, and personal data.
- Replace environment-specific values with documented variables or placeholders.
- Add a usage section and prerequisites.
- Explain whether a script creates billable AWS resources or deletes resources.
- Test destructive cleanup scripts in a safe environment and require explicit confirmation where appropriate.
- Do not publish VPN profiles containing embedded private keys.

The final report mentions an automated CLI teardown script. Add it here only after confirming that the team has the actual script, that it contains no secrets, and that its destructive behavior is clearly documented.
