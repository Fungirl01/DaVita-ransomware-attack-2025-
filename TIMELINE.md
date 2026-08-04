# Timeline — DaVita Ransomware Incident (2025)

This timeline is a reconstructed, hypothetical timeline built from public reporting and typical attacker behaviors. Use it as a template to capture artifacts and evidence.

- Late March 2025 — Initial Compromise (estimated)
  - Probable initial vector: phishing email to billing/admin OR third-party vendor account compromise.
  - Attacker obtains valid credentials and establishes a foothold.

- Early April 2025 — Lateral Movement & Reconnaissance
  - Attacker performs internal reconnaissance, maps shares, and escalates privileges.
  - Possible data staging and compression of sensitive repositories.

- April 10–12, 2025 — Data Exfiltration & Encryption
  - Significant exfiltration of patient data (estimated ~2.7M records).
  - Ransomware deployment and encryption of portions of the environment.
  - Discovery and detection on/around April 12, 2025.

- April 12–mid April 2025 — Response & Containment
  - Incident response engagement, system isolation, and restoration activities initiated.
  - Public disclosure and breach notifications prepared.

- Post-incident — Remediation & Notification
  - Forensics and remediation efforts ongoing; regulatory notifications and patient outreach.

Recommended fields to capture for each event in your internal timeline
- Timestamp (UTC)
- Hostname / IP / User account
- Event type (login, file access, process create, outbound transfer)
- Evidence artifacts (log file locations, EDR IDs, forensic image hashes)
- Action taken & owner

IOC placeholders (collect and expand during investigation)
- IP addresses: <ADD_COLLECTED_IPS>
- Domains: <ADD_MALICIOUS_DOMAINS>
- Filenames/hash samples: <ADD_HASHES>
- Suspicious accounts: <ADD_USERNAMES>
