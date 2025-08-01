# Master Security Incident Response Playbook

## Guide for Comprehensive Cybersecurity Incident Management

* * *

## Table of Contents

- [Master Security Incident Response Playbook](#master-security-incident-response-playbook)
    - [Guide for Comprehensive Cybersecurity Incident Management](#guide-for-comprehensive-cybersecurity-incident-management)
    - [Table of Contents](#table-of-contents)
    - [1. Executive Summary](#1-executive-summary)
    - [2. Incident Classification Matrix](#2-incident-classification-matrix)
    - [2.1 Severity Levels](#21-severity-levels)
    - [2.2 Incident Categories](#22-incident-categories)
    - [3. Team Roles & Responsibilities](#3-team-roles--responsibilities)
    - [3.1 Incident Commander (IC)](#31-incident-commander-ic)
    - [3.2 Security Lead](#32-security-lead)
    - [3.3 IT Operations Lead](#33-it-operations-lead)
    - [3.4 Communications Lead](#34-communications-lead)
    - [3.5 Legal/Compliance Officer](#35-legalcompliance-officer)
    - [4. Communication Templates](#4-communication-templates)
    - [4.1 Initial Notification Template](#41-initial-notification-template)
    - [5. Technical Response Procedures](#5-technical-response-procedures)
    - [5.1 Initial Response Checklist](#51-initial-response-checklist)
    - [5.2 Containment Strategies](#52-containment-strategies)
    - [5.3 Eradication Procedures](#53-eradication-procedures)
    - [6. Evidence Collection & Preservation](#6-evidence-collection--preservation)
    - [6.1 Digital Evidence Management](#61-digital-evidence-management)
    - [6.2 Evidence Collection Commands](#62-evidence-collection-commands)
    - [7. Recovery & Business Continuity](#7-recovery--business-continuity)
    - [7.1 Recovery Planning](#71-recovery-planning)
    - [7.2 Business Continuity Activation](#72-business-continuity-activation)
    - [8. Post-Incident Actions](#8-post-incident-actions)
    - [8.1 Lessons Learned](#81-lessons-learned)
    - [8.2 Implementation of Improvements](#82-implementation-of-improvements)
    - [9. Appendices](#9-appendices)
    - [9.1 Contact Information](#91-contact-information)
    - [9.2 Regulatory Notification Requirements](#92-regulatory-notification-requirements)
    - [9.3 Technical Tools & Resources](#93-technical-tools--resources)

* * *

## 1. Executive Summary

This playbook offers a practical, structured approach for the rapid and coordinated response to cybersecurity incidents. It is based on industry best practices and can be easily adapted to the needs of any organization, serving as a guide for all specialized playbooks.

**Objectives:**  
- Minimize business impact and recovery time  
- Preserve evidence for forensic analysis and root cause analysis  
- Ensure compliance with regulatory requirements  
- Effective and targeted communication with all stakeholders  
- Continuous improvement through lessons learned

* * *

## 2. Incident Classification Matrix

### 2.1 Severity Levels

The severity level is defined by the Organization based on the regulatory framework and management requirements. Critical systems are those internally designated based on Business Impact Analysis, DORA criticality, and GDPR criticality. <span style="color: rgb(22, 145, 121);">(Reference to Critical Systems Registry).</span>

**<span style="color: rgb(186, 55, 42);">CRITICAL (P1)</span>:** Critical systems have been breached, confirmed data leak, regulatory notification required  
- Response time: <span style="color: rgb(186, 55, 42);">Immediate (within 10 minutes from detection)</span>  
- Escalation: Notify C-Suite/Management within half an hour. Initial notification of the incident and start of periodic updates via established communication channels.  
- Resources: Full activation of the IR team, activation of support, and IT contracts. <span style="color: rgb(22, 145, 121);">(Reference to Crisis Management and Internal Communication Form).</span>

**<span style="color: rgb(224, 62, 45);">HIGH (P2)</span>:** Significant breach, possible data leak, service disruption affecting customers.  
- Response time: <span style="color: rgb(224, 62, 45);">Within 45 minutes</span>  
- Escalation: Notify senior management within 2 hours  
- Resources: Core IR team and Directors notified for possible escalation.

**<span style="color: rgb(230, 126, 35);">MEDIUM (P3)</span>:** Limited breach, no confirmed data leak  
- Response time: <span style="color: rgb(230, 126, 35);">Within 2 hours</span>  
- Escalation: Notify IT management within 4 hours  
- Resources: Technical team with IR oversight, and the IR team notified for possible escalation.

**<span style="color: rgb(241, 196, 15);">LOW (P4)</span>:** Suspicious activity, possible incident under investigation  
- Response time: <span style="color: rgb(241, 196, 15);">Within 8 hours</span>  
- Escalation: Notify the security team  
- Resources: Security analyst

### 2.2 Incident Categories

For each detected incident, the IR team must immediately categorize it into one of the following categories to follow the appropriate response procedures:

**Malware / Ransomware**  
  Indicators: Ransom messages, mass file encryption, and malware detection by security tools.  
  Immediate actions: Isolate affected systems, preserve evidence, notify IR team, initiate containment, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Malware/Ransomware Playbook)</span>

**Data Leak/Exfiltration**  
  Indicators: Unexplained large data transfers, sending sensitive files outside the Organization, DLP system alerts.  
  Immediate actions: Identify source of leak, isolate related accounts/systems, preserve logs, notify DPO/legal, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Data Leak/Exfiltration Playbook)</span>

**Unauthorized Access**  
  Indicators: Access to systems with stolen credentials, unusual account activity, and SIEM alerts.  
  Immediate actions: Disable/reset credentials, check logs for lateral movement, isolate affected accounts, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Unauthorized Access Playbook)</span>

**Denial of Service (DoS/DDoS)**  
  Indicators: Service unavailability, excessive requests to servers, and monitoring alerts.  
  Immediate actions: Activate DDoS mitigation, notify provider, log attacks, communicate with affected stakeholders, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to DoS/DDoS Playbook)</span>

**Phishing / Social Engineering**  
  Indicators: Reports of suspicious emails, users providing credentials, and detection of malicious links.  
  Immediate actions: Notify affected users, reset credentials, analyze email headers, notify awareness team, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Phishing / Social Engineering Playbook)</span>

**Insider Threat**  
  Indicators: Unusual access or data exfiltration by internal users, reports of suspicious behavior.  
  Immediate actions: Access audit, isolate account, preserve evidence, notify HR/legal, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Insider Threat Playbook)</span>

**Third Party / Supply Chain**  
  Indicators: Notification of compromise from partner, detection of malicious activity via external services, vulnerability feed alerts.  
  Immediate actions: Communicate with third party, isolate affected integrations, assess impact, notify management, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Third Party / Supply Chain Playbook)</span>

**Physical Security Breach**  
  Indicators: Theft or loss of equipment, unauthorized entry to premises, reports of vandalism.  
  Immediate actions: Notify physical security, preserve CCTV/logs, isolate affected systems, activate disaster recovery if required, start relevant playbook <span style="color: rgb(22, 145, 121);">(Reference to Physical Security Breach Playbook)</span>

* * *

## 3. Team Roles & Responsibilities

Effective incident management relies on a clear division of roles and immediate collaboration among Incident Response (IR) team members. Each role has specific responsibilities and actions, while the Incident Commander (IC) ensures overall coordination and decision-making.

The IR team consists of:  
- **Incident Commander (IC):** The team leader, responsible for coordination, decision-making, and communication with management.  
- **Security Lead:** The primary technical lead for analysis, threat assessment, and evidence management.  
- **IT Operations Lead:** Responsible for isolation, recovery, and ensuring business continuity of systems.  
- **Communications Lead:** Manages internal and external communication, ensuring proper information flow to all stakeholders.  
- **Legal/Compliance Officer:** Oversees legal and regulatory aspects, ensuring compliance and proper evidence handling.

Coordination among roles is achieved through regular communication, clear assignment of responsibilities, and documentation of all actions. The Incident Commander is the sole point of decision-making and communication with management, while each lead ensures timely updates and collaboration with other team members. <span style="color: rgb(22, 145, 121);">(Reference to Crisis Management and Internal Communication Form).</span>

### 3.1 Incident Commander (IC)

The Incident Commander (IC) is responsible for the overall coordination of incident management. They lead the IR team from the moment the playbook is activated until full recovery and incident closure.

**Key Responsibilities:**  
- Coordination of all actions and critical decision-making during the incident.  
- Communication with management, senior leadership, and, where required, external bodies (regulatory authorities, partners, customers).  
- Allocation of roles and resources within the IR team, ensuring each member knows their responsibilities.  
- Documentation of incident progression and maintenance of the overall timeline.  
- Final approval for containment, eradication, and recovery, based on technical leads' recommendations.  
- Activation or escalation to external partners (e.g., forensic experts, legal counsel) when required.  
- Ensuring all actions comply with organizational policies and regulatory requirements.

**Immediate actions upon activation:**  
- Receive incident briefing and confirm severity.  
- Activate the IR team and assign roles.  
- Notify management and key stakeholders.  
- Approve initial containment actions.  
- Monitor progress and make decisions for next steps.  
- Ensure documentation of all actions and communications.

<span style="color: rgb(45, 194, 107);">\> **Note:** The IC remains the sole point of decision-making and communication with management throughout the incident, ensuring a unified strategy and avoiding confusion.</span>

### 3.2 Security Lead

The Security Lead is responsible for the technical management of the incident and threat assessment. They act as the primary technical coordinator of the IR team, ensuring proper analysis, documentation, and preservation of evidence.

**Key Responsibilities:**  
- Conduct technical analysis of the incident (root cause analysis, identification of Indicators of Compromise).  
- Assess the nature, scope, and severity of the threat.  
- Coordinate the collection, preservation, and secure storage of evidence (logs, memory dumps, disk images, etc.).  
- Manage and configure security tools (SIEM, EDR, DLP, IDS/IPS) and monitor relevant alerts.  
- Oversight and guidance of forensic analysis, either internally or in collaboration with external experts.  
- Provide technical recommendations to the Incident Commander for containment, eradication, and recovery.  
- Continuously update the team on technical developments and findings.

**Immediate actions upon activation:**  
- Gain access to necessary systems and monitoring tools.  
- Begin evidence collection based on chain of custody procedures.  
- Analyze initial findings and assess the incident's scope.  
- Inform the Incident Commander of critical technical findings and containment proposals.  
- Document all technical actions and findings.

<span style="color: rgb(45, 194, 107);">\> **Note:** The Security Lead ensures that the technical management of the incident is conducted methodically, with integrity, and by organizational policies.</span>

### 3.3 IT Operations Lead

The IT Operations Lead is responsible for managing the technical infrastructure during the incident, ensuring the isolation, recovery, and continuity of critical services.

**Key Responsibilities:**  
- Implement containment measures on affected systems and networks, according to IR team instructions.  
- Assess the incident's impact on IT infrastructure (servers, networks, applications, cloud).  
- Plan and execute recovery actions, including restoration from backup and service restoration.  
- Coordinate business continuity efforts in collaboration with relevant teams.

**Immediate actions upon activation:**  
- Apply predefined containment measures (e.g., network disconnection, account deactivation).  
- Evaluate the availability of critical systems and services.  
- Inform the IR team of technical obstacles or needs for additional resources.  
- Participate in the planning and implementation of the recovery plan.

<span style="color: rgb(45, 194, 107);">\> **Note:** The IT Operations Lead ensures that technical actions are performed securely and minimize business impact.</span>

### 3.4 Communications Lead

The Communications Lead is responsible for managing communication, both internally and externally, during the incident.

**Key Responsibilities:**  
- Coordinate internal communication with all involved parties (management, IT teams, HR, IR).  
- Manage external communication with customers, regulatory authorities, partners, and media, according to organizational policies.  
- Document all communications and create incident reports.  
- Collaborate with legal/compliance for proper wording and approval of messages.

**Immediate actions upon activation:**  
- Inform key stakeholders about the incident and initial actions.  
- Prepare and distribute approved announcements or updates.  
- Record all communications for transparency and compliance.  
- Collaborate with the legal department to avoid legal risks in communication.

<span style="color: rgb(45, 194, 107);">\> **Note:** The Communications Lead ensures that communication is timely, accurate, and consistent with organizational policies.</span>

### 3.5 Legal/Compliance Officer

The Legal/Compliance Officer is responsible for managing the legal and regulatory aspects of the incident.

**Key Responsibilities:**  
- Assess the need for regulatory notifications (e.g., GDPR, DORA) and ensure their timely submission.  
- Evaluate the legal consequences of the incident and provide relevant guidance to the IR team and management.  
- Ensure compliance in the management and preservation of evidence, according to the legal framework.  
- Coordinate with external legal advisors, regulatory authorities, and other bodies, where required.

**Immediate actions upon activation:**  
- Be informed about the incident and assess the need to notify authorities or customers.  
- Provide guidance on managing evidence and personal data.  
- Collaborate with the communications lead for approval of external announcements.  
- Communicate with external legal counsel or regulatory authorities, if required.

<span style="color: rgb(45, 194, 107);">\> **Note:** The Legal/Compliance Officer ensures that all actions comply with the applicable legal and regulatory framework.</span>

* * *

## 4. Communication Templates

### 4.1 Initial Notification Template

```text
SUBJECT: [SEVERITY] Security Incident - [INCIDENT-ID] - [BRIEF DESCRIPTION]

INCIDENT DETAILS:
- Incident ID: [AUTO-GENERATED] - If not available, simply use the date in DDMMYYYY format
- Detection time: [TIMESTAMP]
- Severity level: [P1/P2/P3/P4]
- Affected systems: [LIST] - Does not need to be exhaustive, only highlight the most critical ones. Update with new data in each notification.
- Initial assessment: [BRIEF DESCRIPTION]
- Incident Commander: [NAME/CONTACT]

IMMEDIATE ACTIONS [SUMMARY]:
- [ACTION 1]
- [ACTION 2]
- [ACTION 3]

NEXT STEPS [SUMMARY]:
- [PLANNED ACTION - TIME]
- [PLANNED ACTION - TIME]

Next update: [In minutes]
```

### 4.2 Executive Briefing Template

```text
EXECUTIVE INCIDENT BRIEFING - [INCIDENT-ID]

SITUATION OVERVIEW:
- What happened: [SIMPLE, NON-TECHNICAL DESCRIPTION]
- When detected: [TIMESTAMP]
- Current status: [CONTAINED/INVESTIGATING/RECOVERING]
- Business impact: [QUANTIFIED] - If quantification is not possible, refer to criticality level P1/P2

RESPONSE ACTIONS:
- Immediate containment: [ACTIONS]
- Investigation progress: [KEY FINDINGS]
- Recovery timeline: [ESTIMATE]

LEGAL/REGULATORY:
- Notification required: [YES/NO - TIME]
- Impact on customers: [DESCRIPTION]
- Media/PR: [ASSESSMENT]

RESOURCE NEEDS:
- Additional personnel: [IF NEEDED]
- External support: [VENDORS/CONSULTANTS]

Next update: [In minutes]
```

* * *

This section describes the basic technical steps the IR team must follow from the moment an incident is detected until the threat is wholly eradicated. The process is structured to ensure speed, accuracy, and preservation of evidence.

### 5.1 Initial Response Checklist

During the initial phase, the IR team follows a specific checklist to ensure all critical steps are covered:

- [ ] **Confirm and validate incident:** Verify that the event is a real security incident.
- [ ] **Assign incident ID and severity:** Register a unique identifier and assess the severity level.
- [ ] **Activate IR team:** Inform and mobilize the appropriate team members.
- [ ] **Initiate evidence preservation:** Immediately capture and secure logs, memory dumps, network captures, etc.
- [ ] **Document actions with timestamps:** Record every action with precise timestamps.
- [ ] **Assess immediate containment needs:** Determine if immediate isolation of systems or accounts is required.
- [ ] **Notify stakeholders according to communication matrix:** Inform relevant parties based on the communication plan.
- [ ] **Establish secure communication channels:** Ensure communication occurs through secure means.
- [ ] **Begin impact assessment:** Initial evaluation of business and technical impact.
- [ ] **Coordinate with external resources if needed:** Activate external partners (e.g., forensic experts, vendors).

### 5.2 Containment Strategies

Containment aims to limit the spread of the incident and protect critical systems. It is divided into short-term and long-term actions:

**Short-term containment:**  
- Network isolation of affected systems (e.g., disconnecting from the network).  
- Deactivation of accounts or immediate password changes.  
- Modification of firewall rules to block malicious traffic.  
- DNS blocking of malicious domains.  
- Quarantine or blocking of suspicious emails.

**Long-term containment:**  
- System updates and hardening.  
- Improvement of network segmentation to limit lateral movement.  
- Enhancement of monitoring and alerting.  
- Review of access controls and permissions.  
- Update and configuration of security tools.

### 5.3 Eradication Procedures

Once containment is achieved, the IR team proceeds with the complete eradication of the threat, depending on the type of incident:

**Malware Removal:**  
1. Identify all affected systems (using IOCs).  
2. Apply anti-malware tools to remove malicious software.  
3. Manually remove persistent threats (e.g., rootkits, backdoors).  
4. Clean registry and file system remnants.  
5. Confirm complete removal through repeated checks.

**Account Compromise:**  
1. Mandatory password change for affected accounts.  
2. Check and revoke suspicious tokens/sessions.  
3. Audit permissions and groups to identify unauthorized changes.  
4. Enable additional authentication (e.g., MFA).  
5. Enhanced monitoring for new unauthorized access.

**System Compromise:**  
1. Restore systems from backups.  
2. Apply all necessary patches and updates.  
3. Harden security settings (system hardening).  
4. Restore data only from verified backups.  
5. Security testing and validation before restoring to production.

<span style="color: rgb(45, 194, 107);">\> **Note:** All actions must be thoroughly documented, and chain of custody procedures for evidence must be followed.</span>

* * *

## 6. Evidence Collection & Preservation

The collection and preservation of evidence is a critical process for forensic analysis, impact assessment, and incident documentation. Proper evidence management ensures its legal validity and integrity.

### 6.1 Digital Evidence Management

**Chain of Custody:**  
The chain of custody process ensures the integrity and reliability of evidence:

- **Collection documentation:** Detailed recording of who, when, and how each piece of evidence was collected.  
- **Detailed management logs:** Recording of every access, transfer, or processing of evidence.  
- **Cryptographic hashing:** Use of algorithms (e.g., SHA-256) to confirm file integrity.  
- **Secure storage:** Storage in a controlled environment with restricted access and backup.  
- **Authorized access:** Access only by authorized personnel with logging of every action.

**Types of Evidence:**  
The IR team collects different types of evidence depending on the nature of the incident:

- **System logs:** Operating system, application, and security logs.  
- **Network traffic captures:** Recording of network traffic and communications.  
- **Memory dumps:** Snapshots of system memory for analysis of active processes.  
- **Disk images:** Full copies of hard drives for forensic analysis.  
- **Email headers & content:** Detailed email communication data.  
- **Database transaction logs:** Recording of transactions and changes in databases.  
- **Physical evidence:** Equipment, storage devices, or documents (if any).

### 6.2 Evidence Collection Commands

The IR team uses specific commands to collect evidence from different environments. Some basic examples are listed below; each playbook contains a particular set of commands and actions that need to be executed.

**Windows Systems:**  

```bash
# Memory dump
DumpIt.exe /output C:\evidence\memory.dmp

# System information
systeminfo > C:\evidence\systeminfo.txt

# Network connections
netstat -ano > C:\evidence
etstat.txt

# Running processes
tasklist /v > C:\evidence\processes.txt

# Event logs export
wevtutil epl System C:\evidence\system.evtx
wevtutil epl Security C:\evidence\security.evtx
wevtutil epl Application C:\evidencepplication.evtx
```

**Linux Systems:**

```bash
# Memory dump
dd if=/dev/mem of=/tmp/evidence/memory.dump

# System information
uname -a > /tmp/evidence/system_info.txt
cat /proc/version >> /tmp/evidence/system_info.txt

# Network connections
netstat -tulpn > /tmp/evidence/network_connections.txt

# Running processes
ps aux > /tmp/evidence/processes.txt

# Log files collection
cp -r /var/log/* /tmp/evidence/logs/
```

**Network & Infrastructure:**

```bash
# Packet capture
tcpdump -i eth0 -w /tmp/evidence/network_capture.pcap

# Continuous capture with rotation
tcpdump -i eth0 -w /tmp/evidence/capture_%Y%m%d_%H%M%S.pcap -G 3600

# DNS query logs
dig @dns_server example.com > /tmp/evidence/dns_queries.txt
```

Additional Commands:

```text
Firewall logs Can Be Exported from the management console or collected from log files.
Proxy logs: Export from the proxy server or web security gateway.
SIEM data: Export relevant events and alerts from the SIEM platform.
```

<span style="color: rgb(45, 194, 107);">\> **Note**: All commands must be executed with appropriate permissions and documented with timestamps. Evidence must be stored in a secure location with hash values calculated to confirm integrity.</span>

* * *

## 7. Recovery & Business Continuity <span style="color: rgb(22, 145, 121);">(Reference to BCP)</span>

The recovery and business continuity phase ensures the safe and controlled return of services to regular operation, minimizing business impact and preventing recurring incidents.

### 7.1 Recovery Planning

Recovery planning prioritizes systems and services, ensuring that the most critical ones for the Organization's operation are restored first.

**Recovery Priorities:**  

1.  **Customer-facing services:** Applications and services used by customers.
2.  **Internal operations:** Support systems for staff and daily operations.
3.  **Administrative systems:** Management, reporting, HR systems, etc.

**Recovery Verification:**  
After each system is restored, specific verification steps are followed:  
- **Functional testing:** Checking basic functionality and availability.  
- **Security testing & vulnerability scanning:** Checking for any remaining vulnerabilities or entry points.  
- **Performance monitoring:** Monitoring performance to detect anomalies.  
- **User acceptance testing:** Confirmation by end-users that the system functions as expected.  
- **Documentation of changes:** Recording all changes, actions, and findings for future reference.

### 7.2 Business Continuity Activation

In cases where recovery is delayed or the availability of critical services cannot be ensured, business continuity plans (BCPs) are activated.

**Activation Triggers:**  
- Critical service unavailability for more than 2 hours.  
- Severe problems in the data center or infrastructure.  
- Extensive breach affecting multiple systems or services.  
- Assessment that recovery will take more than 4 hours.

**Business Continuity Procedures:**  
1. **Activate alternative sites:** Transfer operations to disaster recovery or backup sites.  
2. **Manual workarounds:** Implement manual procedures for critical operations.  
3. **Redirect customer traffic:** Redirect customers to available services or alternative solutions.  
4. **Inform stakeholders:** Continuous updates to management, customers, and partners on the situation and next steps.  
5. **Continuous service monitoring:** Intensive monitoring of service status and alternative solutions.

<span style="color: rgb(45, 194, 107);">\> **Note:** All recovery and business continuity actions must be thoroughly documented and communicated to relevant stakeholders.</span>

* * *

## 8. Post-Incident Actions

The review and improvement phase ensures that every incident is utilized as a learning opportunity and strengthens the Organization's resilience. Systematic analysis and implementation of corrective actions reduce the likelihood of recurrence and improve overall response.

### 8.1 Lessons Learned

After the incident is closed, a lessons learned meeting is held with the participation of all involved teams. The meeting agenda includes:

1.  **Timeline review:** Presentation and analysis of the chronological sequence of events.
2.  **Response effectiveness evaluation:** Discussion of what worked well and what did not in incident management.
3.  **Communication evaluation:** Review of internal and external communication.
4.  **Identification of technical gaps:** Recording of technical weaknesses or deficiencies identified.
5.  **Improvement proposals:** Collection of ideas and suggestions for future enhancement.
6.  **Assessment of training needs:** Evaluation of whether additional training or awareness is required.
7.  **Assignment of action items:** Definition of responsible parties and timelines for corrective actions.

**Required documentation:**  

1. Complete and documented incident timeline.
2. Root cause analysis with analysis of causes.
3. Impact assessment (financial, operational, reputational).
4. Detailed record of actions taken.
5. List and description of evidence collected.
6. Record of regulatory notifications made.
7. Consolidated improvement proposals and lessons learned.

### 8.2 Implementation of Improvements

Improvements resulting from the lessons learned process are implemented at three levels:

**Technical improvements:**  

1. Strengthening existing controls and security mechanisms.
2. Improving monitoring and detection (e.g., new rules, alerts).
3. Changes in system architecture to reduce risk.
4. Hardening of critical systems.
5. Upgrading or replacing security tools.

**Procedural improvements:**  

1. Updating and revising the playbook and IR procedures.
2. Strengthening and updating training and awareness programs.
3. Improving communication between teams and stakeholders.
4. Updating the escalation matrix and communication plans.
5. Strengthening collaboration and relationships with vendors and third parties.

**Organizational improvements:**  

1. Changes in staffing and role allocation.
2. Skill development and professional growth programs.
3. Budget review to cover new needs.
4. Updating security policies and procedures.
5. Improving governance and overall security governance.

<span style="color: rgb(45, 194, 107);">\> **Note:** All improvements must be documented, their implementation monitored, and reviewed regularly.</span>

* * *

## 9. Appendices

### 9.1 Contact Information

**Internal Contacts (Primary and Backup):**  
- Incident Commander: [NAME] - [PHONE] - [EMAIL]  
- Security Team Lead: [NAME] - [PHONE] - [EMAIL]  
- IT Operations Manager: [NAME] - [PHONE] - [EMAIL]  
- Legal Counsel: [NAME] - [PHONE] - [EMAIL]  
- Communications Lead: [NAME] - [PHONE] - [EMAIL]  
- Executive Leadership: [NAME] - [PHONE] - [EMAIL]

**External Contacts:**  
- Cybercrime Division: [DETAILS]  
- Regulatory Authorities: [DETAILS]  
- Cyber Insurance: [DETAILS]  
- External Legal Counsel: [DETAILS]  
- Forensic Investigators: [DETAILS]  
- Public Relations: [DETAILS]

### 9.2 Regulatory Notification Requirements

**GDPR (EU):**  
- Notification to authority: within 72 hours  
- Notification to data subjects: without undue delay  
- Documentation: detailed incident record

**DORA - NIS 2 - EETT:**  
- Significant ICT incidents: immediate notification  
- Significant threats: within 4 hours  
- Follow-up reports: as required

* * *

