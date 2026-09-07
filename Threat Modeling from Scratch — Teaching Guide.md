# Threat Modeling from Scratch — Teaching Guide

## Overview

Threat modeling should not be taught by starting with STRIDE, PASTA, or threat-modeling templates.

A student should first understand:

1. What an application is
2. How applications are designed
3. What application architecture means
4. How application components communicate
5. How data flows through an application
6. Authentication and authorization
7. Trust boundaries
8. Attack surface
9. Threats
10. Risk
11. Security controls

The learning journey should be:

```text
Application Fundamentals
        ↓
Application Design
        ↓
Application Architecture
        ↓
Components & Communication
        ↓
Data Flow
        ↓
Authentication & Authorization
        ↓
Trust Boundaries
        ↓
Attack Surface
        ↓
Threat Modeling
        ↓
STRIDE
        ↓
Risk & Mitigation
```

The key principle is:

> **Don't teach students how to fill a threat-modeling template. Teach them how to look at an architecture and ask: "How can this system be abused?"**

---

# 1. Application Fundamentals

Before teaching threat modeling, explain what an application actually is.

Use a familiar example such as a food-delivery application.

### Example: Food Delivery Application

Users should be able to:

- Register
- Login
- Browse restaurants
- View menus
- Add food to cart
- Place orders
- Make payments
- Track orders

Explain that these are **business requirements and application features**.

At this stage, do not introduce security concepts.

The goal is to understand:

> "What are we trying to build?"

---

# 2. From Business Requirements to Technical Components

Once the student understands the application requirements, ask:

> "What technical components do we need to build this application?"

A simple architecture could be:

```text
                  Food Delivery Application
                           |
          +----------------+----------------+
          |                |                |
          ↓                ↓                ↓
       Frontend           API            Database
                           |
              +------------+------------+
              |            |            |
              ↓            ↓            ↓
         User Service  Order Service  Payment Service
```

Explain that an application is usually made up of multiple components that perform different responsibilities.

---

# 3. What Is Application Architecture?

Explain:

> **Application architecture describes the major components of an application, their responsibilities, how they communicate, and how data flows between them.**

Start with a very simple architecture:

```text
User
  ↓
Frontend
  ↓
Backend / API
  ↓
Database
```

Then explain each component.

### Frontend

The part of the application that the user interacts with.

Examples:

- Web application
- Mobile application

### Backend

The server-side component responsible for business logic.

Examples:

- Login
- Order creation
- Payment processing
- Business rules

### API

The interface through which different components communicate.

Examples:

```http
POST /login
GET /restaurants
POST /orders
GET /orders/123
```

### Database

Stores application data.

For example:

```text
Users
Restaurants
Orders
Payments
```

---

# 4. Understand the Request and Response Flow

This is one of the most important concepts before starting threat modeling.

Consider a login process:

```text
User
  ↓
Login Page
  ↓
POST /login
  ↓
Backend
  ↓
Database
```

Example request:

```http
POST /login

{
  "username": "sai",
  "password": "********"
}
```

The backend might perform:

```text
1. Receive request
2. Validate input
3. Find the user
4. Verify password
5. Create session/token
6. Return response
```

The response could be:

```text
Backend
  ↓
200 OK
  +
Authentication Token
  ↓
User
```

The student should understand that an application is essentially processing:

```text
Input
  ↓
Processing
  ↓
Data Access
  ↓
Response
```

This becomes extremely important when identifying threats.

---

# 5. Authentication and Authorization

Before threat modeling, the student must understand identity and access.

## Authentication

Authentication answers:

> **"Who are you?"**

Example:

```text
Username + Password
        ↓
Authentication
        ↓
User = Sairam
```

Other authentication mechanisms include:

- MFA
- OAuth
- OIDC
- Certificates
- API keys
- Tokens

## Authorization

Authorization answers:

> **"What are you allowed to do?"**

Example:

```text
Normal User
    |
    +---- View own orders       ✅
    |
    +---- View all users        ❌
    |
    +---- Delete users          ❌
    |
    +---- Access admin panel    ❌
```

A student should understand:

```text
Authentication → Who are you?

Authorization → What are you allowed to do?
```

---

# 6. Understanding Data

Consider a simple database:

```text
Users

ID    Name     Email
-------------------------
101   Sai      sai@example.com
102   Ravi     ravi@example.com
```

Suppose the API provides:

```http
GET /api/users/101
```

Now ask the student:

