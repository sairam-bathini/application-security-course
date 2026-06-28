# GitHub for Application Security Engineers

# Learning Objectives

After completing this course, students will be able to:

- Understand Git and GitHub fundamentals
- Work with repositories and branches
- Create and review Pull Requests
- Automate workflows using GitHub Actions
- Secure secrets using GitHub Secrets
- Detect exposed credentials with Secret Scanning
- Manage vulnerable dependencies using Dependabot
- Perform static code analysis using CodeQL
- Protect production branches
- Understand GitHub Security features
- Build a complete DevSecOps pipeline

---

# Module 1 - Introduction to Git

## What is Git?

Imagine five developers working on the same application.

Without Git:

```text
App_Final.zip
App_Final_New.zip
App_Final_New2.zip
App_Final_Latest.zip
App_Final_Latest_Updated.zip
```

Very confusing!

Git solves this problem.

**Git** is a **Version Control System (VCS)**.

It tracks:

- File changes
- Code history
- Contributors
- Versions

---

## Why Git?

Git allows developers to:

- Save project history
- Roll back changes
- Collaborate efficiently
- Compare versions
- Merge code safely

---

# Git vs GitHub

| Git | GitHub |
|------|---------|
| Version Control Tool | Cloud Platform |
| Installed Locally | Repository Hosting |
| Tracks Code Changes | Stores Git Repositories |
| Command Line Tool | Web Interface |

### Simple Analogy

- **Git = Microsoft Word**
- **GitHub = Google Drive**

Git manages your code history.

GitHub stores and shares it.

---

# Module 2 - GitHub Repository

## What is a Repository?

A Repository contains:

```text
Source Code
README
Documentation
Images
Git History
Branches
Issues
Pull Requests
Actions
Security
```

---

## Repository Structure

```text
project/

│── .github/
│── src/
│── tests/
│── README.md
│── LICENSE
│── requirements.txt
```

---

## README.md

A recruiter usually opens the README first.

A good README should include:

- Project Overview
- Features
- Installation Steps
- Usage
- Architecture
- Screenshots
- Security Features
- Known Issues

---

## Commits

A **Commit** represents a saved snapshot of your project.

Good commit messages:

```text
Fix SQL Injection in Login API

Remove hardcoded AWS key

Update authentication logic
```

Poor commit messages:

```text
Update

Changes

Fix
```

---

# Module 3 - Branches

Instead of directly modifying production code, developers work in separate branches.

Example:

```text
main

feature/login

feature/payment

bugfix/cart

security/remove-secrets
```

Workflow:

```text
main
   │
   ├── feature/login
   │
   └── Merge
        │
      main
```

---

# Pull Requests (PR)

A Pull Request is a request to merge code.

Workflow:

```text
Create Branch

↓

Write Code

↓

Commit

↓

Push

↓

Open Pull Request

↓

Review

↓

Approve

↓

Merge
```

Application Security Engineers review:

- Secure coding
- Hardcoded secrets
- Vulnerabilities
- Code quality

---

# Module 4 - GitHub Actions

## What are GitHub Actions?

GitHub Actions automate software development workflows.

Without Actions:

Developers manually perform:

- Build
- Testing
- Security Scan
- Deployment

With Actions:

Everything happens automatically.

Workflow:

```text
Push Code

↓

GitHub Actions

↓

Build

↓

Unit Test

↓

SAST

↓

Secret Scan

↓

Dependency Scan

↓

Deploy
```

---

## Workflow File Location

```text
.github/workflows/
```

Example:

```text
.github/workflows/security.yml
```

---

## Workflow Structure

```yaml
name:

on:

jobs:

steps:
```

---

## Example Workflow

```yaml
name: Hello World

on:
  push:

jobs:
  demo:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - run: echo "Hello Students"
```

Explain every line to students.

---

## Real DevSecOps Pipeline

```text
Developer Push

↓

Checkout Code

↓

Install Dependencies

↓

Run Unit Tests

↓

Run SonarQube

↓

Run Snyk

↓

Run Secret Scan

↓

Generate Report
```

---

# Module 5 - GitHub Secrets

Never store:

- Passwords
- API Keys
- Tokens
- AWS Credentials
- Azure Credentials

Instead use:

```
Repository

↓

Settings

↓

Secrets and Variables

↓

Actions

↓

New Repository Secret
```

Examples:

```text
SONAR_TOKEN

SNYK_TOKEN

AWS_ACCESS_KEY

AWS_SECRET_KEY
```

Usage:

