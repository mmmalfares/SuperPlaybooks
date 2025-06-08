[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
# SuperPlaybooks
A curated list of automation and security playbooks for SOC, SOAR, and incident response teams.

## Real Cybersecurity Playbooks

### 1. Cortex XSOAR Incident Response Playbook: Phishing Email Investigation

**Purpose:** Automate investigation and response to a reported phishing email.

**Steps:**

1. **Alert Ingestion**  
   - Automatically ingest phishing email alert from email gateway or SIEM.

2. **Email Analysis**  
   - Extract sender IP, URLs, attachments, and subject.  
   - Run sender IP and URLs against threat intelligence feeds (VirusTotal, PhishTank).  
   - Scan attachments with sandbox analysis tools.

3. **User Validation**  
   - Check if recipient user has reported the email or interacted with it.  
   - Query mailbox for similar emails.

4. **Incident Creation & Triage**  
   - Create incident ticket in XSOAR and assign severity based on threat intel results.  
   - Notify SOC analyst via Slack or email.

5. **Automated Response**  
   - Quarantine email from user mailbox using email platform API.  
   - Block sender IP and URLs in firewall and web proxy.

6. **Manual Review & Closure**  
   - Analyst reviews the incident and adds notes.  
   - Close incident after remediation confirmed.

---

### 2. Microsoft Sentinel Threat Hunting Playbook: Detect Lateral Movement

**Purpose:** Proactively detect lateral movement in the network using Azure AD and Windows event logs.

**Steps:**

1. **Scheduled Query Execution**  
   - Run Kusto Query Language (KQL) query to detect unusual authentication events, such as logins from unusual locations or times.

2. **Alert Enrichment**  
   - Enrich detected events with user risk scores from Azure AD Identity Protection.  
   - Correlate with other suspicious activities like multiple failed login attempts.

3. **Incident Creation**  
   - Automatically create an incident in Sentinel for high-risk findings.  
   - Assign to SOC analyst team.

4. **Automated Remediation**  
   - Trigger Azure Logic Apps workflow to disable compromised accounts.  
   - Notify the identity owner and IT helpdesk.

5. **Investigation & Reporting**  
   - Provide analysts with detailed timeline and related events.  
   - Generate report summarizing findings and actions taken.

---

### 3. LogRhythm Malware Containment Playbook

**Purpose:** Detect, analyze, and contain malware infections using LogRhythm SIEM.

**Steps:**

1. **Alert Correlation**  
   - Correlate endpoint protection alerts with network traffic anomalies and DNS queries.

2. **Threat Intelligence Lookup**  
   - Enrich suspicious IPs, domains, and file hashes with threat intelligence platforms like VirusTotal or internal threat feeds.

3. **Ticketing & Notification**  
   - Automatically open a ticket in ITSM system (e.g., ServiceNow) with malware details.  
   - Notify SOC and IT Ops teams.

4. **Containment Actions**  
   - Block malicious IPs and domains on firewalls and proxies.  
   - Quarantine infected endpoints via EDR integration.

5. **Cleanup & Recovery**  
   - Run endpoint scans and initiate malware removal tools.  
   - Monitor endpoint for signs of reinfection.

6. **Post-Incident Review**  
   - Document incident timeline, impact, and remediation steps.  
   - Share lessons learned with security teams.

---