> "How does the application know whether the current user is allowed to access User 101?"

This introduces authorization.

Then ask:

> "What happens if the user changes 101 to 102?"

```http
GET /api/users/102
```

If User 101 can access User 102's information, there is an authorization problem.

This is a good point to later introduce concepts such as:

- BOLA
- IDOR
- Broken Access Control

The student should discover the problem before being given the vulnerability name.

---

# 7. Understanding Trust

Now introduce the concept of trust.

Ask:

> "Do we completely trust the user's browser?"

No.

> "Do we completely trust the Internet?"

No.

> "Do we trust our internal backend more than the Internet?"

Yes.

This leads to the concept of **trust boundaries**.

Example:

```text
                 UNTRUSTED
                     |
                  Internet
                     |
            ---- Trust Boundary ----
                     |
                     ↓
                Frontend/API
                     |
            ---- Trust Boundary ----
                     |
                     ↓
              Backend Services
                     |
            ---- Trust Boundary ----
                     |
                     ↓
                  Database
```

Explain:

> **A trust boundary represents a transition between different trust levels or security domains.**

Important rule:

> **Whenever data or control crosses a trust boundary, ask what could go wrong.**

---

# 8. Data Flow Diagrams

Once the student understands components, communication, data, and trust, introduce the Data Flow Diagram (DFD).

Example:

```text
             [User]
                |
                | Login Request
                ↓
        [Web Application]
                |
                | HTTPS
                ↓
            [Auth API]
                |
                | Database Query
                ↓
            [User DB]
```

Explain the main DFD elements.

### External Entity

Something outside the system interacting with it.

Example:

```text
User
```

### Process

A component that processes data.

Examples:

```text
Web Application
Auth API
Order Service
Payment Service
```

### Data Store

Where data is stored.

Examples:

```text
User Database
Order Database
Vector Database
Object Storage
```

### Data Flow

Data moving between components.

Examples:

```text
Login Request
Authentication Token
Customer Information
Payment Information
Order Details
```

### Trust Boundary

A boundary between different trust levels.

---

# 9. Attack Surface

Now ask:

> **"If I am an attacker, what can I interact with?"**

The student might identify:

```text
Login API
Registration API
Order API
Payment API
Admin API
File Upload
Web Interface
Mobile API
```

Introduce:

> **Attack surface is the collection of exposed or reachable entry points, interfaces, components, and paths that could potentially be abused by an attacker.**

Example:

```text
                 Internet
                    |
        +-----------+-----------+
        |           |           |
        ↓           ↓           ↓
      Login       Order      File Upload
       API          API          API
        |           |           |
        +-----------+-----------+
                    |
                 Backend
```

Each exposed interface should become a potential area of investigation.

---

# 10. Now Introduce Threat Modeling

Only after the student understands the application should you introduce threat modeling.

Tell the student:

> **"Until now, we were understanding how the application works. Threat modeling starts when we ask: How can this design be abused?"**

The basic process is:

```text
System
   ↓
Assets
   ↓
Actors
   ↓
Data Flows
   ↓
Trust Boundaries
   ↓
Attack Surface
   ↓
Threats
   ↓
Risk
   ↓
Security Requirements
   ↓
Security Controls
   ↓
Residual Risk
```

---

# 11. Identify Assets

Ask:

> **"What are we trying to protect?"**

Possible assets:

- Passwords
- Authentication tokens
- Customer information
- Payment information
- Orders
- Business data
- Source code
- Secrets
- Personal information

Then ask:

> "Which assets are most valuable?"

This introduces asset criticality and impact.

---

# 12. Identify Actors

Ask:

> **"Who can interact with this system?"**

Possible actors:

```text
Customer
Admin
Support Employee
Developer
Third-Party Service
Attacker
System Service
```

Then ask:

> "Should all actors have the same permissions?"

This naturally leads into:

- Authentication
- Authorization
- RBAC
- Least privilege

---

# 13. Identify Data Flows

Ask:

> **"How does data move through the system?"**

Example:

```text
Customer
   ↓
Frontend
   ↓
API Gateway
   ↓
Order Service
   ↓
Order Database
```

Then identify what data moves:

```text
Customer → Login Credentials
Frontend → API → Order Details
API → Database → Customer Information
Payment Service → API → Payment Status
```

---

# 14. Identify Trust Boundaries

Ask:

> "Where does the data move from one trust level to another?"

Example:

