# 🌐 Web Application Basics | WAPT Learning

<div align="center">

![Web Security](https://img.shields.io/badge/Domain-Web%20Application%20Security-blue?style=for-the-badge)
![Internship](https://img.shields.io/badge/Internship-IqraSec%20Academy-red?style=for-the-badge)
![Phase](https://img.shields.io/badge/Phase-01-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Learning-orange?style=for-the-badge)

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=22&pause=1000&color=00C7FF&center=true&vCenter=true&width=650&lines=Welcome+to+Web+Application+Security;Learn+%7C+Understand+%7C+Test+%7C+Secure;Building+WAPT+Fundamentals" alt="Animated typing banner" />

**Understand Web Applications. Learn Security. Practice Ethical Hacking.**

</div>

---

## 📌 1. Project Overview

Welcome to the **Web Application Basics** learning repository.

This repository is created as part of the Web Application Penetration Testing (WAPT) Internship at IqraSec Academy.

The main purpose of this project is to understand how web applications work, learn their underlying technologies, explore common web security vulnerabilities, and develop the fundamental skills required for web application security testing.

This repository is designed for beginners who want to start learning web application security from the basics.

It includes theoretical explanations, learning notes, testing methodologies, practical commands, lab exercises, and security recommendations.

## 🎯 2. Learning Objectives

The main learning objectives are:

- Understand how websites and web applications work.
- Learn client-server architecture.
- Understand HTTP and HTTPS communication.
- Learn HTTP requests and responses.
- Understand DNS and basic networking concepts.
- Explore passive and active reconnaissance.
- Learn Burp Suite and its Repeater functionality.
- Understand common web application vulnerabilities.
- Practice vulnerability testing in authorized environments.
- Learn security assessment and remediation techniques.

## 🌍 3. What Is a Web Application?

A web application is software that runs on a web server and can be accessed through a web browser.

Examples include:

- Online banking applications.
- E-commerce websites.
- Social media platforms.
- Content management systems.
- Online learning platforms.
- Web-based dashboards.

### How Does a Web Application Work?

A basic web application follows a client-server communication model.

1. A user opens a website in a browser.
2. The browser sends an HTTP request to the server.
3. The server processes the request.
4. The server communicates with the database when required.
5. The server generates an HTTP response.
6. The browser displays the requested content.

**Basic Architecture:**

```text
        USER
          |
          v
     WEB BROWSER
          |
          | HTTP / HTTPS Request
          v
      WEB SERVER
          |
          v
    APPLICATION LOGIC
          |
          v
       DATABASE
          |
          v
     SERVER RESPONSE
          |
          v
      WEB BROWSER
```

## 🧰 4. Tools & Technologies

| Tool | Purpose |
|---|---|
| Burp Suite | Web application security testing |
| Kali Linux | Security testing environment |
| Nmap | Network and service discovery |
| Nmap NSE | Script-based service checks |
| curl | HTTP request testing |
| Browser DevTools | Inspecting web applications |
| Firefox | Web application testing |
| OWASP Juice Shop | Vulnerable practice application |
| PortSwigger Web Security Academy | Web security learning and labs |
| Git & GitHub | Documentation and version control |

## 📚 5. Learning Modules

### Module 01 – Web Fundamentals

Topics:

- Room 1: Web Application Basics
- Room 2: HTTP in Detail

Learning focus:

- Client-server architecture.
- Web application components.
- HTTP methods.
- Request and response structure.
- HTTP status codes.
- Headers, cookies and sessions.
- HTTPS and TLS fundamentals.

### Module 02 – Reconnaissance & Enumeration

Topics:

- Room 1: Passive Recon
- Room 2: Active Recon
- Room 3: Content Discovery

Learning focus:

- Information gathering.
- DNS enumeration.
- Subdomain discovery.
- Technology identification.
- Directory and file discovery.
- Understanding the application attack surface.

### Module 03 – Burp Suite

Topics:

- Room 1: Burp Suite Repeater

Learning focus:

- Proxy fundamentals.
- HTTP request interception.
- Request modification.
- Response analysis.
- Repeater functionality.
- Manual security testing.

### Module 04 – Common Web Vulnerabilities

The following vulnerability areas are included in this learning repository.

| No. | Vulnerability / Topic |
|---|---|
| 01 | Authentication & Access Control |
| 02 | Broken Access Control |
| 03 | Command Injection |
| 04 | Cross-Site Request Forgery (CSRF) |
| 05 | File Inclusion |
| 06 | Insecure Direct Object Reference (IDOR) |
| 07 | SQL Injection |
| 08 | File Upload Vulnerabilities |
| 09 | Cross-Site Scripting (XSS) |

Additional practical learning environments:

- OWASP Juice Shop
- PortSwigger Web Security Academy

---

## 🔬 6. Basic Vulnerability Testing Commands

**Important:** The following examples are for authorized, intentionally vulnerable labs or applications running locally. Replace placeholders with your own lab URL and parameters. Never test websites without permission.

### 01. Authentication Testing

Authentication testing checks how an application verifies user identities.

Basic request:

```bash
curl -i http://127.0.0.1:3000/login
```

POST request example:

```bash
curl -i -X POST http://127.0.0.1:3000/login \
-d "username=testuser&password=testpass"
```

Things to observe:

- Login response.
- Authentication errors.
- Session creation.
- Cookie security.
- Account lockout behavior.

### 02. Broken Access Control

This vulnerability occurs when users can access resources or perform actions beyond their authorized permissions.

Basic request:

```bash
curl -i http://127.0.0.1:3000/profile
```

Check an authorized test user's access to another test resource:

```bash
curl -i http://127.0.0.1:3000/admin
```

Things to observe:

- HTTP 200, 403 or 401 responses.
- Unauthorized access.
- Role-based permissions.
- Server-side authorization checks.

### 03. Command Injection

Command injection occurs when an application incorrectly passes user input into operating system commands.

Example test input for an authorized lab:

```text
127.0.0.1; id
```

Another basic test:

```text
127.0.0.1 && whoami
```

Things to observe:

- Unexpected command output.
- Application errors.
- Input validation.
- Secure command execution.

### 04. Cross-Site Request Forgery (CSRF)

CSRF attempts to make an authenticated user's browser perform an unwanted action.

Basic testing checklist:

```text
1. Identify a state-changing request.
2. Inspect its HTTP method.
3. Check whether a CSRF token exists.
4. Check token validation.
5. Verify Origin and Referer handling.
6. Test only with an authorized lab account.
```

Things to observe:

- CSRF token implementation.
- Cookie SameSite attributes.
- Origin validation.
- Server-side request verification.

### 05. File Inclusion

File inclusion vulnerabilities occur when an application improperly handles file paths or includes user-controlled files.

Basic lab test input:

```text
../../../../etc/passwd
```

Example request:

```bash
curl -i "http://127.0.0.1:3000/view?file=../../../../etc/passwd"
```

Things to observe:

- Path traversal.
- File access restrictions.
- Input validation.
- Safe file handling.

### 06. IDOR – Insecure Direct Object Reference

IDOR occurs when an application allows users to access another user's resources by changing an object identifier without proper authorization checks.

Example:

```bash
curl -i http://127.0.0.1:3000/api/users/1001
```

Test a second ID belonging to your own lab:

```bash
curl -i http://127.0.0.1:3000/api/users/1002
```

Things to observe:

- Object-level authorization.
- User ownership checks.
- API response differences.
- Unauthorized data exposure.

### 07. SQL Injection (SQLi)

SQL Injection occurs when untrusted user input is improperly included in database queries.

Basic lab payload:

```sql
' OR '1'='1'--
```

Example request:

```bash
curl -i -G "http://127.0.0.1:3000/search" \
--data-urlencode "q=' OR '1'='1'--"
```

Things to observe:

- Database errors.
- Unexpected query behavior.
- Input handling.
- Parameterized queries.
- Database error disclosure.

### 08. File Upload Vulnerabilities

File upload vulnerabilities occur when an application does not properly validate uploaded files.

Create a harmless test file:

```bash
echo "WAPT Upload Test" > test.txt
```

Upload it to an authorized lab endpoint:

```bash
curl -i -X POST \
-F "file=@test.txt" \
http://127.0.0.1:3000/upload
```

Things to observe:

- File extension validation.
- MIME type validation.
- File size restrictions.
- File storage location.
- Server-side file validation.

### 09. Cross-Site Scripting (XSS)

XSS occurs when an application allows untrusted content to execute as JavaScript in another user's browser.

Basic harmless lab payload:

```html
<script>alert('XSS Test')</script>
```

Example URL test:

```text
http://127.0.0.1:3000/search?q=%3Cscript%3Ealert(1)%3C%2Fscript%3E
```

Things to observe:

- Reflected XSS.
- Stored XSS.
- DOM-based XSS.
- Output encoding.
- Content Security Policy (CSP).

---

## 🧪 7. Practical Learning Environments

### OWASP Juice Shop

OWASP Juice Shop is an intentionally vulnerable web application designed for security training and practical exercises.

Official resource:

https://owasp.org/www-project-juice-shop/

### PortSwigger Web Security Academy

PortSwigger Web Security Academy provides free web security learning materials and interactive labs.

Official resource:

https://portswigger.net/web-security

---

## 🛡️ 8. Security Best Practices & Remediation

| Vulnerability | Recommended Protection |
|---|---|
| Authentication Issues | MFA, secure sessions, strong password policies |
| Broken Access Control | Server-side authorization checks |
| Command Injection | Avoid shell execution and validate inputs |
| CSRF | CSRF tokens and appropriate SameSite cookies |
| File Inclusion | Strict file allowlists and safe path handling |
| IDOR | Object-level authorization |
| SQL Injection | Parameterized queries |
| File Upload | File validation, safe storage and access restrictions |
| XSS | Context-aware output encoding and CSP |

## 📂 9. Repository Structure

```text
Web-Application-Basics/
│
├── README.md
│
├── 1.Web-Fundamentals/
│   ├── Room1_Web-Application-Basics/
│   │   └── Room1_Web-Application-Basics.pdf
│   │
│   └── Room2_HTTP-in-Detail/
│
├── 2.Recon-Enumeration/
│   ├── Room1_Passive-Recon/
│   ├── Room2_Active-Recon/
│   └── Room3_Content-Discovery/
│
├── 3.Burp-Suite/
│   └── Room1_Burp-Suite-Repeater/
│
└── 4.Common-Web-Vulnerabilities/
    ├── Authentication-Access-Control/
    ├── Broken-Access-Control/
    ├── Command-Injection/
    ├── CSRF/
    ├── File-Inclusion/
    ├── IDOR/
    ├── OWASP-Juice-Shop/
    ├── PortSwigger-Lab/
    ├── SQL-Injection/
    ├── Upload-Vulnerabilities/
    └── XSS/
```

*Note: This is the intended documentation structure. Add only the files and folders that actually exist in your repository.*

## 📈 10. Learning Outcomes

After completing these learning modules, the expected learning outcomes include:

- Understanding web application architecture.
- Reading and analyzing HTTP requests and responses.
- Understanding basic reconnaissance techniques.
- Using Burp Suite for manual request analysis.
- Recognizing common web application vulnerabilities.
- Performing basic tests in authorized lab environments.
- Understanding security risks and mitigation techniques.
- Writing structured technical documentation.

## 📖 11. References

1. OWASP Top 10 – https://owasp.org/www-project-top-ten/
2. OWASP Web Security Testing Guide – https://owasp.org/www-project-web-security-testing-guide/
3. PortSwigger Web Security Academy – https://portswigger.net/web-security
4. MDN Web Docs – https://developer.mozilla.org/
5. OWASP Juice Shop – https://owasp.org/www-project-juice-shop/
6. RFC Editor – https://www.rfc-editor.org/

## ⚠️ 12. Disclaimer

This repository is created strictly for educational purposes and authorized cybersecurity training.

All practical security testing must be performed on personally owned systems, intentionally vulnerable lab environments, or systems for which explicit permission has been granted.

Unauthorized access, testing, exploitation, or disruption of third-party systems is not supported.

## 👨‍💻 13. Internship Information

**Program:** Web Application Penetration Testing Internship  
**Organization:** IqraSec Academy  
**Phase:** Phase 1 – Learning & Foundation  
**Submission Period:** 1 November – 5 November 2026

---

<div align="center">

**Learn. Practice. Analyze. Secure.**

*Building strong foundations in Web Application Security.*

</div>
