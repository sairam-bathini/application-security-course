# 🔐 Snyk Architecture Explained

## 🎯 What is Snyk?

Snyk is a **Developer Security Platform** that helps identify and fix vulnerabilities in:

* Open Source Dependencies (SCA)
* Source Code (SAST)
* Containers
* Infrastructure as Code (IaC)

---

# 🏗️ High-Level Snyk Architecture

```text
                ┌─────────────────┐
                │  Snyk Cloud     │
                │ Vulnerability DB│
                └────────┬────────┘
                         │
                         │
       ┌─────────────────┼─────────────────┐
       │                 │                 │
       ▼                 ▼                 ▼

   GitHub           Jenkins CI/CD      Developer Laptop
   Repository         Pipeline            Snyk CLI

       │                 │                 │
       └─────────────────┼─────────────────┘
                         │
                         ▼

               Dependency Analysis
               Code Analysis
               Container Analysis
               IaC Analysis

                         │
                         ▼

                 Security Results

                         │
                         ▼

             Fix Recommendations
```

---

# 🧠 Core Components of Snyk

## 1️⃣ Snyk Cloud Platform

The Snyk Cloud Platform acts as the central intelligence engine.

### Responsibilities

* Stores vulnerability database
* Maps packages to CVEs
* Generates reports
* Provides remediation advice

### Think of it as

> The security intelligence engine.

---

## 2️⃣ Snyk Vulnerability Database

Contains vulnerability intelligence for:

```text
Spring Framework
Log4j
Jackson
Apache Commons
NPM Packages
Python Packages
Docker Images
```

### Example

```text
log4j-core 2.14.0
↓
CVE-2021-44228
(Log4Shell)
```

Snyk immediately detects the risk and recommends a fix.

---

## 3️⃣ Snyk CLI

Installed on:

* Developer machines
* Jenkins servers
* Build agents

### Example

```bash
snyk test
```

### Purpose

* Scan project
* Send metadata to Snyk Cloud
* Receive vulnerability results

---

# 🔄 Dependency Scanning Flow (SCA)

Software Composition Analysis (SCA) is one of the primary use cases of Snyk.

```text
pom.xml
package.json
requirements.txt

        │
        ▼

    Snyk CLI

        │
        ▼

 Dependency Tree Creation

        │
        ▼

 Snyk Vulnerability Database

        │
        ▼

 Vulnerability Match

        │
        ▼

 Security Report
```

---

# 📦 Example Using a Maven Project

Suppose the project contains:

```xml
<dependency>
    <groupId>org.apache.logging.log4j</groupId>
    <artifactId>log4j-core</artifactId>
    <version>2.14.0</version>
</dependency>
```

### Step 1

Read:

```text
pom.xml
```

### Step 2

Build dependency graph:

```text
Project
 └── log4j-core
      └── log4j-api
```

### Step 3

Check vulnerability database:

```text
log4j-core 2.14.0
```

### Step 4

Find matching vulnerability:

```text
CVE-2021-44228
(Log4Shell)
```

### Step 5

Provide remediation advice:

```text
Critical Severity
Upgrade to 2.17.1
```

---

# 🏗️ Jenkins + Snyk Architecture

```text
Developer
    │
    ▼
 GitHub
    │
    ▼
 Jenkins
    │
 ┌──┴─────────────┐
 ▼                ▼

SonarQube       Snyk

(SAST)          (SCA)

 │                │
 └──────┬─────────┘
        ▼

 Security Report
```

---

# 🐳 Container Security Architecture

Snyk can scan Docker images and identify vulnerable packages.

```text
Dockerfile
     │
     ▼
 Docker Image
     │
     ▼
 Snyk Container Scan
     │
     ▼
 Vulnerable Packages
     │
     ▼
 Remediation Advice
```

### Example

```text
Ubuntu Image
      │
      ▼
 OpenSSL Vulnerability
```

Snyk identifies the issue and recommends fixes.

---

# ☁️ Infrastructure as Code (IaC) Architecture

Snyk scans:

```text
Terraform
CloudFormation
Kubernetes YAML
```

### Example

```yaml
security_group:
  ingress:
    - 0.0.0.0/0
```

### Detection

```text
Security Misconfiguration
Public Exposure Detected
```

---

# 🔥 Complete Snyk Architecture

```text
                     Snyk Cloud
                     (CVE Database)
                            ▲
                            │
                            │
        ┌───────────────────┼───────────────────┐
        │                   │                   │
        ▼                   ▼                   ▼

   Developer CLI      GitHub Integration   Jenkins Pipeline

        │                   │                   │
        └───────────────────┼───────────────────┘
                            │
                            ▼

         ┌───────────────────────────────┐
         │   Open Source Dependencies    │
         │   Source Code                 │
         │   Containers                  │
         │   Infrastructure as Code      │
         └───────────────────────────────┘

                            │
                            ▼

                  Security Findings

                            │
                            ▼

                 Fix Recommendations
```

---

# 📚 Key Concepts

| Concept         | Description                                               |
| --------------- | --------------------------------------------------------- |
| SAST            | Static Application Security Testing                       |
| SCA             | Software Composition Analysis                             |
| CVE             | Common Vulnerabilities and Exposures                      |
| IaC             | Infrastructure as Code                                    |
| Dependency Tree | Hierarchical structure of packages used by an application |

---

# 🎓 Snyk vs SonarQube

| Feature                      | SonarQube   | Snyk         |
| ---------------------------- | ----------- | ------------ |
| Focus                        | Source Code | Dependencies |
| Security Testing Type        | SAST        | SCA          |
| Detects SQL Injection        | ✅           | ❌            |
| Detects Vulnerable Libraries | ❌           | ✅            |
| Detects Code Smells          | ✅           | ❌            |
| Detects CVEs                 | ❌           | ✅            |

---

# 💡 One-Line Summary

**SonarQube checks the code you write, while Snyk checks the software and libraries you depend on. Snyk continuously compares your application's dependencies, containers, and infrastructure against known vulnerabilities and provides remediation guidance.**
