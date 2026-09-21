# 🔐 Week 3 – Network Security Assessment

## 📌 Overview

This repository contains my **Week 3 Cybersecurity Internship practical work**, focused on network security assessment, network traffic analysis, vulnerability identification, and basic security hardening.

The practical work was performed in an **authorized lab environment** to understand how security professionals discover systems, enumerate services, analyze network traffic, identify potential security issues, and verify security improvements.

---

## 🎯 Objectives

The main objectives of this week's practical work were:

* Perform network discovery using Nmap
* Identify open ports and running services
* Perform service and basic OS enumeration
* Understand different Nmap scanning techniques
* Capture and analyze network traffic using Wireshark
* Understand TCP, UDP, DNS, ARP, and ICMP traffic
* Correlate Nmap scan activity with Wireshark packets
* Identify potential security findings based on observed evidence
* Apply basic security hardening measures
* Verify security improvements using before/after scans
* Document observations and security recommendations

---

## 🧪 Lab Environment

The practical activities were performed in an authorized lab environment.

### Environment

* **Virtualization:** [VirtualBox / VMware]
* **Analyst Machine:** [Kali Linux / Your OS]
* **Target Machine:** [Ubuntu / Windows / Other]
* **Network Type:** [Host-Only / NAT / Internal Network]
* **Nmap Version:** [Version]
* **Wireshark Version:** [Version]

> ⚠️ All scanning and testing activities were performed only against systems within the authorized lab environment.

---

## 🛠️ Tools Used

| Tool                | Purpose                                        |
| ------------------- | ---------------------------------------------- |
| Nmap                | Network discovery and port/service enumeration |
| Wireshark           | Network traffic capture and packet analysis    |
| VirtualBox / VMware | Virtual lab environment                        |
| diagrams.net        | Network architecture diagram                   |
| GitHub              | Documentation and version control              |

---

# 🔎 Tasks Completed

## Task 7 – Network Discovery & Basic Nmap Scanning

Performed network discovery to identify active hosts within the authorized lab network.

Activities included:

* Identifying IP addresses
* Identifying subnet/network information
* Performing host discovery
* Performing basic port scanning
* Recording discovered ports and services

### Commands Used

```bash
nmap -sn <lab-network>
```

```bash
nmap <target-ip>
```

The actual scan results and screenshots are available in:

```text
01-Nmap/
```

---

## Task 8 – Advanced Nmap Scanning

Performed additional Nmap scans to understand services, operating systems, TCP scanning, and UDP exposure.

### Techniques Used

```bash
nmap -sV <target-ip>
```

```bash
nmap -O <target-ip>
```

```bash
nmap -sS <target-ip>
```

```bash
nmap -sU --top-ports 20 <target-ip>
```

Where appropriate and authorized:

```bash
nmap --script vuln <target-ip>
```

The results were analyzed to identify:

* Open ports
* Protocols
* Running services
* Service versions
* Potential exposure
* Security observations

---

# 🦈 Task 9 – Wireshark Traffic Analysis

Wireshark was used to capture and analyze network traffic generated within the authorized lab environment.

The following protocols and traffic types were investigated:

* DNS
* TCP
* UDP
* ICMP
* ARP
* HTTP

### Example Wireshark Filters

```text
dns
```

```text
tcp
```

```text
udp
```

```text
icmp
```

```text
arp
```

```text
tcp.flags.syn == 1
```

```text
tcp.flags.reset == 1
```

```text
dns.flags.response == 0
```

The captured PCAP files and screenshots are stored under:

```text
02-Wireshark/
```

---

# 🔗 Task 10 – Nmap + Wireshark Correlation

A TCP SYN scan was performed while Wireshark was capturing traffic.

```bash
nmap -sS <target-ip>
```

The resulting packets were analyzed to understand how Nmap scanning activity appears at the packet level.

The investigation focused on:

* SYN packets
* SYN/ACK responses
* RST responses
* Source and destination IP addresses
* Destination ports
* TCP flags
* Connection attempts

### General Observation

For an accessible open TCP port, the scan can result in a sequence involving:

```text
SYN → SYN/ACK
```

For a closed TCP port:

```text
SYN → RST
```

The exact observations and packet numbers are documented using the actual lab capture.

---

# 🔍 Task 11 – Advanced Traffic Investigation

Network traffic was investigated to identify interesting communication patterns within the authorized lab environment.

The analysis included:

* Frequently communicating hosts
* Source and destination systems
* DNS queries and responses
* TCP connection attempts
* SYN/SYN-ACK/RST behavior
* Unusual or unexpected ports
* Repeated connection attempts
* Unexpected protocols or systems

