2.  Terminology

   This section defines terms used in the CSP specification.

   - **Client:** The entity checking a password for breaches.
   - **Server:** The entity storing breach data and responding to prefix queries.
   - **Prefix:** The first N characters of a cryptographic hash.
   - **Zero-knowledge:** A property ensuring the server cannot deduce the client’s full hash.
   - **Full Hash:** The complete hash of the password (never sent to the server).
   - **Breach Database:** A collection of known compromised password hashes.
