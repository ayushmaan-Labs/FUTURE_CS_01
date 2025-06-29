# FUTURE_CS_01
## 📄 Executive Summary

This report summarizes the findings from a web application penetration test of OWASP Juice Shop. The test identified critical vulnerabilities such as SQL Injection and Reflected XSS using manual testing techniques. The vulnerabilities were verified, documented, and mapped to the OWASP Top 10. Recommended mitigations are provided to enhance the security posture of the application.

# 🔐 Report - Web Application Security Testing

## 🧪 Application: OWASP Juice Shop
- Set up using Docker on Ubuntu VM

## ✅ Vulnerability 1: SQL Injection

- **Location**: Login form
- **Payload Used**: `' OR 1=1--`
- **Result**: Logged in as unauthorized user
- **Impact**: Full authentication bypass
- **Severity**: Critical

## Screenshots
![Image](https://github.com/user-attachments/assets/02a9e058-e391-4628-a61c-0e36bc09341d)
![Image](https://github.com/user-attachments/assets/287b7f59-dd69-4582-bbec-e3a361bd2d06)

### 🛠️ Mitigation
Use parameterized queries (prepared statements) to avoid injecting raw SQL. Sanitize all input fields and apply strict input validation.

## ✅ Vulnerability 2: Reflected Cross-Site Scripting (XSS)

- **Location**: Search bar  
- **Payload Used**: `<iframe src="javascript:alert('xss')">`  
- **Result**: Payload executed immediately upon search  
- **Impact**: Could allow malicious actors to steal session cookies or perform actions on behalf of the user  
- **Type**: Reflected XSS  
- **Severity**: High 

## Screenshot

![Image](https://github.com/user-attachments/assets/a4b1b4bb-0d49-423f-ba59-f69adef3ad44)

8d9e-7cd9a7aa08fa)

### 🛠️ Mitigation
Sanitize and encode user inputs before reflecting them into the DOM. Use frameworks or libraries that auto-handle XSS (e.g., React, Angular).

## ✅ Vulnerability 3: Hidden Functionality Exposure (Score Board)

- **Location**: `/#/score-board`
- **Discovery**: Manually accessed hidden route
- **Result**: Gained access to full list of challenges
- **Impact**: Information Disclosure
- **Severity**: Low
- **Notes**: This confirms presence of hidden functionality that may guide attackers to targets.

## Screenshot
![Image](https://github.com/user-attachments/assets/d9ea1812-c717-4050-8d9e-7cd9a7aa08fa)

### 🛠️ Mitigation
Disable access to non-public routes using proper role-based access control. Avoid exposing internal paths or debug pages in production.

---

## ✅ Vulnerability 4: Admin Login Challenge Triggered

- **Description**: Without valid credentials, admin login challenge was marked as complete (2-star difficulty)
- **Impact**: Indicates insecure authentication logic
- **Severity**: High
- **Status**: Triggered automatically after SQLi exploit
  
## Screenshot
![Image](https://github.com/user-attachments/assets/8003c045-4423-472b-8087-c2d57945b5d7)

### 🛠️ Mitigation
Harden authentication logic and avoid exposing insecure challenge logic. Validate credentials server-side and use secure session handling.

---

## 🧠 Learning Outcomes

- Understood **OWASP Top 10** risks in a live test environment
- Practiced SQL Injection and Reflected XSS attacks
- Navigated hidden routes and debugged Docker network issues
- Strengthened Linux command-line and Docker skills

---

## 🧩 OWASP Top 10 Mapping

| Vulnerability | OWASP Category |
|---------------|----------------|
| SQL Injection | A03:2021 - Injection |
| XSS           | A07:2021 - Cross-Site Scripting |
| Hidden Routes | A05:2021 - Security Misconfiguration |
| Insecure Auth | A01:2021 - Broken Access Control |


