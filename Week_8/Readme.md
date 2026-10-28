# 🛡️ DG Interns Hub — Cybersecurity Internship Program
## Week 8: Advanced VAPT (Attack Surface Mapping, Parameter Testing & Attack-Chain Analysis)

<p align="center">
  <img src="https://img.shields.io/badge/Internship-DG%20Interns%20Hub-blue?style=for-the-badge&logo=shield" alt="DG Interns Hub">
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" alt="Status Completed">
  <img src="https://img.shields.io/badge/Target-DVWA%20(Local%20Lab)-orange?style=for-the-badge" alt="DVWA Local Lab">
  <img src="https://img.shields.io/badge/Tool-Burp%20Suite-orange?style=for-the-badge&logo=burpsuite" alt="Burp Suite">
</p>

---

## 👨‍💻 Intern Details
* **Name:** Prakhar Gupta
* **Role:** Cybersecurity Intern
* **Program:** DG Interns Hub — Cybersecurity Internship Program
* **Submission Date:** 28 October 2026

---

## 🎯 Project Overview
This repository contains the documentation, artifacts, and findings for **Week 8** of the cybersecurity internship. The practical assessment focused on advanced Vulnerability Assessment and Penetration Testing (VAPT) methodologies, specifically **Attack Surface Mapping**, **Parameter Testing**, and **Attack-Chain Analysis** conducted within an authorized local lab environment.

---

## 🧪 Lab Environment & Tools
* **Target Application:** Damn Vulnerable Web Application (DVWA) hosted locally at `http://127.0.0.1:8080` (Configured to **Medium Security** setting).
* **Assessment Toolkit:** Burp Suite Community Edition (Proxy, Repeater, Sequencer) and modern web browser developer tools.
* **Scope:** Local training application modules including SQL Injection, Brute Force authentication, and Weak Session IDs.

---

## 📑 Key Modules & Findings

| Module / Vector | Observation / Finding | Risk Level | Status |
| :--- | :--- | :--- | :--- |
| **SQL Injection (SQLi)** | Modified user-ID parameter using Boolean logic (`2 OR 1=1`) successfully altered query logic, disclosing multiple records. | High (Lab) | Confirmed |
| **Brute Force Login** | Credentials observed in URL query strings (GET method) rather than a secure POST body. | Medium (Design) | Observed |
| **Weak Session IDs** | `dvwaSession` cookie values changed upon generation requests; requires statistical randomness analysis. | Low / Info | Needs Validation |
| **Parameter Validation** | Invalid/non-matching ID (`999`) returned HTTP 200 without disclosing records (expected safe behavior). | Informational | Baseline Verified |

---

## 📂 Repository Structure
```text
├── Week_8.pdf                 # Complete formal internship report (PDF)
├── README.md                  # Project documentation & summary
└── assets/                    # Burp Suite screenshots and figures (Figures 1 - 10)