```text
Internet
   |
   | Trust Boundary
   ↓
API Gateway
   |
   | Trust Boundary
   ↓
Internal Services
   |
   | Trust Boundary
   ↓
Database
```

For each boundary ask:

> **"What assumptions are we making about the data crossing this boundary?"**

---

# 15. Identify Threats

Now ask:

> **"If I am an attacker, what can go wrong?"**

Take a login API.

Ask:

### Spoofing

> Can an attacker pretend to be another user?

Potential threats:

- Credential theft
- Session theft
- Token theft

### Tampering

> Can an attacker modify a request or data?

Example:

```http
POST /transfer

{
  "amount": 100
}
```

What if the attacker changes it to:

```json
{
  "amount": 100000
}
```

### Information Disclosure

> Can an attacker access information they should not see?

Example:

```http
GET /users/102
```

when the attacker should only access their own data.

### Denial of Service

> Can an attacker make the service unavailable?

Examples:

- Request flooding
- Resource exhaustion
- Expensive operations

### Elevation of Privilege

> Can a normal user obtain administrative privileges?

Example:

```text
Normal User
     ↓
Privilege Escalation
     ↓
Admin
```

---

# 16. STRIDE

Once the student understands threats, introduce STRIDE as a systematic checklist.

| STRIDE | Question |
|---|---|
| S — Spoofing | Can someone pretend to be someone else? |
| T — Tampering | Can someone modify data or requests? |
| R — Repudiation | Can someone deny performing an action? |
| I — Information Disclosure | Can someone access information they should not see? |
| D — Denial of Service | Can someone make the service unavailable? |
| E — Elevation of Privilege | Can someone gain privileges they should not have? |

The key teaching point:

> **STRIDE is a checklist, not the definition of threat modeling.**

Do not make students memorize six definitions.

Make them ask six questions.

---

# 17. Threat vs Vulnerability vs Risk

These concepts must be clearly separated.

### Threat

Something that could cause harm.

Example:

```text
Attacker accesses another user's account.
```

### Vulnerability

A weakness that makes the threat possible.

Example:

```text
Missing authorization check.
```

### Risk

The potential business/security impact resulting from a threat exploiting a weakness.

A simplified model:

```text
Risk ≈ Likelihood × Impact
```

Example:

```text
Asset:
Customer Data

Threat:
Unauthorized access

Vulnerability:
Missing object-level authorization

Likelihood:
High

Impact:
High

Risk:
High
```

---

# 18. Threat → Risk → Control

This is where threat modeling becomes useful for Product Security.

Example:

### Threat

User A accesses User B's order.

### Asset

Customer order information.

### Vulnerability

Missing object-level authorization.

### Impact

Unauthorized access to sensitive customer information.

### Risk

High risk of data exposure.

### Security Control

Implement object-level authorization.

### Validation

Test the API using different user identities.

### Monitoring

Log and alert on suspicious unauthorized access attempts.

The complete chain becomes:

```text
Threat
   ↓
Vulnerability
   ↓
Likelihood + Impact
   ↓
Risk
   ↓
Security Requirement
   ↓
Security Control
   ↓
Security Testing
   ↓
Monitoring
```

---

# 19. The Five-Question Threat Modeling Technique

Whenever the student gets stuck, use these five questions.

### Question 1

> **What are we protecting?**

→ Assets

### Question 2

> **Who can interact with it?**

→ Actors

### Question 3

> **What can an attacker control?**

→ Inputs, requests, identities, data, actions

### Question 4

> **What can go wrong?**

→ Threats

### Question 5

> **How can we reduce the risk?**

→ Security Controls

This can be used against almost any application architecture.

---

# 20. Practical Exercise 1 — Login Application

Start with:

```text
User
 ↓
Frontend
 ↓
API Gateway
 ↓
Authentication Service
 ↓
User Database
```

Ask the student:

### Architecture

1. What are the components?
2. What does each component do?
3. How do the components communicate?

### Data

4. What data is being transmitted?
5. Which data is sensitive?

### Identity

6. Who are the users?
7. What permissions do they have?

### Trust

8. Which components are trusted?
9. Where are the trust boundaries?

### Attack Surface

10. What can an attacker reach?

### Threats

11. What can go wrong?

### Risk

12. Which threats are most dangerous?

### Controls

13. How would you reduce the risks?

Do not give the answers immediately.

Let the student reason through the architecture.

---

# 21. Practical Exercise 2 — E-Commerce Application

