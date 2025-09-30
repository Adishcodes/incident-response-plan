# Incident Response Plan — Malware Infection

## 1. Purpose
This document defines the steps to detect, contain, eradicate, recover from, and learn following a malware infection affecting organizational systems.

## 2. Scope
Applies to all workstations, servers, cloud resources, and mobile devices owned or administered by the organization.

## 3. Definitions
- **Incident**: Any confirmed or suspected unauthorized access, malware infection, or data compromise.
- **Malware**: Malicious software including ransomware, trojans, worms, spyware, or other unwanted programs.

## 4. Incident Response Phases
1. **Preparation**
   - Keep backups offline and tested.
   - Ensure AV/EDR and logging are enabled.
   - Maintain contact list and escalation matrix (see Roles file).
   - Regular training & phishing awareness.

2. **Identification (Detection)**
   - Indicators:
     - AV/EDR alerts, unusual CPU/disk/network load
     - Pop-ups, ransom notes, encrypted files
     - Unusual outbound connections or beaconing
     - User reports of unexpected behavior
   - Tools:
     - Antivirus/EDR console, SIEM, network flow logs, endpoint logs
   - Action:
     - Triage alert severity (Low / Medium / High / Critical)
     - Record timestamp, affected host(s), user(s), observed indicators

3. **Containment**
   - **Short-term (Immediate):**
     - Isolate affected device(s) from network (unplug Ethernet / disable Wi‑Fi).
     - Disable affected user accounts if credential compromise suspected.
     - Take screenshots of ransom notes or suspicious UI.
     - Preserve volatile evidence (see Evidence Checklist).
   - **Long-term:**
     - Block malicious IPs/domains at firewall.
     - Apply network segmentation to stop lateral movement.

4. **Eradication**
   - Identify root cause (phishing, unpatched service, removable media).
   - Remove malware: clean with AV/EDR tools or reimage compromised systems.
   - Patch vulnerable software, rotate credentials, revoke possibly compromised certs.

5. **Recovery**
   - Restore from clean backups to verified systems.
   - Monitor recovered systems for recurrence (increased logging & EDR watch).
   - Return systems to production in stages (start with least-risky systems).

6. **Lessons Learned**
   - Conduct a post-incident review within 7–14 days.
   - Document timeline, root cause, impact, and gaps.
   - Update controls, playbooks, and training.

## 5. Severity Classification (example)
- **Low**: Single workstation with removable adware, no data access.
- **Medium**: Multiple workstations, limited lateral movement, no encryption.
- **High**: Ransomware encrypting files on critical systems.
- **Critical**: Widespread encryption or exfiltration of sensitive data.

## 6. Reporting & Escalation
- All incidents must be reported to IT Security immediately.
- For High/Critical incidents, notify management, legal, and external incident responders.

## 7. Evidence & Chain of Custody
- Preserve logs and images, note who accessed evidence and actions taken.
- Use secure storage and hash files (sha256) when moving evidence.

## 8. Communication
- Follow the Communication Templates file for internal/external messages.
- Limit public statements until legal/management approves.

## 9. Roles & Responsibilities
See `roles-and-responsibilities.md`.

## 10. Post-Incident Actions
- Apply patches and enforce mitigations
- Run additional scans across environment
- Mandatory security awareness refresher for affected users
- Update incident response playbook and documentation

---

*Keep this IRP under revision control. Update annually or after any incident.*
