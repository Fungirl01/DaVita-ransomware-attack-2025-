# Mitigation Checklist — Prioritized Controls

Quick wins (days)
- Enforce MFA (phishing-resistant when possible) for all remote access and privileged accounts.
- Block legacy remote access protocols (unrestricted RDP) from the internet; require VPN plus MFA and allowlisting.
- Reset credentials for suspicious or high-risk accounts and enforce strong password policies.
- Enable logging and centralize logs (SIEM) from endpoints, domain controllers, network devices, VPN, and cloud services.
- Schedule and run targeted phishing simulations for billing/admin users.

Near-term (weeks)
- Deploy or tune EDR across all endpoints and enable 24/7 alerting or managed detection.
- Implement network segmentation between corporate, clinical, backup, and third-party networks.
- Harden and patch externally facing assets (VPN appliances, jump hosts) and remove unsupported services.
- Audit and reduce privileged accounts; apply least privilege for service accounts and admin roles.
- Ensure offline, immutable backups are taken regularly and test restores.

Medium-term (1–6 months)
- Implement Zero Trust network controls (micro-segmentation, conditional access).
- Formalize vendor risk management program: least-privileged third-party access, contractual security requirements, and periodic assessments.
- Conduct tabletop exercises and red-team simulations focused on phishing and lateral movement.
- Deploy data-loss prevention (DLP) for sensitive PHI repositories.

Long-term (6+ months)
- Architect resiliency and disaster recovery plans for clinical systems, with RTO/RPO targets aligned to patient care needs.
- Continuous threat hunting and mature SOC capabilities with runbook automation for common threats.
- Invest in identity security: hardware-backed keys for administrators, IAM posture management, and privileged access management (PAM).

Metrics to track
- Mean time to detect (MTTD) and mean time to respond (MTTR).
- Number of successful phishing clicks in simulations.
- Percentage of endpoints covered by EDR and telemetry quality score.
- Backup recovery success rate and time to recovery for priority systems.

Owner recommendations
- CISOs: prioritize funding for EDR, backups, and identity hardening.
- IT Ops: schedule patching cadence and validate backup integrity.
- Security Ops: implement SOC playbooks and detection coverage for lateral movement and exfil.