Use this architecture:

```text
                Customer
                    |
                    ↓
                Web App
                    |
                    ↓
               API Gateway
              /     |      \
             /      |       \
            ↓       ↓        ↓
        User DB  Order DB  Payment
```

Ask the student to identify:

### Assets

- Customer data
- Order information
- Payment information
- Credentials
- Authentication tokens

### Actors

- Customer
- Admin
- Support staff
- Payment provider
- Attacker

### Attack Surface

- Login API
- Registration API
- Order API
- Payment API
- Admin API

### Trust Boundaries

- Internet → Web Application
- Web Application → API
- API → Internal Services
- Services → Database
- Application → Payment Provider

Then ask:

> "What can an attacker do?"

Do not provide the threats immediately.

---

# 22. Practical Exercise 3 — Microservices

Move to:

```text
User
 ↓
API Gateway
 ↓
+-----------------------+
|                       |
↓                       ↓
User Service       Order Service
|                       |
↓                       ↓
User DB             Order DB
                        |
                        ↓
                  Payment Service
```

Ask:

- Can one service access another service?
- How are services authenticated?
- How are services authorized?
- What happens if one service is compromised?
- Can a compromised service access every database?
- Where are secrets stored?
- What happens if the API Gateway is compromised?
- Can one tenant access another tenant's data?

This introduces:

- Service-to-service authentication
- Service authorization
- Least privilege
- Secrets management
- Lateral movement
- Network segmentation
- Tenant isolation

---

# 23. Practical Exercise 4 — Cloud Application

Example:

```text
Internet
   ↓
WAF
   ↓
Load Balancer
   ↓
Kubernetes
   ↓
Microservices
   ↓
Database
   ↓
Object Storage
```

Ask:

> What happens if the attacker compromises a pod?

Then:

> What can that pod access?

Then:

> What permissions does its service account have?

Then:

> Can it access the Kubernetes API?

Then:

> Can it access secrets?

Then:

> Can it access cloud metadata?

Then:

> Can it access the database?

This naturally introduces:

- IAM
- RBAC
- Network Policies
- Secrets Management
- Container Security
- Kubernetes Security
- Cloud Security
- Lateral Movement

---

# 24. Practical Exercise 5 — AI/RAG Application

This is especially useful for AI Security training.

Architecture:

```text
User
 ↓
AI Application
 ↓
LLM
 ↓
RAG
 ↓
Vector Database
 ↓
Enterprise Documents
```

Ask:

### Scenario 1

> Can User A retrieve User B's documents?

Potential issue:

- Authorization failure
- Tenant isolation failure
- Data leakage

### Scenario 2

> What if an attacker uploads a malicious document?

Potential issue:

- RAG poisoning

### Scenario 3

> What if a malicious prompt attempts to extract system instructions?

Potential issue:

- Prompt injection
- Sensitive information disclosure

### Scenario 4

> What if the AI has access to a file-deletion tool?

Potential issue:

- Excessive agency
- Tool abuse
- Unauthorized actions

This demonstrates that threat modeling applies to new AI architectures as well.

---

# 25. Recommended 12-Day Threat Modeling Learning Path

## Day 1 — Application Fundamentals

Topics:

- What is an application?
- Business requirements
- Functional requirements
- Application features
- Frontend
- Backend
- APIs
- Databases
- Basic request/response flow

---

## Day 2 — Application Architecture

Topics:

- Client-server architecture
- Three-tier architecture
- Monolithic architecture
- Microservices
- Components
- Service-to-service communication
- External services
- Architecture diagrams

---

## Day 3 — Security Fundamentals

Topics:

- Assets
- Actors
- Authentication
- Authorization
- Roles
- Permissions
- Sensitive data
- Trust
- Attack surface

---

## Day 4 — Data Flow and Trust

Topics:

- Data Flow Diagrams
- Processes
- Data stores
- External entities
- Data flows
- Trust boundaries
- Entry points

---

## Day 5 — Threat Modeling Fundamentals

Topics:

- What is threat modeling?
- Why threat modeling?
- Threat vs vulnerability
- Threat vs risk
- Attack scenarios
- Abuse cases
- Security requirements

---

## Day 6 — STRIDE

Topics:

- Spoofing
- Tampering
- Repudiation
- Information Disclosure
- Denial of Service
- Elevation of Privilege

Practice:

- Login system
- E-commerce system

---

## Day 7 — Risk and Mitigation

Topics:

