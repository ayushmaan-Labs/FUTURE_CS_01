# FUTURE_CS_01

# 🔐 Internship Report - Web Application Security Testing

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
*(You can add them later after pushing to GitHub)*