```yaml
${{ secrets.SONAR_TOKEN }}
```

---

# Module 6 - GitHub Secret Scanning

Secret Scanning automatically detects exposed credentials.

Example:

```python
AWS_SECRET_KEY="ABCD123456"

GITHUB_TOKEN="ghp_xxxxxxxxx"
```

GitHub detects:

- AWS Keys
- Azure Keys
- Google Cloud Keys
- GitHub Tokens
- Slack Tokens
- Stripe Keys
- Twilio Tokens
- OpenAI API Keys
- Many more

---

## Push Protection

Workflow:

```text
Developer Pushes Secret

↓

GitHub Blocks Push

↓

Developer Removes Secret

↓

Push Allowed
```

---

# Module 7 - Dependabot

Dependabot detects vulnerable libraries.

Example:

```text
requests==2.21

↓

Known CVE Found

↓

Upgrade Suggested

↓

requests==2.32
```

Dependabot automatically:

- Detects vulnerable packages
- Creates alerts
- Opens Pull Requests
- Suggests secure versions

---

# Module 8 - Code Scanning (CodeQL)

GitHub uses **CodeQL** for Static Application Security Testing (SAST).

It detects:

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection
- SSRF
- Path Traversal
- Hardcoded Passwords
- Insecure Deserialization
- Other security issues

Workflow:

```text
Developer Push

↓

GitHub Action

↓

CodeQL Scan

↓

Security Report

↓

Developer Fixes Issues
```

---

# Module 9 - GitHub Security Tab

The Security tab contains:

- Code Scanning Alerts
- Secret Scanning Alerts
- Dependabot Alerts
- Security Advisories
- Security Policy

Students should become familiar with navigating this dashboard.

---

# Module 10 - Branch Protection Rules

Protect the `main` branch.

Recommended rules:

- Require Pull Requests
- Require Code Reviews
- Require Status Checks
- Require Security Scans
- Block Direct Pushes

Only allow merge when:

- Unit Tests Pass
- SonarQube Passes
- Snyk Passes
- CodeQL Passes
- Secret Scan Passes

---

# End-to-End DevSecOps Architecture

```text
Developer

↓

VS Code

↓

Git

↓

GitHub Repository

↓

GitHub Actions

↓

SonarQube

↓

Snyk

↓

Secret Scanning

↓

Dependabot

↓

CodeQL

↓

Security Report

↓

Merge Pull Request
```

---

# Hands-on Labs

## Lab 1

Create a GitHub account

- Create Repository
- Clone Repository
- Commit Changes
- Push Code

---

## Lab 2

Branching

- Create Branch
- Modify README
- Commit
- Create Pull Request
- Merge

---

## Lab 3

GitHub Actions

- Create Workflow
- Print Hello World

---

## Lab 4

Python Workflow

- Install Dependencies
- Run Unit Tests

---

## Lab 5

GitHub Secrets

- Store Snyk Token
- Store SonarQube Token
- Access Secret inside Workflow

---

## Lab 6

Secret Scanning

- Commit Fake Secret
- Observe Alert
- Remove Secret

---

## Lab 7

Dependabot

- Enable Dependabot
- Introduce Vulnerable Package
- Observe Alert
- Merge Update PR

---

## Lab 8

CodeQL

- Enable CodeQL
- Introduce SQL Injection
- View Security Alerts

---

## Lab 9

Branch Protection

- Enable Protection Rules
- Require Pull Request
- Require Security Checks
- Verify Protected Merge

---

# Final Capstone Project

Build a deliberately vulnerable **Python Flask** application.

The application should contain:

- SQL Injection
- Cross-Site Scripting (XSS)
- Hardcoded API Keys
- Vulnerable Dependencies
- Weak Input Validation

Students will then:

1. Push the project to GitHub.
2. Configure GitHub Actions.
3. Run automated tests.
4. Integrate SonarQube.
5. Integrate Snyk.
6. Enable GitHub CodeQL.
7. Enable Dependabot.
8. Enable Secret Scanning.
9. Store secrets using GitHub Secrets.
10. Configure Branch Protection.
11. Fix vulnerabilities.
12. Merge the Pull Request after all security checks pass.

---

# Course Outcome

By the end of this training, students will understand how GitHub fits into a modern DevSecOps pipeline and how Application Security Engineers use GitHub to:

- Collaborate securely
- Automate security testing
- Detect vulnerabilities
- Protect secrets
- Secure software supply chains
- Enforce secure development practices
- Deliver safer applications to production