- Likelihood
- Impact
- Risk
- Risk prioritization
- Security requirements
- Security controls
- Residual risk
- Risk acceptance

---

## Day 8 — E-Commerce Threat Model

Complete end-to-end threat model:

```text
Customer
 ↓
Web App
 ↓
API Gateway
 ↓
Microservices
 ↓
Databases
 ↓
Payment Provider
```

---

## Day 9 — API and Microservices Threat Modeling

Topics:

- API attack surface
- Authentication
- Authorization
- BOLA
- Token security
- Rate limiting
- Input validation
- Service-to-service security

---

## Day 10 — Cloud and Kubernetes Threat Modeling

Topics:

- Cloud attack surface
- IAM
- Network boundaries
- Containers
- Kubernetes
- RBAC
- Secrets
- Network policies
- Workload identity

---

## Day 11 — AI Security Threat Modeling

Topics:

- LLM applications
- RAG
- Vector databases
- Prompt injection
- Data leakage
- RAG poisoning
- AI agents
- Tool abuse
- Excessive agency
- Tenant isolation

---

## Day 12 — Architecture Interview

Give the student a completely new architecture.

For example:

> "Design and threat-model a secure online banking application."

The student should independently identify:

```text
Assets
   ↓
Actors
   ↓
Architecture
   ↓
Data Flows
   ↓
Trust Boundaries
   ↓
Attack Surface
   ↓
Threats
   ↓
Risk
   ↓
Security Controls
   ↓
Testing
   ↓
Monitoring
   ↓
Residual Risk
```

---

# 26. How to Teach Each Class

Avoid spending the entire session on slides.

Use this approximate structure:

```text
10%  → Explain concepts
20%  → Draw architecture
30%  → Ask questions
30%  → Attack/defend scenarios
10%  → Summarize
```

The student should spend more time **thinking and drawing** than listening.

---

# 27. Trainer's Questioning Technique

When the student gives an answer, don't immediately say:

> "Correct."

Ask:

> "Why?"

Then:

> "What threat does that address?"

Then:

> "Where would you implement that control?"

Then:

> "How would you validate it?"

Then:

> "How would you monitor it?"

Example:

Student:

> "We should use MFA."

Trainer:

> "Why?"

Student:

> "To protect against credential compromise."

Trainer:

> "Does MFA prevent BOLA?"

Student:

> "No."

Trainer:

> "Why?"

This teaches the student that **one security control does not solve every threat**.

---

# 28. The Architecture-to-Threat-Modeling Mental Model

The student should eventually be able to look at an architecture and mentally walk through:

```text
Business Requirement
        ↓
Application Components
        ↓
Architecture
        ↓
Assets
        ↓
Users / Actors
        ↓
Data Flows
        ↓
Trust Boundaries
        ↓
Entry Points
        ↓
Attack Surface
        ↓
Threats
        ↓
Risk
        ↓
Security Requirements
        ↓
Security Controls
        ↓
Security Testing
        ↓
Monitoring
        ↓
Residual Risk
```

This is the real skill you want to develop.

---

# 29. Product Security Perspective

For Product Security, threat modeling should eventually become part of the Secure SDLC.

```text
Business Requirement
        ↓
Security Requirements
        ↓
Threat Model
        ↓
Architecture Review
        ↓
Security Controls
        ↓
Implementation
        ↓
Security Testing
        ↓
Release Decision
        ↓
Runtime Monitoring
```

This connects threat modeling to:

- Secure SDLC
- AppSec
- API Security
- Cloud Security
- Kubernetes Security
- DevSecOps
- Vulnerability Management
- AI Security

---

# 30. Final Teaching Principle

The goal is **not** for the student to memorize:

```text
S = Spoofing
T = Tampering
R = Repudiation
I = Information Disclosure
D = Denial of Service
E = Elevation of Privilege
```

The goal is for the student to look at:

```text
User
 ↓
Frontend
 ↓
API Gateway
 ↓
Service
 ↓
Database
```

and immediately start asking:

```text
What are we protecting?

Who can access it?

What can the attacker control?

Where are the trust boundaries?

What can the attacker reach?

What could go wrong?

What is the impact?

What is the risk?

How do we mitigate it?

How do we test the mitigation?

How do we monitor the remaining risk?
```

> **That is threat modeling.**

The most effective way to teach it is:

**Understand the application → understand the architecture → understand the data → think like an attacker → identify threats → assess risk → design controls.**