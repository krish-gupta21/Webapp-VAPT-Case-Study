# Webapp-VAPT-Case-Study
Anonymized web application security assessment showcasing real-world vulnerabilities including XSS, credential exposure, and broken access control.

# 🛡️ Web Application Security Assessment – Case Study

## 👨‍💻 Author  
Krish Gupta

---

## 📌 Overview  
This repository presents an anonymized case study of a vulnerability assessment performed on a real-world web application.

The objective was to identify security weaknesses, understand their impact, and demonstrate how multiple vulnerabilities can be chained to achieve critical exploitation.

---

## 🚨 Key Vulnerabilities Identified  

### 🔴 1. Credential Exposure (Critical)  
Sensitive authentication tokens were exposed in application responses.

**Impact:**  
- Account takeover  
- Unauthorized access to user data  
- Session compromise  

---

### 🟠 2. Stored Cross-Site Scripting (XSS)  
User input was not properly sanitized, allowing persistent script execution.

**Example Payload:**
```html
<script>alert(1)</script>
