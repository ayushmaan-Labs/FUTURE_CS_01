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
