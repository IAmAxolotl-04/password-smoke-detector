# 3. Protocol Overview

## 3.1 Core Protocol Flow

1. Client hashes password locally
2. Extracts prefix
3. Sends prefix to server
4. Server returns possible matches
5. Client verifies locally

## 3.2 Threat Model

- Honest-but-Curious Server
- Passive network observer
- Client integrity

CSP does NOT protect against MITM, malware, or malicious server responses.
