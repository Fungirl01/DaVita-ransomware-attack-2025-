# Incident Response Playbook — Healthcare Ransomware (DaVita 2025)

Purpose
- A step-by-step playbook for technical responders, leadership, legal, and communications during a suspected or confirmed ransomware incident in a healthcare environment.

Scope
- Applies to incidents involving suspected credential compromise, data exfiltration, and ransomware deployment that may affect PHI and clinical operations.

Initial detection & triage (first 0–4 hours)
1. Declare incident and assemble IR team: Incident Response Lead, SOC Lead, Forensics, IT Ops, Legal/GRC, Communications, Clinical leadership, Vendor management.
2. Capture high-level facts: detection time, affected systems, scope, initial indicators (IP, user, hashes), and suspected data types.
3. Preserve evidence: snapshot volatile memory if possible, isolate affected hosts (network isolation, not immediate disk power-off), and collect logs (SIEM, EDR, VPN, domain controllers, mail servers).
4. Activate communications channel (out-of-band) for IR team coordination.

Containment (4–24 hours)
- Short-term containment
  - Isolate confirmed infected hosts from network (switch ports, NAC, or host-based firewall rules).
  - Disable compromised user accounts and any service accounts suspected to be abused.
  - Block attacker C2 IPs/domain indicators at perimeter and on endpoint controls.
- Avoid broad wipes or mass reboots until forensic collection is complete.

Forensic investigation (0–72 hours)
- Acquire forensic images of compromised endpoints and critical servers (full disk images and memory dumps).
- Collect logs: EDR telemetry, SIEM events, VPN logs, RDP sessions, Windows security/event logs, domain controller logs, cloud provider logs, backup logs.
- Build a timeline of attacker activity (first access, lateral movement, data exfil, encryption staging, encryption start).
- Identify persistence, scheduled tasks, new user accounts, and unauthorized privileged accounts.
- Determine exfiltration scope (which data repositories, S3 buckets, FTP transfers, or cloud storage).

Eradication and remediation (72 hours–weeks)
- Remove persistence mechanisms (malicious scheduled tasks, new services, web shells, backdoors).
- Patch known exploited vulnerabilities and update exposed services.
- Reset credentials for compromised users, privileged accounts, and API keys. Force password changes and rotate secrets.
- Rebuild compromised systems from known-good images where practical.
- Reconnect systems to the network in a controlled manner with heightened monitoring.

Recovery and restoration
- Validate backups (offline/immutable) and restore systems using tested procedures.
- Bring systems back online incrementally, starting with non-critical services and monitoring for re-infection.
- Re-enable accounts and services after verification.

Legal, regulatory, and external engagement
- Notify Legal/GRC immediately to track HIPAA notification requirements and coordinate with counsel.
- Preserve chain of custody for all forensic artifacts.
- Consider engaging external forensics and IR specialists and law enforcement; contact FBI/Secret Service as appropriate for extortion data and criminal activity.

Patient & public communications
- Work with Communications and Legal to prepare statements for patients, employees, and regulators.
- Provide actionable guidance for affected patients (credit monitoring, identity theft steps) if PHI was exposed.

Post-incident (remediation & lessons learned)
- Conduct a full post-mortem: timeline, root cause, controls gap analysis, and prioritized remediation plan.
- Implement recommended controls from remediation plan and verify with audits/assessments.
- Run crisis simulations and tabletop exercises incorporating lessons learned.

Playbook appendices
- Evidence collection checklist
- Chain-of-custody template
- Forensics triage checklist
- Communications templates
- HIPAA reporting thresholds and timelines (state-by-state considerations)

Notes
- Always coordinate clinical continuity decisions with clinical leadership to ensure patient safety during containment and recovery.