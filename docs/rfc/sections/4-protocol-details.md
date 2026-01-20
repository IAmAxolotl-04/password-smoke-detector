# 4. Protocol Details

## 4.1 Hash Function Requirements

Must support SHA-512, should support SHA-256/SHA-384.

## 4.2 Prefix Exchange Mechanism

- Privacy vs. utility tradeoff
- Recommended prefix: 16 hex chars

## 4.3 Server-Side Processing

- Indexed breach DB
- Return possible matches
- Do not log queries

## 4.4 Client-Side Verification

- Compute full hash
- Compare prefix
- Verify local match
