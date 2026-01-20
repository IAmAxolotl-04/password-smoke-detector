# 4. Protocol Details

## 4.1. Hash Function Requirements
- MUST support SHA-512
- SHOULD support SHA-256 and SHA-384

## 4.2. Prefix Exchange
- Prefix length default: 16 hex chars (64 bits)
- Longer prefixes: fewer false positives
- Shorter prefixes: lower server load

## 4.3. Server-Side Processing
- Indexed breach database
- Return full hashes matching prefix
- Do NOT log or correlate queries

## 4.4. Client-Side Verification
- Compute full hash locally
- Compare against server results
- Verification result never leaves client device
