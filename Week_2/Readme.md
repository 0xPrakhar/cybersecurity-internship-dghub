# DG Interns Hub — Cybersecurity Internship

## Week 2 Assignment Report

This repository contains my **Week 2 Cybersecurity Internship Assignment** completed as part of the internship at **DG Interns Hub**.

The assignment focuses on **Advanced Networking, Network Analysis, and Security Concepts**, combining theoretical understanding with practical exercises in controlled and authorized environments.

## Topics Covered

* Network Ports and Services
* Networking Devices

  * Router
  * Switch
  * Firewall
* Network Security Basics

  * Man-in-the-Middle (MITM)
  * Denial-of-Service (DoS)
  * Packet Sniffing
* Network Traffic Analysis using Wireshark
* Network Scanning using Nmap
* LAN Configuration using Cisco Packet Tracer
* Safe MITM Concept Simulation

## Tools Used

| Tool                    | Purpose                                       |
| ----------------------- | --------------------------------------------- |
| **Wireshark**           | Network packet capture and traffic analysis   |
| **Nmap**                | Network scanning and service detection        |
| **Cisco Packet Tracer** | Network topology design and LAN configuration |

## Setup

### Prerequisites

Install the following tools before performing the practical exercises:

* **Wireshark** — for packet capture and traffic analysis
* **Nmap** — for authorized network scanning
* **Cisco Packet Tracer** — for network topology and LAN simulation
* A terminal or command prompt for running Nmap commands

### Installation

Download and install each tool from its official source. After installation, verify that the tools are working correctly.

For Nmap, open a terminal or Command Prompt and run:

```bash
nmap --version
```

For Wireshark, launch the application and verify that the available network interfaces are displayed.

For Cisco Packet Tracer, launch the application and create a new network simulation project.

## Usage

### 1. Wireshark — Packet Analysis

1. Open Wireshark.
2. Select the active network interface.
3. Start packet capture.
4. Generate normal network traffic, such as visiting a website.
5. Stop the capture.
6. Analyze DNS, HTTP/HTTPS, and source/destination IP information.

Example filters that can be used for analysis:

```text
dns
http
tcp
udp
```

> Only capture and analyze traffic on networks and devices that you own or have explicit permission to monitor.

### 2. Nmap — Network Scanning

Nmap was used against the authorized educational target:

```text
scanme.nmap.org
```

Basic scan:

```bash
nmap scanme.nmap.org
```

Service and version detection:

```bash
nmap -sV scanme.nmap.org
```

The results can be used to identify available ports, services, and service-version information.

> Do not scan systems or networks without authorization. The commands in this report are intended for authorized security testing and learning purposes.

### 3. Cisco Packet Tracer — LAN Setup

Create the following topology:

```text
PC1 ───┐
       │
     Switch
       │
PC2 ───┘
```

Configure the devices with:

```text
PC1: 192.168.1.10
PC2: 192.168.1.11
```

After configuration, open the command prompt on PC1 and test connectivity:

```bash
ping 192.168.1.11
```

A successful reply confirms that the two PCs can communicate through the switch.

### 4. MITM Concept — Safe Simulation

The MITM activity was performed as a **conceptual and controlled simulation** to understand how an attacker could position themselves between communicating devices.

Example topology:

```text
PC1 (Victim) ── Switch ── Router
                    │
              PC2 (Attacker)
```

The simulation was limited to understanding the concept, network positioning, and associated security risks. No unauthorized interception or credential capture was performed.

## Practical Work

The practical exercises included:

1. Identifying common ports, protocols, and services.
2. Understanding the role of routers, switches, and firewalls.
3. Analyzing captured network traffic using Wireshark.
4. Performing an authorized Nmap scan on `scanme.nmap.org`.
5. Creating a basic LAN with two PCs and a switch.
6. Testing connectivity using the `ping` command.
7. Studying the MITM attack concept through a safe and controlled simulation.

## Safety & Authorization

All security-related activities were performed for **educational purposes in controlled and authorized environments**.

Network scanning was conducted only against the authorized Nmap testing target, while the MITM activity was limited to conceptual/safe simulation.

Do not use the techniques demonstrated in this project against systems, networks, or users without explicit authorization.

## Learning Outcomes

This assignment strengthened my understanding of:

* Network communication and common services
* TCP and UDP-based communication
* Network devices and their functions
* Packet capture and traffic analysis
* Network scanning and service identification
* LAN configuration and connectivity testing
* Basic network security threats
* Responsible and authorized security testing

## Internship Details

**Intern:** Prakhar Gupta
**Organization:** DG Interns Hub
**Internship:** Cybersecurity Internship
**Assignment:** Week 2
**Focus:** Advanced Networking, Analysis & Security Concepts
**Submission Date:** 14 September 2026
