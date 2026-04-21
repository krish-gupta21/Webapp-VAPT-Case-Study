# Webapp-VAPT-Case-Study
Anonymized web application security assessment showcasing real-world vulnerabilities including XSS, credential exposure, and broken access control.

# 🛡️ Web Application Security Assessment – Case Study

## 👨‍💻 Author
**Krish Gupta**

---

## 📌 Overview
This repository presents an **anonymized case study** of a vulnerability assessment performed on a real-world web application. 

The objective was to identify security weaknesses, understand their impact, and demonstrate how multiple vulnerabilities can be chained to achieve critical exploitation.

---

## 🚨 Key Vulnerabilities Identified

### 🔴 1. Credential Exposure (Critical)
Sensitive authentication tokens were found to be exposed in application responses, appearing in headers and response bodies of unprivileged requests.

* **Impact:** * Full account takeover.
    * Unauthorized access to private user data.
    * Long-term session compromise.

### 🟠 2. Stored Cross-Site Scripting (XSS)
User input was not properly sanitized before being stored in the database, allowing persistent script execution for any user viewing the affected page.

* **Example Payload:**
    ```html
    <script>alert('XSS_Vulnerability_Confirmed')</script>
    ```
* **Impact:** * Session hijacking via cookie theft.
    * Credential theft through fake login overlays.
    * Malicious script injection.

### 🟡 3. Broken Access Control
Certain endpoints lacked proper authorization validation, allowing low-privileged users to access restricted resources or administrative functions.

* **Impact:** * Unauthorized access to restricted resources.
    * Exposure of sensitive system configurations.

### 🔵 4. Sensitive Data Exposure
Application responses included sensitive user-related data (PII) without proper encryption or masking.

* **Impact:** * Privacy breaches and compliance risks.
    * Data scraping vulnerabilities.

---

## 🔗 Attack Chain
The true risk was demonstrated by combining vulnerabilities to escalate the overall impact:

> **XSS + Credential Exposure** $\rightarrow$ **Full Account Takeover**

By leveraging the Stored XSS to scrape the exposed credentials from another user’s session, an attacker could gain full control of any account visiting the compromised page.

---

## 🛠️ Tools & Techniques
* **Burp Suite:** Proxying, Repeater, and Intruder for request manipulation.
* **Nuclei:** Template-based automated vulnerability scanning.
* **Directory Fuzzing:** Discovery of hidden endpoints and unlinked files.
* **Manual Testing:** Business logic assessment and custom payload crafting.
* **HTTP Analysis:** Detailed inspection of Request/Response flows.

---

## 🧪 Methodology
1.  **Reconnaissance:** Endpoint discovery and tech-stack profiling.
2.  **Parameter Testing:** Identifying entry points for malicious input.
3.  **Auth Validation:** Testing the strength of authentication and authorization logic.
4.  **Input Validation:** Checking for XSS, SQLi, and injection flaws.
5.  **Exploitation:** Demonstrating proof-of-concept and impact chaining.

---

## 🔒 Remediation Recommendations
* **Strict Access Control:** Implement server-side authorization checks for every request.
* **Input Sanitization:** Validate and encode all user-supplied data using a secure allow-list.
* **Secure Token Handling:** Use `HttpOnly` and `Secure` flags; never expose tokens in response bodies.
* **Standards:** Align development with the **OWASP Top 10** framework.

---

## 📊 Key Learnings
* Deep insight into the real-world impact of OWASP Top 10 vulnerabilities.
* Practical experience in **vulnerability chaining** to demonstrate maximum risk.
* Refined a structured, ethical approach to security testing.

---

## ⚠️ Disclaimer
This case study is **fully anonymized**. All sensitive data, identifiers, and target-specific details have been removed to ensure responsible disclosure and ethical usage.
