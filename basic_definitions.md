1. Security Fundamentals

Information Security: Protecting data and systems from unauthorized access, change, or disruption.
Cybersecurity: Defending digital systems, networks, and applications from attacks.
CIA Triad: Confidentiality (only authorized access), Integrity (no unauthorized modification), Availability (accessible when needed).
Authentication: Verifying identity, such as username plus password or token.
Authorization: Defining what an authenticated user is allowed to do.
Accountability: Ability to trace actions to an identity.
Non-repudiation: Proof that an action happened and cannot be denied later.
Asset: Anything valuable to the business, such as data, APIs, source code, credentials, or infrastructure.
Threat: A potential cause of harm, such as attacker behavior or malware.
Vulnerability: A weakness that can be exploited by a threat.
Risk: Likelihood and impact of a threat exploiting a vulnerability.
Control: Safeguard that prevents, detects, or corrects security issues.
Compensating Control: Alternative control used when the preferred control is not feasible.
Attack Surface: All possible points where an attacker can try to enter or extract data.
Security Posture: Overall strength of an organization’s security practices and controls.

2. Governance to Product Security Bridge

GRC: Governance, Risk, and Compliance; policy and oversight discipline.
Product Security: Security integrated into software design, development, testing, release, and operations.
Shift Left Security: Introducing security earlier in design and coding stages.
Security by Design: Building security requirements into architecture from the beginning.
Defense in Depth: Multiple layers of controls so one failure does not cause full compromise.
Least Privilege: Granting only minimum access needed for tasks.
Secure by Default: Safe configurations enabled by default, not optional.
Trust Boundary: Point where data or privileges move between different trust levels.

3. Secure SDLC Basics

SDLC: Software Development Life Cycle, from requirements to retirement.
Secure SDLC: SDLC with security activities in every phase.
Security Requirements: Explicit security expectations such as encryption, logging, and access control.
Security Gate: Release checkpoint requiring security criteria to pass.
Abuse Case: A misuse scenario showing how attackers can abuse features.
Security Champion: Engineer in each team who drives security adoption.
Code Review: Human review of code for quality and security issues.
Release Hardening: Final actions that reduce exploitable weaknesses before production.
Security Sign-off: Formal approval based on risk and control evidence.

4. Threat Modeling Basics

Threat Modeling: Structured method to identify threats, risks, and mitigations before incidents happen.
Data Flow Diagram: Visual map of processes, data stores, data flows, and trust boundaries.
STRIDE: Threat categories: Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, Elevation of Privilege.
Attack Tree: Diagram showing attacker goals and possible attack paths.
Misuse Case: Description of harmful user behavior against a system.
Mitigation: Technical or process measure reducing likelihood or impact.
Residual Risk: Risk remaining after controls are applied.

5. Vulnerability Management Basics

Vulnerability Management: Continuous cycle of discover, assess, prioritize, remediate, and verify.
CVE: Public identifier for a known vulnerability.
CVSS: Scoring method for vulnerability severity.
EPSS: Probability score estimating likelihood of exploitation.
Exploitability: How practical it is for attackers to use a vulnerability.
Patch Management: Process of applying vendor fixes safely and promptly.
Risk-based Prioritization: Fix order based on business impact and exploit likelihood.
SLA for Remediation: Target timelines for fixing vulnerabilities by severity.
False Positive: Scanner finding that is not actually a real vulnerability.
Exception or Risk Acceptance: Formal approval to temporarily not fix an issue with justification.

6. API Security Basics

API: Interface allowing systems to communicate via requests and responses.
REST: API style using HTTP methods and resources.
GraphQL: Query language and runtime for flexible API data access.
BOLA: Broken Object Level Authorization, users access objects they should not.
Authentication Token: Credential proving identity in API calls.
JWT: Token format with signed claims.
OAuth 2.0: Authorization framework for delegated access.
OpenID Connect: Identity layer on top of OAuth 2.0.
Rate Limiting: Restricting request volume to prevent abuse and denial of service.
Input Validation: Ensuring incoming data is expected, safe, and well-formed.
API Gateway: Entry layer applying auth, routing, and policy enforcement.

