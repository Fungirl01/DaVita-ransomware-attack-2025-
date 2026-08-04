# DaVita Ransomware Attack (2025) — Executive Summary

This repository documents an executive summary and response guidance for the DaVita ransomware attack discovered April 12, 2025. It is intended as a reference for security teams, executives, and incident responders in healthcare organizations.

## What happened
- In early 2025, a major ransomware group known as "Interlock" gained access to DaVita's networks in late March 2025 and operated undetected for several weeks.
- The attackers performed reconnaissance, moved laterally, exfiltrated a large amount of sensitive data (approximately 2.7 million patients), and deployed ransomware that encrypted parts of the environment before the intrusion was discovered on April 12, 2025.
- Stolen data reportedly included names, addresses, dates of birth, Social Security numbers, insurance and clinical information (including dialysis test results). The attackers posted proof to pressure the victim.

## Likely root causes (hypotheses)
- Phishing: An employee in billing or administration likely clicked a malicious link or opened an infected attachment. Compromised credentials were used for privilege escalation and lateral movement.
- Unpatched/exposed remote access: An exposed VPN, RDP, or other remote-access tool without multifactor authentication could have been exploited.
- Third-party compromise: A vendor or partner with network access (medical device supplier, billing partner) may have been the initial breach vector.
- Long dwell time suggests insufficient network monitoring and endpoint detection to catch the attack before data theft and encryption.

## Impact across the CIA triad
- Confidentiality: Extensive data exfiltration of protected health information (PHI) and PII for ~2.7M patients.
- Integrity: Ransomware encrypted files, and prolonged attacker access raises risk of record tampering or hidden persistence/backdoors.
- Availability: Parts of DaVita's internal IT systems were taken offline and manual processes were used to sustain patient care; operations and revenue were disrupted.

## Prevention / Recommended Controls
- Deploy phishing-resistant MFA (hardware security keys, platform-based biometrics) for all remote and privileged access.
- Implement network segmentation: separate workstations, clinical systems, and backups; enforce least privilege.
- 24/7 SOC with EDR and proactive threat hunting to detect lateral movement and data exfiltration early.
- Maintain offline, immutable backups to enable recovery without paying ransom.
- Apply rigorous patch management and limit exposed remote access (VPN/RDP) with strong authentication and allowlisting.
- Conduct frequent phishing simulations and role-based user training.
- Enforce vendor risk management: review third-party access, contracts, and security posture.

## Business impact (typical outcomes)
- Direct costs: incident response, forensics, legal, regulatory fines, potential ransom payments, estimated in the millions to tens of millions.
- Operational losses: lost revenue and productivity during system outages; manual workarounds impacting time-sensitive dialysis services.
- Reputational damage and patient trust erosion; potential class-action lawsuits from affected patients.
- Regulatory and legal consequences: HIPAA breach notifications, state AG investigations, and potential fines or settlements.

## Incident response roles involved
- SOC Analysts (Tier 1–3): detection, triage, and escalation.
- Incident Response Lead: coordination of containment, eradication, and recovery.
- Forensics Analysts: timeline, root cause, and data-exfiltration assessment.
- Threat Hunters: proactive discovery of hidden activity and persistence.
- GRC / Legal: HIPAA notifications, regulatory reporting, and communication with authorities.
- Cloud / IAM Analysts: reset credentials, reconfigure access, and enforce MFA.
- Communications Lead: internal and external messaging to patients, staff, and the public.
- Vendor Risk Analyst: assess third-party involvement and remediation for partner access.

## Suggested next artifacts (this repo)
- IR_PLAYBOOK.md — a tailored incident response playbook for healthcare ransomware.
- MITIGATION_CHECKLIST.md — prioritized technical controls and remediation steps.
- TIMELINE.md — a concise technical timeline with evidence and IOCs.
- Detection rules (SIGMA / SIEM) for suspicious authentication, RDP/VPN anomalies, data exfil patterns, and ransomware behavior.

---

This README is a summary based on publicly available reporting and typical forensic analysis of similar healthcare ransomware incidents. It is not an official DaVita post‑mortem.
