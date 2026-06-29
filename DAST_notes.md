# 📘 DAST (Dynamic Application Security Testing) – Fundamentals

> A beginner-friendly guide to understanding **Dynamic Application Security Testing (DAST)**, its purpose, evolution, workflow, benefits, limitations, and popular tools.

---

# 📑 Table of Contents

- [What is DAST?](#-what-is-dast)
- [Why DAST Exists](#-why-dast-exists)
- [History & Evolution](#-history--evolution)
- [Where DAST Fits](#-where-dast-fits)
- [How DAST Works](#-how-dast-works)
- [What DAST Tests](#-what-dast-tests)
- [Types of DAST](#-types-of-dast)
- [Benefits of DAST](#-benefits-of-dast)
- [Limitations of DAST](#-limitations-of-dast)
- [Popular DAST Tools](#-popular-dast-tools)
- [Modern Usage](#-modern-usage)
- [Key Takeaways](#-key-takeaways)
- [Next Steps](#-next-steps)

---

# 🔍 What is DAST?

**Dynamic Application Security Testing (DAST)** is a security testing methodology that evaluates a **running application** from the outside to identify security vulnerabilities.

Unlike Static Application Security Testing (SAST), DAST does **not require access to the source code**. It interacts with the application the same way a hacker or end user would.

---

## ✅ Simple Explanation

DAST:

- Tests applications while they are running
- Does **not** require source code
- Simulates real attacker behavior
- Finds vulnerabilities by sending malicious inputs
- Evaluates runtime security

---

## 🧠 Analogy

| Concept | Example |
|----------|---------|
| Application | House |
| DAST Tester | Attacker |
| Testing | Trying to break doors or windows |

> **Think of DAST as checking how secure a house is from the outside without knowing how it was built.**

---

# ❓ Why DAST Exists

## 🚨 Problem Before DAST

Traditional software testing mainly focused on:

- Functional Testing ✅
- Code Correctness ✅

Security testing was often ignored.

As a result, applications worked correctly but still contained serious security vulnerabilities.

---

## ⚠️ Common Security Issues

Applications were vulnerable to:

- SQL Injection
- Cross-Site Scripting (XSS)
- Broken Authentication
- Command Injection
- Directory Traversal

Even though all functional tests passed successfully.

---

## 🔍 Gap in Traditional Testing

| Testing Method | Limitation |
|----------------|------------|
| Functional Testing | No security validation |
| Code Review | Misses runtime behavior |

---

## ✅ Solution: DAST

DAST was introduced to:

- Identify vulnerabilities in live applications
- Simulate real-world attacks
- Validate application security during runtime

> **Key Insight:**  
> *A working application is not always a secure application.*

---

# 🕰️ History & Evolution

## 📌 Phase 1: Early Web (1990s–2005)

Characteristics:

- Basic websites
- Little security awareness
- Manual testing only

---

## 📌 Phase 2: Rise of Web Attacks (2005–2012)

Cyberattacks became more sophisticated.

Common attacks included:

- SQL Injection
- Cross-Site Scripting (XSS)

OWASP introduced the **OWASP Top 10** to highlight common web application risks.

Popular tools:

- IBM AppScan
- HP WebInspect

---

## 📌 Phase 3: Open-Source Expansion (2012–2018)

Security testing became more accessible.

Popular tools:

- OWASP ZAP
- Nikto

Automation became increasingly popular.

---

## 📌 Phase 4: DevSecOps Era (2018–Present)

Modern DAST includes:

- Continuous Security Testing
- CI/CD Integration
- API Security Testing
- Cloud-native applications

> **Key Insight:**  
> *DAST evolved because attackers became more advanced.*

---

# 🧭 Where DAST Fits

## 🔐 Security Testing Types

| Type | Description |
|------|-------------|
| SAST | Tests source code |
| DAST | Tests running application |
| IAST | Combines SAST and DAST techniques |
| Penetration Testing | Manual exploitation of vulnerabilities |

---

## ⚖️ SAST vs DAST

| Feature | SAST | DAST |
|---------|------|------|
| Requires Source Code | ✅ | ❌ |
| Tests Running Application | ❌ | ✅ |
| Simulates Attacks | ❌ | ✅ |
| Early SDLC | ✅ | ❌ |

> **Key Insight:**  
> *SAST predicts vulnerabilities, while DAST proves they can be exploited.*

---

# ⚙️ How DAST Works

## 🔄 DAST Workflow

```text
Identify Endpoints
        │
        ▼
Send HTTP Requests
        │
        ▼
Inject Attack Payloads
        │
        ▼
Analyze Responses
        │
        ▼
Report Vulnerabilities
```

---

## 🧪 Example

### Normal Request

```http
POST /login

username=admin
password=123456
```

---

### Attack Request

```http
POST /login

username=admin' OR '1'='1
password=test
```

If authentication succeeds unexpectedly, it indicates a potential **SQL Injection vulnerability**.

---

# 🔎 What DAST Tests

## Common Vulnerabilities

- SQL Injection (SQLi)
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Broken Authentication
- Security Misconfigurations
- Sensitive Data Exposure
- Command Injection
- Directory Traversal

---

## Real-World Scenarios

DAST can identify:

- Login bypass
- Unauthorized data access
- Session vulnerabilities
- Injection attacks
- Information disclosure

---

# 🧪 Types of DAST

## 🔹 Automated DAST

Characteristics:

- Tool-driven scanning
- Fast
- Scalable
- Suitable for CI/CD pipelines

Examples:

- OWASP ZAP
- Burp Scanner
- Invicti

---

## 🔹 Manual DAST

Characteristics:

- Human-driven testing
- Deep vulnerability analysis
- Better for business logic flaws
- Used during penetration testing

> **Key Insight:**  
> *Automation finds more vulnerabilities quickly, while manual testing finds deeper issues.*

---

# ✅ Benefits of DAST

- No source code required
- Simulates real attacker behavior
- Detects runtime vulnerabilities
- Technology independent
- Useful for production-like environments
- Easy integration into CI/CD pipelines

---

# ⚠️ Limitations of DAST

- Cannot identify the exact vulnerable code
- May produce false positives
- Requires a running application
- Limited visibility into business logic vulnerabilities
- Slower than SAST for large applications

> **Key Insight:**  
> *DAST shows the symptoms of vulnerabilities, not their root causes.*

---

# 🧰 Popular DAST Tools

## 🔓 Open Source

### OWASP ZAP

- Free and open source
- Beginner-friendly
- Supports automation
- Active community support

---

### Nikto

- Lightweight web server scanner
- Performs basic security checks
- Detects outdated software
- Easy to use

---

## 💼 Commercial Tools

### Burp Suite Professional

- Industry standard
- Excellent for manual testing
- Powerful scanner
- Highly customizable

---

### Acunetix

- Fast automated scanning
- Good reporting
- API testing support

---

### Invicti (formerly Netsparker)

- High accuracy
- Low false positives
- Enterprise-ready

---

### IBM AppScan / Checkmarx

Enterprise-grade solutions offering:

- DAST
- Compliance reporting
- CI/CD integration
- Large-scale scanning

> **Key Insight:**  
> *OWASP ZAP is excellent for learning, while Burp Suite is widely used by professional penetration testers.*

---

# 🚀 Modern Usage

## DevSecOps Integration

```text
Developer

↓

Commit Code

↓

Build Application

↓

Deploy to Test Environment

↓

DAST Scan

↓

Security Report

↓

Fix Vulnerabilities

↓

Deploy to Production
```

---

## Common Use Cases

- Pre-production security testing
- Continuous security monitoring
- Compliance validation
- CI/CD automation
- API security testing

---

# 🎯 Key Takeaways

- Applications may function correctly while still being vulnerable.
- DAST tests applications from an attacker's perspective.
- It requires a running application but not the source code.
- DAST plays a vital role in modern DevSecOps pipelines.
- Automated tools improve efficiency, but understanding security concepts remains essential.

---

# 🚀 Next Steps

After completing this module, continue with:

## 📖 OWASP ZAP

- Installation
- Architecture
- User Interface
- Proxy Configuration
- Spidering
- Active Scanning
- Reporting

---

## 🔬 Hands-on Labs

- SQL Injection Testing
- XSS Testing
- Authentication Testing
- Session Management Testing
- DAST Automation

---

# 💡 Final Note

> **"Security is not about how your application works — it is about how it behaves under attack."**
