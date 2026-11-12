# DG Interns Hub — Cybersecurity Internship Program
## Week 10 Assignment Report: SOC — Wazuh SIEM Setup & Alert Monitoring

This repository documents the work completed for Week 10 of the DG Interns Hub Cybersecurity Internship. Building upon the Intrusion Detection System (Snort) deployed in Week 9, this week focuses on setting up a centralized **Security Information and Event Management (SIEM)** platform using **Wazuh** for comprehensive endpoint logging, real-time alert monitoring, and incident investigation.

---

### 👨‍💻 Author & Metadata
* **Prepared By:** Prakhar Gupta[cite: 26]
* **Role:** Cybersecurity Intern[cite: 26]
* **Submission Date:** 12/11/2026[cite: 26]
* **Module:** Security Operations Center (SOC) — SIEM & XDR[cite: 27, 30]

---

### 📁 Project Structure & Table of Contents
1. **Introduction:** Transitioning from network intrusion detection (Snort) to centralized log management and SIEM platforms (Wazuh)[cite: 28].
2. **Objective & Scope:** Lab goals, isolated hypervisor environment, and tool versions[cite: 29].
3. **Wazuh Overview (Task 1):** Architecture, core components (Manager, Agent, Indexer, Dashboard), and SIEM vs. IDS comparisons[cite: 30, 31].
4. **Wazuh Setup (Task 2):** VirtualBox OVA deployment, service initialization, and web UI configuration[cite: 32, 33, 34].
5. **Wazuh Agent Deployment (Task 3):** Installing, configuring, and connecting the Kali Linux endpoint agent[cite: 35].
6. **Generating Security Events (Task 4):** Simulating authentication failures, successful logins, file modifications, and network pings[cite: 36, 37].
7. **Alert Analysis — 10 Alerts (Task 5):** Detailed breakdown and analysis of 10 security events, highlighting high-severity brute-force attempts[cite: 38, 39, 40].
8. **Snort + Wazuh Integration (Task 6):** Architectural approach for feeding Snort alert logs into Wazuh for unified monitoring[cite: 41, 42].
9. **SOC Incident Investigation (Task 7):** Full incident response lifecycle (Detection, Analysis, Severity Assessment, Containment, Recovery, and Lessons Learned) for an SSH brute-force attack[cite: 42, 43].
10. **SOC Analyst Dashboard Summary (Task 8):** Final metric summary and dashboard overview[cite: 43, 44, 45].
11. **Conclusion & References:** Key takeaways on threat storytelling, false-positive tuning, and official documentation links[cite: 45, 46].

---

### 🛠️ Environment & Tools Used
* **Hypervisor:** Oracle VirtualBox[cite: 29]
* **SIEM / XDR Platform:** Wazuh 4.x (Virtual Appliance running Manager, Indexer, and Dashboard)[cite: 29, 30]
* **Test Endpoint:** Kali Linux (running Wazuh Agent)[cite: 29, 35]
* **Network Security Sensor:** Ubuntu Server with Snort 2.9.7 (carried over from Week 9)[cite: 29]

---

### 🚀 Key Tasks Completed
* **Task 1:** Researched and documented Wazuh architecture and SIEM vs. IDS operational differences[cite: 27, 30, 31].
* **Task 2:** Provisioned and configured the Wazuh OVA appliance inside VirtualBox[cite: 27, 32, 33, 34].
* **Task 3:** Deployed and verified the Wazuh agent on the Kali Linux virtual machine[cite: 27, 35].
* **Task 4:** Generated safe security test events (failed logins, file touching/modifying, service restarts)[cite: 27, 36, 37].
* **Task 5:** Analyzed 10 distinct Wazuh alerts and performed deep-dive investigation on SSH brute-force patterns[cite: 27, 38, 39, 40].
* **Task 6:** Designed and documented the Snort-to-Wazuh log forwarding integration architecture[cite: 27, 41, 42].
* **Task 7:** Executed a complete SOC incident investigation workflow for a high-severity alert[cite: 27, 42, 43].
* **Task 8:** Compiled the final SOC analyst dashboard summary and metrics report[cite: 27, 43, 44, 45].

---

### 💡 Core Learnings
* **Centralized Visibility:** Understood how a SIEM correlates disparate endpoint logs into actionable intelligence, reducing detection time from hours to seconds[cite: 28, 43].
* **Detection Engineering:** Gained hands-on experience differentiating between network-layer monitoring (Snort) and host-layer introspection (Wazuh)[cite: 31].
* **Incident Response:** Practiced the full investigative lifecycle from alert triage to containment, remediation, and post-incident documentation[cite: 42, 43, 45].