7. AI, LLM, RAG, and Agent Security Basics

AI Security: Protecting AI systems, data, models, and outputs from abuse.
LLM: Large Language Model trained on massive text corpora.
Prompt Injection: Malicious input that manipulates model behavior.
Jailbreak: Bypassing model safety constraints.
Hallucination: Confident but incorrect model output.
Data Leakage: Sensitive data exposure through prompts, context, logs, or outputs.
RAG: Retrieval-Augmented Generation, model answers using retrieved external knowledge.
Vector Database: A database optimized for similarity search using embeddings.
Embedding: Numeric representation of text used for semantic search.
RAG Poisoning: Injecting malicious or misleading content into retrievable knowledge.
Grounding: Forcing model responses to trusted evidence.
AI Guardrails: Rules and filters controlling prompts, tools, data access, and output.
Agent: LLM-driven system that can plan and call tools.
Tool Abuse: Exploiting agent tool permissions to perform unauthorized actions.
Model Context Window: Maximum input/output token capacity for one interaction.

8. Cloud Security Fundamentals

Shared Responsibility Model: Cloud provider secures cloud infrastructure, customer secures what they run in cloud.
Cloud Misconfiguration: Unsafe settings such as public storage or weak IAM roles.
IAM: Identity and Access Management for users, roles, policies, and permissions.
Role-Based Access Control: Access rights tied to roles, not individuals.
Service Account: Non-human identity used by applications or workloads.
Secret Management: Secure storage and rotation of credentials and keys.
CSPM: Cloud Security Posture Management, continuous cloud configuration assessment.
Cloud Threat Modeling: Threat modeling focused on cloud services, identities, and control planes.
Control Plane: Management APIs and services controlling cloud resources.
Data Plane: Runtime path where workloads process and transfer data.

9. Docker and Kubernetes Security Basics

Container: Isolated runtime package with app code and dependencies.
Image: Read-only template used to create containers.
Image Hardening: Reducing image size, packages, and vulnerabilities.
Runtime Security: Monitoring and blocking malicious behavior during execution.
Orchestration: Automated deployment, scaling, and management of containers.
Kubernetes: Container orchestration platform.
Pod: Smallest deployable unit in Kubernetes.
Namespace: Logical isolation boundary in Kubernetes.
RBAC in Kubernetes: Role-based permissions for API actions.
Network Policy: Rules controlling traffic between pods and services.
Admission Controller: Policy checks before resources are accepted by cluster.
Secret in Kubernetes: Object holding sensitive values, should be encrypted and access-limited.
Supply Chain Security: Protecting code, dependencies, builds, artifacts, and deployments from tampering.

10. DevSecOps Basics

DevSecOps: Integrating security into development and operations automation.
CI: Continuous Integration, frequent merge and build with automated checks.
CD: Continuous Delivery or Deployment, automated release pipeline.
SAST: Static Application Security Testing, scans source or bytecode without running app.
DAST: Dynamic Application Security Testing, tests running application externally.
SCA: Software Composition Analysis, identifies vulnerable open source dependencies.
IaC Security: Scanning infrastructure code for insecure cloud configurations.
Secret Scanning: Detecting hardcoded passwords, keys, and tokens.
Policy as Code: Defining security rules as machine-enforced code in pipelines.
Build Provenance: Verifiable record of how an artifact was built.
SBOM: Software Bill of Materials listing included components and versions.

Understand each definition and acronym.
Be able to classify examples into threat, vulnerability, risk, and control.
Explain the difference between preventive, detective, and corrective controls.
Draw a basic data flow diagram and identify trust boundaries.
Describe where SAST, SCA, and DAST fit in CI/CD.
