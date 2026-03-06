# Web Application Penetration Testing with Burp Suite Pro

##  Project Overview
This project documents a **web application penetration test** conducted on the intentionally vulnerable website:

Target: http://testphp.vulnweb.com/

The objective of this assessment is to identify and demonstrate common web vulnerabilities using **Burp Suite Professional**.

Disclaimer:  
This website is intentionally vulnerable and created for security testing and educational purposes only.

---

## Objectives
- Perform manual penetration testing using Burp Suite Pro
- Identify security vulnerabilities
- Demonstrate proof-of-concept exploits
- Provide remediation recommendations

---

## Tools Used

- Burp Suite Professional
- Web Browser (Firefox)
- Burp Scanner

---

## Testing Methodology

The testing methodology followed common penetration testing frameworks such as:

- OWASP Testing Guide
- PTES (Penetration Testing Execution Standard)

### Steps

1. Reconnaissance
2. Application Mapping
3. Intercepting Requests
4. Parameter Testing
5. Vulnerability Identification
6. Exploitation
7. Reporting

---

##  Vulnerabilities Identified

### 1️ SQL Injection
**Endpoint:**

## /listproducts.php?cat=

**Description:**  
The application fails to properly sanitize user input, allowing SQL queries to be manipulated.

Payload Example:

```sql
1' OR '1'='1
```

Impact:
- Unauthorized database access
- Data extraction

### 2️ Cross-Site Scripting (XSS)

Endpoint:

/search.php?test=

**Payload:**

```<script>alert('XSS')</script>
```

Impact:

Session hijacking

Credential theft

Malicious script execution

### 3️ Cross-Site Request Forgery (CSRF)

Description:
The application does not implement anti-CSRF tokens.

Impact:
Attackers could trick authenticated users into performing unwanted actions.

📸 Proof of Concept

Screenshots of the vulnerabilities can be found in the /screenshots directory.

Example:
screenshots/
   sql_injection.png
   xss_attack.png
   burp_proxy_capture.png
   
### Mitigation Recommendations

Implement prepared statements for database queries

Apply input validation and output encoding

Add CSRF tokens to sensitive requests

Implement Content Security Policy (CSP)

Sanitize all user input

###  References

OWASP Top 10

Burp Suite Documentation

Web Security Academy

### Legal Disclaimer

This project is for educational purposes only.
Testing was performed on a deliberately vulnerable application designed for security practice.

### Author

Your Name
IGUE SAMUEL / Penetration Tester

GitHub: https://github.com/simplenation