Potentially interesting traffic was treated as an observation requiring further investigation rather than automatically being classified as malicious.

---

# ⚠️ Task 12 – Vulnerability Assessment

Security findings were identified based on evidence collected during the Nmap and Wireshark analysis.

Findings were evaluated based on:

* Security exposure
* Likelihood of misuse
* Potential impact
* Necessity of the exposed service
* Configuration and network exposure

### Findings

| Finding     | Evidence   | Risk   | Potential Impact | Recommendation   |
| ----------- | ---------- | ------ | ---------------- | ---------------- |
| [Finding 1] | [Evidence] | [Risk] | [Impact]         | [Recommendation] |
| [Finding 2] | [Evidence] | [Risk] | [Impact]         | [Recommendation] |
| [Finding 3] | [Evidence] | [Risk] | [Impact]         | [Recommendation] |
| [Finding 4] | [Evidence] | [Risk] | [Impact]         | [Recommendation] |
| [Finding 5] | [Evidence] | [Risk] | [Impact]         | [Recommendation] |

> Findings in the final report are based on actual observations from the authorized lab environment.

---

# 🛡️ Task 13 – Security Hardening

Basic security improvements were implemented based on the identified findings.

The hardening process followed:

```text
Initial Scan
     ↓
Identify Security Issue
     ↓
Apply Security Improvement
     ↓
Perform New Scan
     ↓
Compare Before vs After
```

### Hardening Results

| Security Issue | Before         | Action Taken | After         | Improvement   |
| -------------- | -------------- | ------------ | ------------- | ------------- |
| [Issue 1]      | [Before state] | [Action]     | [After state] | [Improvement] |
| [Issue 2]      | [Before state] | [Action]     | [After state] | [Improvement] |
| [Issue 3]      | [Before state] | [Action]     | [After state] | [Improvement] |

Before and after evidence is available in:

```text
04-Hardening/
```

---

# 📊 Key Learnings

This practical helped me understand how different cybersecurity tools work together during a network security assessment.

### Key takeaways:

* Network discovery is an important first step in understanding an environment.
* Open ports represent network-accessible services and should be reviewed carefully.
* Service enumeration provides additional information about exposed applications.
* Wireshark allows network activity to be investigated at the packet level.
* Nmap scan behavior can be observed directly through TCP packets in Wireshark.
* Security findings should be supported by evidence rather than assumptions.
* Hardening should be followed by verification to confirm that the security posture improved.
* Cybersecurity requires understanding the meaning behind tool output rather than simply running commands.

---

# 💡 Security Recommendations

Based on the practical assessment, the following general recommendations are suggested:

1. Disable unnecessary services and close unnecessary ports.
2. Restrict network services to trusted hosts or networks where possible.
3. Keep operating systems and exposed services updated.
4. Use firewall rules to reduce unnecessary network exposure.
5. Regularly monitor and analyze network traffic for unexpected behavior.
6. Perform periodic vulnerability and configuration assessments.
7. Follow the principle of least privilege for network services and users.

---

# 📁 Repository Structure

```text
Week-3-Cybersecurity/
│
├── 01-Nmap/
│   ├── Scans/
│   └── Screenshots/
│
├── 02-Wireshark/
│   ├── PCAP/
│   └── Screenshots/
│
├── 03-Vulnerability-Assessment/
│
├── 04-Hardening/
│   ├── Before/
│   └── After/
│
├── Network-Diagram/
│
├── Week-3-Report.pdf
├── Week-3-Presentation.pptx
└── README.md
```

---

# 📄 Deliverables

The repository contains:

* Nmap scan results
* Nmap screenshots
* Wireshark PCAP files
* Wireshark analysis screenshots
* Vulnerability assessment
* Hardening evidence
* Network architecture diagram
* Week 3 report
* Week 3 presentation
* This README

---

# ⚖️ Ethical & Legal Notice

All scanning, traffic capture, enumeration, and security testing activities documented in this repository were intended for an **authorized lab environment**.

Nmap and other security tools should only be used against systems and networks where explicit authorization has been provided.

---

# 🚀 Conclusion

Week 3 provided practical exposure to the workflow of a basic network security assessment:

```text
Discover
   ↓
Enumerate
   ↓
Analyze
   ↓
Assess
   ↓
Harden
   ↓
Verify
```

The practical work strengthened my understanding of network discovery, service enumeration, packet analysis, security assessment, and basic network hardening.

This experience also reinforced the importance of combining automated security tools with manual analysis and evidence-based decision making.
