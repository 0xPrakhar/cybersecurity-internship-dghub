```markdown
# Week 7: VAPT – Web Application Testing with Burp Suite

This repository contains the complete documentation, technical VAPT assessment report, presentation slides, and lab notes for the **Week 7 Practical Assessment** completed as part of the Cybersecurity Internship Program at **DG Interns Hub**[cite: 23]. 

The project focuses on mastering **Burp Suite Community Edition** for professional web application penetration testing, covering proxy setup, application mapping, manual exploitation via Repeater and Intruder, endpoint discovery using Gobuster, and formal VAPT vulnerability reporting[cite: 23, 25].

---

## 📂 Repository Structure

```text
├── Report/
│   └── Week7_VAPT_Report.pdf             # Comprehensive 15-page technical VAPT report
├── Presentation/
│   └── Week7_VAPT_Presentation.pptx      # Slide deck summarizing methodology and findings
├── Screenshots/
│   ├── burp_intercept/                   # Proxy configuration and HTTPS/HTTP traffic interception proofs
│   ├── site_map/                         # Target tool endpoint mapping and attack surface discovery
│   ├── repeater_tests/                   # SQL Injection and Reflected XSS request/response payload analysis
│   ├── intruder_auth/                    # Authentication testing and payload position configuration
│   └── gobuster_scan/                    # Directory and endpoint brute-forcing results
└── README.md                             # Project overview and documentation index

```

---

## 🛠️ Lab Environment & Toolchain Architecture

Testing was conducted in a controlled, isolated lab environment.

* **Target Application:** **DVWA (Damn Vulnerable Web Application)** self-hosted locally via Docker at `http://localhost:8081` (Security Level: Low).


* **Attacker / Analysis OS:** Kali Linux.


* **Primary Platform:** **Burp Suite Community Edition** (Intercepting Proxy, Target/Site Map, Repeater, Intruder).


* **Directory Brute-Forcer:** **Gobuster** (using the `dirb/common.txt` wordlist).



---

## 📋 Detailed Breakdown of Weekly Tasks & Execution

### Task 1: Burp Suite Setup & Intercepting Proxy Configuration

* Configured Burp Suite as an intercepting proxy on `127.0.0.1:8080` and installed Burp's CA certificate in the browser trust store to seamlessly capture and inspect HTTPS and HTTP traffic without security warnings.


* Analyzed plaintext credential transmission over HTTP login flows.



### Task 2: Reconnaissance & Application Mapping

* Browsed the complete DVWA application while routing traffic through Burp, allowing the **Target tool** to automatically build a comprehensive site map of endpoints, methods, parameters, and status codes.


* Prioritized high-value injection parameters across login, SQLi, XSS, and command execution modules.



### Task 3: Manual Vulnerability Testing (Repeater & Intruder)

* **SQL Injection (Repeater):** Sent the `id` parameter request to Repeater and injected `1 OR 1=1 --` to bypass form submission and dump all database user records in a single response.


* **Cross-Site Scripting (Repeater):** Modified the `name` parameter in Repeater to carry `<script>alert(1)</script>`, verifying unescaped reflection in the raw HTML response and browser render view.


* **Authentication Testing (Intruder):** Configured a Sniper attack in Intruder against the login password parameter. Discovered an essential technical nuance: dynamic single-use anti-CSRF tokens (`user_token`) must be refreshed per request to prevent uniform rejection across multi-request payload attacks.


* **Parameter Tampering:** Tested out-of-range numeric inputs (`id=200000000`) to confirm lack of server-side bounds validation.



### Task 4: Directory & Endpoint Discovery (Gobuster)

* Executed Gobuster against the target URL to brute-force hidden paths not visible through normal application navigation:


```bash
gobuster dir -u http://localhost:8081 -w /usr/share/wordlists/dirb/common.txt

```


* Uncovered non-public directories including `/config/`, `/docs/`, `/external/`, and directly reachable configuration files like `/php.ini`.



### Task 5: Formal Vulnerability Reporting

Documented confirmed findings using industry-standard VAPT reporting formats complete with descriptions, reproduction steps, impact assessments, and remediation guidance:

1. **SQL Injection (Critical):** Direct concatenation of user input in the `id` parameter allowing unauthorized database extraction.


2. **Reflected XSS (High):** Unsanitized `name` parameter echoing arbitrary JavaScript into victim browser sessions.


3. **Information Disclosure via Exposed Directories (Medium):** Reachable sensitive paths (`/config/`, `/php.ini`) expanding the application attack surface.



---

## 📊 Summary of Confirmed Findings

| # | Vulnerability | Location / Module | Risk Level | Description & Real-World Impact |
| --- | --- | --- | --- | --- |
| **1** | **SQL Injection** | DVWA - SQL Injection (`id`) | **Critical** | Input concatenated directly into SQL queries; permits complete extraction of database records without credentials.

 |
| **2** | **Reflected XSS** | DVWA - Reflected XSS (`name`) | **High** | Unsanitized input reflected in responses, enabling script execution, cookie theft, and session hijacking.

 |
| **3** | **Information Disclosure** | Server Root / Gobuster Scan | **Medium** | Exposed configuration and directory paths (`/config/`, `/php.ini`) leaking server architecture details.

 |

---

## 👤 Author & Program Details

* **Author:** Prakhar Gupta
* **Role:** Cybersecurity Intern
* **Hosting Organization:** DG Interns Hub Cybersecurity Internship Program


* **Submission Date:** 21 September 2025



```[cite: 6, 23, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36]

```
