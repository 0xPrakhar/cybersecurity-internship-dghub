Week 9 Assignment Report: SOC Introduction & Setup — Snort IDS Lab

DG Interns Hub Cybersecurity Internship Program

Intern Name: Prakhar Gupta

Submission Date: 5/11/2026

Module: Security Operations Center (SOC)

Environment / Tools: Kali Linux (VMware Workstation), Snort IDS (Snort++ 3.12.2.0)

Overview

This repository contains the documentation, custom detection rules, and assignment artifacts for Week 9 of the DG Interns Hub Cybersecurity Internship. The lab shifts focus from offensive security testing (VAPT) to defensive monitoring, introducing fundamental Security Operations Center (SOC) workflows and practical deployment of the Snort Intrusion Detection System (IDS).

Project Structure

├── README.md               # Project documentation and guide
├── Week_9.pdf              # Complete formal assignment report PDF
├── rules/
│   └── local.rules         # Custom Snort detection rules (ICMP & HTTP)
└── screenshots/            # Lab evidence screenshots (Host, Install, Validation, Alerts)


Key Objectives Covered

SOC Fundamentals: Researching and documenting core SOC operations, analyst tiers (L1 Triage, L2 Investigation, L3 Threat Hunting), and the distinct roles of SIEM, IDS, and IPS.

Environment & Host Setup: Confirming host identity (hostnamectl) and network interfaces (ip a) inside a Kali Linux virtual machine (eth0 at 192.168.150.128).

Snort IDS Installation: Installing and verifying Snort++ 3.12.2.0 and validating configurations against /etc/snort/snort.lua.

Detection Engineering: Authoring, validating, and negative-testing two custom detection rules in /etc/snort/rules/local.rules.

Live Traffic Testing: Capturing real-time console alerts with raw packet dumps for network reconnaissance (ping sweeps) and web traffic.

Custom Snort Rules (local.rules)

The custom rules implemented for this lab are stored in /etc/snort/rules/local.rules:

# Rule 1: Flag ICMP Echo Request (ping) traffic - basic reconnaissance detection
alert icmp any any -> $HOME_NET any (msg:"SOC-ALERT ICMP Ping Detected"; itype:8; sid:1000001; rev:1;)

# Rule 2: Flag TCP connections on port 80 - basic plaintext HTTP visibility
alert tcp any any -> $HOME_NET 80 (msg:"SOC-ALERT Inbound HTTP Connection"; sid:1000002; rev:1;)


Running Validation and Live Capture

1. Configuration Syntax Validation

Verify the base configuration and custom rules without starting a live capture:

sudo snort -c /etc/snort/snort.lua -R /etc/snort/rules/local.rules -T


2. Start Live Snort IDS Capture

Bind Snort to the primary network interface (eth0) in console alert mode:

sudo snort -c /etc/snort/snort.lua -R /etc/snort/rules/local.rules -i eth0


Production Recommendations

To transition this lab setup into a production-grade enterprise SOC:

Scope HOME_NET: Restrict HOME_NET explicitly to protected subnets rather than any to prevent bidirectional matching.

Log Forwarding: Run Snort as a background systemd service exporting logs in JSON or syslog format to a central SIEM.

Rule Tuning: Layer the Snort Community rule set, eliminate noisy signatures, and carefully promote high-confidence rules from IDS (alert) to IPS (drop) mode.

Author

Prakhar Gupta

Cybersecurity Intern | DG Interns Hub
