# Credential Shield Protocol (CSP) - Technical Specification
*Version 0.1 | Core Protocol & Value Proposition*

## 1. The Problem: Two Gaps in Current Solutions

### 1.1 The Hash Mismatch Problem
Modern applications **must** use strong, salted password hashes (Argon2, bcrypt, PBKDF2) for storage. However, breach databases (like HIBP's Pwned Passwords) primarily contain **SHA-1 or NTLM hashes**.

**Current "Solutions" Create Risk:**
*   **Downgrade & Query:** An application could re-hash the user's input with SHA-1 to query an API. This creates a **weak hash** of the password in memory/logs, violating security best practices.
*   **Brute-Force Local Check:** Downloading the full 60GB+ breach database to check against the application's strong hash locally is **operationally burdensome**.

### 1.2 The Data Liability Problem
Using any external API—even with k-anonymity—creates **query logs**. For an organization, these logs are a new data asset that must be protected, can be subpoenaed, and increases breach disclosure scope. Privacy policies like "zero-logging" are just that—policies, not architectural guarantees.

## 2. CSP's Architectural Proposition: Server-Blind Verification

CSP is designed to allow a service to check a credential against a breach database **without learning the credential or creating a queryable log**.

### 2.1 Core Protocol Flow**Outcome:** The server facilitates the check but cannot determine the original hash, the credential, or whether a match occurred.

### 2.2 Key Technical Differentiators
| Problem | HIBP / PasswordRBL Approach | CSP Approach |
| :--- | :--- | :--- |
| **Hash Mismatch** | Client must use or generate a SHA-1 hash. | Client uses its **production strong hash**. Protocol bridges the hash gap cryptographically. |
| **Data Liability** | k-Anonymity. Server sees hash prefix. Policy-based "no-logging". | **Server-blind.** Server sees only an opaque token. Logging is architecturally meaningless. |
| **Deployment** | Centralized service. | **Self-hostable** protocol. Breach DB stays within organizational control. |

## 3. Practical Implementation & Integration

### 3.1 For Application Developers
Integrate the CSP client library to add breach checking to sign-up or password reset flows. You never need to handle a SHA-1 hash of your user's password.

### 3.2 For Infrastructure Teams
Deploy the CSP server internally. It acts as a secure, privacy-preserving gateway to an updated breach corpus, fulfilling security mandates without creating external dependencies or internal logs.

## 4. Alignment with Research & Feedback
This design directly addresses the critical feedback from security experts:
*   **"Hash mismatch makes API use awkward"** (Jim, HIBP Research): CSP cryptographically bridges the hash gap.
*   **"Zero-logging is a policy"** (PasswordRBL Analysis): CSP makes logging irrelevant by design.
*   **"Need for self-hosted solutions in regulated entities"** (Competitive Analysis): CSP is a protocol, not a SaaS, enabling full control.

---
*This is a living document. The core value proposition is stable, but specifications will evolve with implementation feedback.*
