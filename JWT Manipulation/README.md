JSON Web Token (JWT) Manipulation & Privilege Escalation
Overview
Explored the use of JSON Web Tokens (JWTs) for authentication and authorization in the OWASP Juice Shop application. The primary goal was to demonstrate how weak JWT implementation can lead to privilege escalation.
Tools Used

Burp Suite (Proxy & Repeater)
jwt.io
OWASP Juice Shop
Kali Linux

Methodology & Steps

Token Capture
Successfully logged in as administrator using SQL Injection and captured the issued JWT token from the response.
Token Analysis
Decoded the JWT using jwt.io to examine its structure (Header, Payload, Signature).
Identified sensitive claims, particularly the role field.
Token Manipulation
Modified the role claim from admin to superadmin.
Changed the signing algorithm from RS256 to none (removing signature validation).
Re-encoded the modified token.
Exploitation
Used the tampered token in subsequent requests via the Authorization: Bearer header.
Observed successful privilege escalation and access to higher-level functionality.

Key Findings

The application accepted unsigned tokens (alg: "none").
Changing the role claim granted elevated privileges.
Demonstrated a complete authentication/authorization bypass.

What I Learned

JSON Web Tokens are widely used for stateless authentication but can be dangerous if not properly validated.
Server-side validation of JWT signatures, expiration, and claims is critical.
Authorization logic must always be enforced on the server — never trust client-controlled data.
Understanding JWT structure helps identify common implementation weaknesses.

Security Takeaways for Developers

Always use strong signing algorithms (RS256, ES256) and never accept none.
Validate JWT signature, expiration, issuer, and audience on every request.
Do not store sensitive authorization data (e.g., roles) in the payload without proper protection.
Implement server-side authorization checks independent of the token content.
