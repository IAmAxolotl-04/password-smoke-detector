# 3. Protocol Overview

## 3.1. Core Protocol Flow

1. Client hashes password locally using SHA-512
2. Extracts first N characters (prefix)
3. Sends prefix to server
4. Server returns potential full hashes with matching prefix
5. Client checks locally for full match

## 3.2. Threat Model

- Honest-but-curious server
- Passive network observer
- Client device integrity

CSP does NOT protect against:
- MITM attacks (TLS required)
- Client malware
- Malicious server data
