# Penetration Test Report

---

# Table of Contents

- [1. Executive Summary (Management Summary)](#1-executive-summary-management-summary)
- [2. Introduction](#2-introduction)
    - [2.1 Purpose](#21-purpose)
    - [2.2 Target](#22-target)
    - [2.3 Scope](#23-scope)
    - [2.4 Methodology](#24-methodology)
    - [2.5 Timeline](#25-timeline)
    - [2.6 Assumptions](#26-assumptions)
- [3. Initial Situation & Objectives](#3-initial-situation--objectives)
- [4. Methodology & Tools](#4-methodology--tools)
- [5. Testing & Findings](#5-testing--findings)
- [6. Recommendations](#6-recommendations)
- [7. Appendices (Optional)](#7-appendices-optional)

---

## 1. Executive Summary (Management Summary)

This report presents the results of a black-box penetration test performed on the **OWASP Juice Shop** web application. The objective was to identify exploitable security vulnerabilities that could impact the confidentiality, integrity, and availability of the application and its users.

### Key Findings

- **SQL Injection:** Allows attackers to manipulate backend databases.
- **Broken Authentication:** Enables unauthorized access to user accounts.
- **Cross-Site Scripting (XSS):** Allows execution of malicious scripts in users' browsers.
- **Server-Side Request Forgery (SSRF):** Permits attackers to induce the server to make unintended requests.

### Business Risks

The identified vulnerabilities could lead to:
- Unauthorized access and data breaches.
- Data manipulation or loss.
- Loss of user trust and reputational damage.

### Key Recommendations

- Prioritize remediation of critical vulnerabilities such as SQL Injection and authentication flaws.
- Establish regular security testing and code reviews.
- Integrate secure development lifecycle practices to prevent future vulnerabilities.

---

## 2. Introduction

### 2.1 Purpose

The purpose of this penetration test is to evaluate the security posture of the OWASP Juice Shop application by identifying common web application vulnerabilities through ethical hacking techniques.

### 2.2 Target

The target of this assessment is the OWASP Juice Shop, an intentionally vulnerable e-commerce web application designed for security training.

### 2.3 Scope

Testing focuses on critical areas including:
- Application endpoints
- User authentication mechanisms
- Data storage practices
- Input validation processes
- Access control measures

All testing aligns with the OWASP Top 10 vulnerability categories.

### 2.4 Methodology

A black-box testing approach was employed, simulating an external attacker without prior knowledge or access. The testing combined manual techniques and automated tools such as OWASP ZAP, Tenable Nessus and Burp Suite, guided by the OWASP Testing Guide.

### 2.5 Timeline

- Start Date: **15.05.2025**
- End Date: **05.06.2025**

### 2.6 Assumptions

- Testing is conducted in a controlled, isolated environment.
- Denial-of-service or disruptive attacks will be avoided.
- All activities are authorized and comply with university policies.

---

## 3. Initial Situation & Objectives

This penetration test was conducted as part of a university cybersecurity project aimed at simulating a professional security assessment. The objectives include:

- Identifying vulnerabilities that could be exploited by attackers.
- Assessing the security posture of the OWASP Juice Shop application.
- Providing clear remediation guidance to enhance the application’s security.

---

## 4. Methodology & Tools

The test followed a structured process based on the OWASP Testing Guide, targeting the OWASP Top 10 risks. The following tools were used throughout the engagement:

- Burp Suite Community Edition
- JWT Editor Burp Extension
- Sqlmap
- CrackStation
- Hashcat
- JWT.io
- FoxyProxy
- Firefox
- Kali Linux

Each vulnerability discovery includes a description, evidence such as screenshots and logs, severity assessment, and recommended remediation steps.

---

## 5. Testing & Findings

*(This section will be completed after testing.)*

### 5.1 SQL Injection

- **Description:** SQL Injection is a type of cyberattack where an attacker inserts malicious SQL code into a query to manipulate or access a database in unauthorized ways. It usually targets insecure input fields in web applications.


- **Evidence:** By entering ' OR 1=1 -- in the Email field and anything in the password field, the application logs in as the first user in the database, which in this case happens to be the administrator.
-  ![SQL Injection exploit](screenshots/sql_injection)


- **Severity:** **_Critical_** – This allows an attacker to bypass authentication, access sensitive data, and potentially take full control of the application (admin privileges).


- **Remediation Advice:**
  - Use parameterized queries (prepared statements) to prevent SQL injection.
  - Sanitize and validate all user inputs.
  - Apply least privilege to database accounts (e.g., limit read/write access).

---

## 6. Recommendations

- Remediate critical and high-severity vulnerabilities promptly.
- Enhance input validation and output encoding to prevent injection attacks.
- Implement multi-factor authentication mechanisms.
- Provide ongoing secure coding training for developers.
- Schedule regular penetration testing and vulnerability assessments.

---

## 7. Appendices (Optional)

- Comprehensive logs and raw tool outputs.
- Screenshots and proof of concept for vulnerabilities found.  
