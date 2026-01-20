3.  Protocol Details

   3.1.  Hashing and Prefix Extraction

   - Clients hash passwords locally using a strong algorithm (e.g., SHA-512).
   - A fixed-length prefix (e.g., 16 hex characters) is extracted for server queries.
   - Prefix length is chosen to balance security and query efficiency.

   3.2.  Server Query

   - Client sends only the prefix to the server.
   - Server returns candidate full hashes that match the prefix.
   - Server does not learn which full hash (if any) is present on the client.

   3.3.  Local Verification

   - Client compares received hashes with its own local full hash.
   - No sensitive data is transmitted during verification.
   - Client determines breach status entirely locally.
