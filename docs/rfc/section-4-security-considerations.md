4.  Security Considerations

   - Prefix length must be sufficient to prevent collisions and minimize leakage.
   - Servers should rate-limit queries to mitigate enumeration attacks.
   - Full hashes should never leave the client.
   - Consider adding optional salts or HMACs to further strengthen privacy.
   - Ensure TLS is used for all client-server communications.
