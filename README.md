# 🔐 Credential Shield Protocol
## Launch Day: January 17, 2026

### Mission
Building privacy-first authentication for the next generation of the internet.

### Day 1 Goal
Create a 'Password Smoke Detector' browser extension that checks password safety 100% locally.

### Quick Start
1. Load the extension in Chrome/Brave/Edge
2. Visit any login page
3. Type a password - see safety indicators appear

### Technology Stack
- Vanilla JavaScript (no frameworks)
- Chrome Extensions Manifest V3
- Zero-knowledge principles
- Local-first architecture

### Contact
Starting transparent from Day 1.

Competitive Landscape & Positioning

The Credential Shield Protocol (CSP) exists in a mature market of password breach checking solutions. Our approach is not to replicate existing services, but to offer a **privacy-first, open-source alternative** built on different architectural principles.

| Feature | Have I Been Pwned (Pwned Passwords) | PasswordRBL | **Credential Shield Protocol (CSP)** |
|---------|--------------------------------------|-------------|--------------------------------------|
| **Privacy Model** | k-Anonymity (5-char hash prefix) | Zero-logging policy | **Server-blind architecture** |
| **Data Exposure** | Server sees hash prefix | Server sees full PBKDF2 hash | **Server sees non-reversible token only** |
| **Source Code** | Closed (API only) | Closed proprietary | **Open-source (MIT License)** |
| **Deployment** | Cloud API only | Cloud API + Windows Agent | **Self-hostable anywhere** |
| **Cost Model** | Free tier, paid enterprise API | Monthly subscription (SaaS) | **Free / Self-hosted** |
| **Hash Compatibility** | SHA-1 / NTLM only | PBKDF2-SHA256 | **Any client-side hash algorithm** |
| **Target User** | Individuals, Developers | Windows/Active Directory Enterprises | **Privacy-conscious orgs, developers, regulated entities** |

### Why CSP Exists
- **For organizations that can't use cloud APIs** due to data sovereignty or compliance requirements.
- **For developers who want transparency and control** over their security infrastructure.
- **For situations where "zero-logging" policies aren't enough**—where you need architectural guarantees, not just promises.

CSP is not a direct competitor to these services, but a **different paradigm**: privacy-by-design as a protocol, not privacy-as-a-policy in a SaaS product.

---

## 🏗️ Project Structure

```
├── .github/              # GitHub workflows and templates
├── api-server/           # Reference API server implementation
├── protocol/             # Core protocol specification and logic
├── scripts/              # Build, test, and deployment scripts
├── package.json          # Node.js dependencies
├── quick-test.js         # Quick protocol test script
└── README.md             # This file
```


## 🚀 Live Demo

[![GitHub Pages](https://img.shields.io/badge/Live_Demo-Available-success)](https://iamaxolotl-04.github.io/password-smoke-detector/)
