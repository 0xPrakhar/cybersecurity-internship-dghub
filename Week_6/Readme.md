```markdown
# Week 6: Web Security & Vulnerability Assessment and Penetration Testing (VAPT)

This repository houses the complete documentation, technical assessment reports, presentation decks, study notes, and proof-of-concept artifacts for the **Week 6 Practical Assessment** completed during the Cybersecurity Internship Program at **DG Interns Hub**[cite: 6]. 

The primary objective of this project is to bridge theoretical cybersecurity principles—specifically the **OWASP Top 10** web application risks—with practical, hands-on execution using **DVWA (Damn Vulnerable Web Application)**[cite: 6, 7].

---

## 📂 Complete Repository Structure

```text
├── Report/
│   └── Week6_VAPT_Project_Report.pdf     # Comprehensive 13-page technical VAPT report
├── Presentation/
│   └── Week6_VAPT_Presentation.pptx      # Slide deck summarizing methodology, tools, and findings
├── Notes/
│   └── OWASP_Top10_Notes.md              # In-depth study notes on web vulnerabilities & attack vectors
├── Screenshots/
│   ├── sql_injection/                    # Step-by-step evidence for SQLi baseline & UNION injection payloads
│   ├── xss_tests/                        # Execution proofs for Reflected and Stored XSS scripts
│   ├── burp_suite/                       # Proxy traffic captures and Repeater request/response analysis
│   └── owasp_zap/                        # Automated spider crawls, active scans, and alert breakdowns
└── README.md                             # Project overview and documentation index

```

---

## 🛠️ Lab Environment & Toolchain Architecture

Testing was performed exclusively within an isolated, local development environment to ensure safety, control, and legal compliance.

* **Target Application:** **DVWA (Damn Vulnerable Web Application)** hosted locally via XAMPP (`http://localhost/dvwa/`) on an Apache, MySQL, and PHP stack.


* **Testing / Attacker OS:** **Kali Linux**.


* **Intercepting Proxy:** **Burp Suite Community Edition** configured through Mozilla Firefox and FoxyProxy (`127.0.0.1:8080`) to inspect and tamper with live HTTP headers, cookies, and parameters.


* **Automated DAST Scanner:** **OWASP ZAP (Zed Attack Proxy)** used for automated spidering, endpoint discovery, and active injection scanning.



---

## 📋 Detailed Breakdown of Weekly Tasks & Execution

### Task 1: Study of the OWASP Top 10

Comprehensive study notes were compiled covering the fundamental architecture of web security vulnerabilities:

* **SQL Injection (SQLi):** Occurs when untrusted user input is directly concatenated into SQL statements without sanitization or parameterization, permitting query manipulation, authentication bypass, and unauthorized data extraction.


* **Cross-Site Scripting (XSS):** Divided into **Reflected XSS** (payload executed immediately via URL/request parameters), **Stored XSS** (payload persisted server-side in databases/guestbooks and served to all users), and DOM-based XSS.


* **Broken Authentication:** Flaws in session management, lack of rate limiting, unhashed password storage, and vulnerable credential recovery mechanisms leading to account takeovers.


* **Security Misconfiguration:** Risks arising from default credentials, verbose error stacks leaking internal paths, directory listing enabled, and missing security headers (CSP, X-Frame-Options).



### Task 2: Environment Setup & Tool Configuration

* Deployed XAMPP to run a local Apache web server and MySQL database backend.


* Cloned and configured DVWA into the `htdocs` directory, initializing database tables via `setup.php`.


* Installed Burp Suite and configured Firefox with FoxyProxy to seamlessly route, intercept, and drop web traffic.



### Task 3: Manual Testing & Payload Execution on DVWA

* **SQL Injection Module (Low Level):**
* *Baseline Request:* Submitted standard numeric IDs to observe expected database outputs.


* *Payload Injection:* Executed logic-altering and extraction strings (`' OR '1'='1` and `UNION SELECT user, password FROM users`) which successfully exposed hidden database credentials and table records.




* **Cross-Site Scripting Modules:**
* *Reflected XSS:* Submitted `<script>alert('Reflected XSS')</script>` into input fields, confirming immediate script execution within the browser context.


* *Stored XSS:* Posted malicious script payloads into the application guestbook, verifying that the script persisted on the server and executed automatically for every subsequent visitor.





### Task 4: Traffic Interception & Analysis (Burp Suite)

* **Proxy Intercept:** Captured raw HTTP GET and POST requests in real-time, analyzing cookie parameters, user-agents, and injection vectors.


* **Repeater Analysis:** Sent intercepted requests into Burp Repeater to iteratively modify parameters and examine side-by-side server responses without re-submitting web forms.



### Task 5: Automated Vulnerability Scanning (OWASP ZAP)

* Executed ZAP's **Automated Scan** utility against the local DVWA target URL.


* Used the automated spider to crawl and map directory paths, followed by an active scan injecting attack rule sets across discovered parameters.


* Reviewed categorized alerts in the Alerts panel grouped by risk level (High, Medium, Low) and exported the final scan report.



---

## 📊 Summary of Confirmed Findings & Risk Levels

| # | Vulnerability | Location / Module | Risk Level | Description & Real-World Impact |
| --- | --- | --- | --- | --- |
| **1** | **SQL Injection** | DVWA - SQL Injection Module | **High** | Input concatenated directly into SQL queries; permits full database extraction and authentication bypass.

 |
| **2** | **Reflected XSS** | DVWA - XSS (Reflected) | **High** | Unsanitized parameters reflected in page response, executing arbitrary JavaScript in victim browsers.

 |
| **3** | **Stored XSS** | DVWA - XSS (Stored) / Guestbook | **High** | Malicious script persisted server-side, executing automatically for every user viewing the page.

 |
| **4** | **Broken Authentication** | DVWA - Brute Force Module | **Medium** | Absence of rate limiting, account lockout policies, or CAPTCHA protection against credential stuffing.

 |
| **5** | **Security Misconfiguration** | Server & DVWA Configuration | **Medium** | Verbose error messaging and unpatched component headers exposing internal application architecture.

 |
| **6** | **Missing Security Headers** | Application-wide (ZAP Scan) | **Low** | Absence of Content Security Policy (CSP), X-Frame-Options, and HSTS weakening defense-in-depth.

 |

---

## 🛡️ Recommended Mitigation Strategies

* **For SQL Injection:** Implement parameterized queries (prepared statements), enforce the principle of least privilege on database accounts, and disable verbose database error reporting in production.


* **For Cross-Site Scripting:** Contextually encode and escape all user-supplied output rendered in HTML/JavaScript contexts, enforce a strict Content Security Policy (CSP), and set `HttpOnly` and `Secure` flags on session cookies.


* **For Broken Authentication:** Enforce robust password complexity rules, implement account lockout or rate-limiting thresholds after consecutive failed attempts, and integrate Multi-Factor Authentication (MFA).


* **For Misconfigurations:** Remove default files and accounts, automate configuration hardening pipelines, and apply recommended security headers across all responses.



---

## 👤 Author & Program Details

* **Author:** Prakhar Gupta
* **Role:** Cybersecurity Intern
* **Hosting Organization:** DG Interns Hub Cybersecurity Internship Program


* **Submission Date:** 14 October 2026



```

```
