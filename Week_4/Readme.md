# 🛡️ DG Interns Hub - Cybersecurity Internship
## Week 4: Basic Network Setup & Initial Security Testing

This repository contains the documentation, scan outputs, and evidence files for **Week 4** of the Cybersecurity Internship Program at DG Interns Hub.

---

### 📋 Assignment Overview
* **Objective:** Understand basic network setup and perform initial security testing in an isolated lab environment.
* **Intern:** Prakhar Gupta[cite: 1]
* **Role:** Cybersecurity Intern
* **Submission Date:** 30/Sept/2026

---

### 🛠️ Lab Environment & Topology
* **Hypervisor:** VMware Workstation Pro[cite: 49]
* **Network Mode:** VMware NAT Network (`192.168.94.0/24`, Gateway: `192.168.94.2`)[cite: 49, 50]
* **Attacker Machine:** Kali Linux (`192.168.94.137`)[cite: 49]
* **Target Machine:** Metasploitable 2 - Ubuntu Linux (`192.168.94.135`)[cite: 49]

---

### 🧩 Tasks Performed & Workflow

#### 1. Task 1: Setup Basic Network (Lab)
* Established an isolated two-node multi-machine virtual lab using VMware.
* Ensured secure communication across the virtual switch without exposing traffic to external public networks[cite: 50].

#### 2. Task 2: Install & Configure Services
* Verified that the **Apache HTTP Server (v2.2.8)** was actively running on target port 80[cite: 49, 52].
* Tested service accessibility from the Kali attacker node using `curl`, confirming default HTML responses and bundled training web applications[cite: 51].

#### 3. Task 3: Network Scanning (Nmap)
* Executed service and version detection scans (`nmap -sV`) against the target[cite: 52, 53].
* Identified **24 open TCP ports**, mapping out exposed legacy services including FTP (`vsftpd 2.3.4`), SSH (`OpenSSH 4.7p1`), Telnet, and MySQL[cite: 52, 53].

#### 4. Task 4: Traffic Analysis (Wireshark)
* Captured live interface traffic on the Kali host during reconnaissance and testing[cite: 54, 55].
* Filtered and analyzed core protocol packets:
  * **HTTP:** Inspected `GET` requests and `200 OK` server replies[cite: 54].
  * **DNS:** Monitored domain resolution queries routed through the gateway[cite: 54].
  * **ICMP:** Verified host liveness via ping echo request/reply sequences[cite: 55].

#### 5. Task 5: Mini Project Output & Documentation
* Compiled findings into a structured PDF report and presentation deck outlining the full end-to-end testing workflow[cite: 57].

---

### 🚀 Key Learnings & Takeaways
* **Tool Synergy:** Demonstrated how reconnaissance tools complement each other—`curl` verifies service uptime, `Nmap` proves discoverability, and `Wireshark` exposes underlying wire mechanics[cite: 57].
* **Attack Surface Reduction:** Uncovered the security risks associated with legacy training environments (like Metasploitable) which intentionally expose unnecessary services, reinforcing the critical need for strict port minimization and patch management[cite: 57].

---
*© 2026 Prakhar Gupta. All rights reserved for internship assessment use.*
