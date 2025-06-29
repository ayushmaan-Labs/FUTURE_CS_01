# FUTURE_CS_01

# 🔐 Report - Web Application Security Testing

## 🧪 Application: OWASP Juice Shop
- Set up using Docker on Ubuntu VM

## ✅ Vulnerability 1: SQL Injection

- **Location**: Login form
- **Payload Used**: `' OR 1=1--`
- **Result**: Logged in as unauthorized user
- **Impact**: Full authentication bypass
- **Severity**: Critical

## ✅ Vulnerability 2: Cross-Site Scripting (XSS)

- **Location**: Search bar
- **Payload Used**: `<script>alert(1)</script>`
- **Result**: JavaScript executed
- **Type**: Reflected XSS
- **Severity**: High

## Tools Used
- Docker
- Firefox (manual testing)
- Ubuntu 22.04

## Screenshots
![Image](https://github.com/user-attachments/assets/7bc2ac48-458b-47b0-ae3a-6539d71c1b46)

## ✅ Vulnerability 3: Hidden Functionality Exposure (Score Board)

- **Location**: `/#/score-board`
- **Discovery**: Manually accessed hidden route
- **Result**: Gained access to full list of challenges
- **Impact**: Information Disclosure
- **Severity**: Low
- **Notes**: This confirms presence of hidden functionality that may guide attackers to targets.

## Screenshots
![Image](https://github.com/user-attachments/assets/d9ea1812-c717-4050-8d9e-7cd9a7aa08fa)


---

## ✅ Vulnerability 4: Admin Login Challenge Triggered

- **Description**: Without valid credentials, admin login challenge was marked as complete (2-star difficulty)
- **Impact**: Indicates insecure authentication logic
- **Severity**: High
- **Status**: Triggered automatically after SQLi exploit

---

## 🧠 Learning Outcomes

- Understood **OWASP Top 10** risks in a live test environment
- Practiced SQL Injection and Reflected XSS attacks
- Navigated hidden routes and debugged Docker network issues
- Strengthened Linux command-line and Docker skills

---

## 🛠️ Troubleshooting Notes

- **Docker Port Error**: Resolved `port already allocated` by stopping existing containers:
  ```bash
  sudo docker ps
  sudo docker stop <container_id>

