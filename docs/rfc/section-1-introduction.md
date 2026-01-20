1.  Introduction

   1.1.  Motivation

   Traditional password breach checking services, while valuable for
   security, introduce privacy concerns by requiring users to submit
   full password hashes to centralized servers. This creates permanent
   query logs that can be analyzed, correlated, and potentially
   compromised.

   The Credential Shield Protocol (CSP) addresses this by implementing
   a zero-knowledge approach where only non-reversible hash prefixes
   are exchanged. The server assists in breach checking without
   learning whether a match was found, preserving user privacy while
   maintaining security utility.

   1.2.  Protocol Overview

   CSP operates on a simple principle: "Check without revealing."
   The protocol follows these steps:

   1.  Client hashes password locally using a strong cryptographic
       hash function (e.g., SHA-512)
   2.  Client extracts the first N characters (prefix) of the hash
   3.  Client sends only the prefix to the server
   4.  Server returns possible full hashes from breach databases
       that share that prefix
   5.  Client checks locally if any returned hash matches the full
       local hash
   6.  Server never learns the verification result

   This approach minimizes data exposure while providing breach
   checking functionality.
