# 📘 OWASP ZAP – Hands-on Guide & DAST Automation

> Learn how to use **OWASP ZAP (Zed Attack Proxy)** to perform Dynamic Application Security Testing (DAST), manually test web applications, and automate security scans using GitHub Actions.

> **Prerequisite:** Complete the **DAST Fundamentals** module before starting this guide.

---

# 📑 Table of Contents

* [Introduction](#-introduction)
* [Why OWASP ZAP?](#-why-owasp-zap)
* [OWASP ZAP Architecture](#-owasp-zap-architecture)
* [Installation & Setup](#-installation--setup)
* [Configuring Browser Proxy](#-configuring-browser-proxy)
* [OWASP ZAP Interface](#-owasp-zap-interface)
* [Typical ZAP Workflow](#-typical-zap-workflow)
* [Spidering](#-spidering)
* [Passive Scanning](#-passive-scanning)
* [Active Scanning](#-active-scanning)
* [Manual Security Testing](#-manual-security-testing)
* [Understanding Alerts](#-understanding-alerts)
* [Testing OWASP Juice Shop](#-testing-owasp-juice-shop)
* [DAST Automation with GitHub Actions](#-dast-automation-with-github-actions)
* [Common Issues](#-common-issues)
* [Best Practices](#-best-practices)
* [Key Takeaways](#-key-takeaways)

---

# 🚀 Introduction

**OWASP ZAP (Zed Attack Proxy)** is one of the world's most popular open-source web application security testing tools.

It sits between your browser and the target application, allowing you to:

* Capture HTTP/HTTPS requests
* Modify requests and responses
* Discover hidden endpoints
* Perform automated security scans
* Conduct manual penetration testing

---

# ❓ Why OWASP ZAP?

Without ZAP:

* Limited visibility into HTTP traffic
* Difficult to understand application behavior
* Manual security testing becomes harder

With ZAP:

* Intercept requests and responses
* Modify parameters before they reach the server
* Automatically discover pages
* Identify security vulnerabilities
* Generate professional security reports

---

# 🏗️ OWASP ZAP Architecture

## Core Components

### 1. Proxy

The Proxy is the heart of OWASP ZAP.

Responsibilities:

* Intercepts browser traffic
* Captures requests
* Allows request modification
* Forwards traffic to the web server

Default configuration:

| Setting | Value     |
| ------- | --------- |
| Host    | 127.0.0.1 |
| Port    | 8080      |

---

### 2. Spider

The Spider automatically explores the application.

It discovers:

* Pages
* Links
* Forms
* Hidden URLs
* API endpoints

---

### 3. Passive Scanner

The Passive Scanner analyzes captured traffic without sending attack payloads.

Common findings include:

* Missing Security Headers
* Information Disclosure
* Cookie Security Issues
* Server Information Leakage

---

### 4. Active Scanner

The Active Scanner sends attack payloads to identify vulnerabilities.

Examples:

* SQL Injection
* Cross-Site Scripting (XSS)
* Command Injection
* Path Traversal
* Server Misconfigurations

> **Warning:** Only run Active Scans against applications you own or are authorized to test.

---

# 🔄 ZAP Architecture Flow

```text
Browser
    │
    ▼
OWASP ZAP Proxy
    │
    ▼
Web Application
    │
    ▼
Captured Traffic
    │
 ┌─────────────┐
 │ Passive Scan│
 └─────────────┘
        │
        ▼
     Spider
        │
        ▼
  Active Scanner
        │
        ▼
 Security Report
```

---

# ⚙️ Installation & Setup

## Step 1 – Install OWASP ZAP

Download and install the latest version of OWASP ZAP from the official website.

---

## Step 2 – Launch ZAP

Open the application.

You will be prompted to:

* Create a new session
* Continue with an existing session

Choose **Persist Session** if you want to save your work.

---

# 🌐 Configuring Browser Proxy

Configure your browser to use ZAP as its proxy.

| Setting | Value     |
| ------- | --------- |
| Host    | 127.0.0.1 |
| Port    | 8080      |

After configuration:

```
Browser
      ↓
OWASP ZAP
      ↓
Target Website
```

Open any website and verify that requests appear inside the **Sites Tree**.

---

# 🖥️ OWASP ZAP Interface

## Sites Tree

Displays:

* Domains
* URLs
* API endpoints

---

## History Tab

Shows every captured HTTP request.

Useful for:

* Reviewing requests
* Replaying requests
* Manual testing

---

## Request / Response Panel

Displays:

* Request headers
* Request body
* Response headers
* Response body

You can edit requests before sending them.

---

## Alerts Tab

Lists all detected vulnerabilities.

Each alert contains:

* Severity
* Risk
* Description
* Evidence
* Recommendation

---

## Quick Start

Provides quick options for:

* Automated Scan
* Manual Explore
* API Scan

---

# 🔄 Typical ZAP Workflow

```text
Configure Proxy

↓

Browse Application

↓

Capture Requests

↓

Spider Application

↓

Passive Scan

↓

Active Scan

↓

Review Alerts

↓

Manual Verification
```

---

# 🕷️ Spidering

The Spider automatically discovers application content.

To run:

```
Target Site

↓

Right Click

↓

Attack

↓

Spider
```

Spidering helps uncover:

* Hidden pages
* Parameters
* Forms
* API endpoints

---

# 🔎 Passive Scanning

Passive Scanning runs automatically while browsing.

No attack traffic is generated.

Typical findings include:

* Missing CSP Header
* Missing X-Frame-Options
* Cookie Missing HttpOnly
* Missing Secure Cookie Flag

---

# 💣 Active Scanning

To launch:

```
Right Click Target

↓

Attack

↓

Active Scan
```

The scanner injects attack payloads to identify security vulnerabilities.

Typical findings:

* SQL Injection
* Cross-Site Scripting
* Command Injection
* Path Traversal

---

# 🧪 Manual Security Testing

Manual testing helps validate findings and identify vulnerabilities that automated scanners may miss.

Common activities:

## Modify Requests

Example:

```http
POST /login

username=admin
password=123
```

Modify:

```http
password=wrongpassword
```

Observe the server response.

---

## Replay Requests

Use **Resend** to:

* Repeat requests
* Modify parameters
* Test edge cases

---

## Example: IDOR Testing

Original request:

```text
GET /profile?user_id=100
```

Modify:

```text
GET /profile?user_id=101
```

Then:

```text
GET /profile?user_id=102
```

Observe whether unauthorized data is accessible.

---

# 📊 Understanding Alerts

Each alert includes:

* Alert Name
* Risk Level
* Confidence
* Description
* Evidence
* Solution
* References

Always validate alerts manually before reporting them.

---

# 🧪 Testing OWASP Juice Shop

OWASP Juice Shop is intentionally vulnerable and ideal for learning.

Suggested workflow:

```
Start Juice Shop

↓

Configure Browser Proxy

↓

Browse Application

↓

Spider

↓

Passive Scan

↓

Active Scan

↓

Review Findings

↓

Manual Verification
```

---

# 🚀 DAST Automation with GitHub Actions

## Project Structure

```text
.github/
└── workflows/
    └── zap-dast-scan.yml
```

---

## Baseline Scan (Recommended)

```yaml
name: ZAP DAST Scan - Juice Shop

on:
  push:
    branches: [ main ]

  pull_request:

jobs:
  zap_scan:

    runs-on: ubuntu-latest

    steps:

    - uses: actions/checkout@v4

    - name: Start Juice Shop
      run: docker run -d -p 3000:3000 bkimminich/juice-shop

    - name: Wait
      run: sleep 20

    - name: Run Baseline Scan
      uses: zaproxy/action-baseline@v0.12.0
      with:
        target: 'http://localhost:3000'
        cmd_options: '-a'

    - name: Upload Report
      uses: actions/upload-artifact@v4
      with:
        name: zap-report
        path: report_html.html
```

---

## Full Scan (Advanced)

```yaml
name: ZAP Full Scan

on:
  workflow_dispatch:

jobs:

  full_scan:

    runs-on: ubuntu-latest

    steps:

    - uses: actions/checkout@v4

    - name: Start Juice Shop
      run: docker run -d -p 3000:3000 bkimminich/juice-shop

    - name: Wait
      run: sleep 30

    - name: Run Full Scan
      uses: zaproxy/action-full-scan@v0.10.0
      with:
        target: 'http://localhost:3000'

    - name: Upload Report
      uses: actions/upload-artifact@v4
      with:
        name: zap-full-report
        path: report_html.html
```

---

# ⚠️ Common Issues

| Problem               | Solution                                         |
| --------------------- | ------------------------------------------------ |
| No traffic captured   | Verify browser proxy settings                    |
| HTTPS errors          | Install the ZAP Root CA Certificate              |
| Active Scan fails     | Ensure the application is fully loaded           |
| Spider finds few URLs | Browse the application manually before spidering |
| GitHub Action fails   | Increase the startup wait time for Juice Shop    |

---

# ✅ Best Practices

* Perform Passive Scans before Active Scans.
* Never run Active Scans against production systems.
* Validate all findings manually.
* Use Juice Shop or other intentionally vulnerable applications for learning.
* Integrate ZAP into CI/CD pipelines for continuous security testing.
* Combine ZAP with SAST tools such as SonarQube or Snyk for broader security coverage.

---

# 🎯 Key Takeaways

* OWASP ZAP is one of the most widely used open-source DAST tools.
* The Proxy is the core component of ZAP.
* Spidering discovers application content automatically.
* Passive Scanning is safe and non-intrusive.
* Active Scanning performs automated security attacks.
* Manual testing is essential for validating automated findings.
* GitHub Actions can automate ZAP scans as part of a DevSecOps pipeline.
* OWASP Juice Shop is an excellent practice target for learning web application security.
