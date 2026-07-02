Broken Access Control Exploitation
Overview
Conducted testing on the OWASP Juice Shop application to identify and exploit Broken Access Control vulnerabilities, demonstrating how insufficient authorization checks can allow unauthorized access to restricted resources.
Tools Used

Burp Suite (Proxy & Repeater)
OWASP Juice Shop

Methodology & Steps

Initial Access
Logged in as a standard user and navigated through the application while monitoring all requests in Burp Suite.
Access Control Testing
Attempted to access administrative and sensitive areas of the application, including:
The /admin and /administration sections
User management and configuration endpoints (/api/Users, /rest/admin/application-configuration)
Other users' data via IDOR attempts (/api/users/ID)

Discovery
Identified that several admin-only resources were accessible without proper authorization.
Privilege Escalation
Combined findings with SQL Injection and JWT token manipulation to escalate privileges from a standard user to administrator/superadmin level.

Key Findings

The /admin endpoint was publicly accessible without authentication.
Multiple REST API endpoints (/api/Users, /rest/admin/...) returned sensitive data without proper role validation.
Successfully escalated privileges using JWT token manipulation by changing the role claim and setting the algorithm to none.

What I Learned

Broken Access Control occurs when applications fail to properly enforce authorization checks on the server side.
Relying solely on client-side (frontend) restrictions is insufficient — all sensitive operations must be validated on the backend.
IDOR (Insecure Direct Object Reference) and weak token-based authorization are common real-world issues.
Understanding how to chain multiple vulnerabilities (SQLi → JWT manipulation → privilege escalation) is critical for effective penetration testing.

Security Takeaways for Developers

Implement robust server-side authorization checks for every sensitive action.
Follow the principle of least privilege.
Never trust client-side controls for access decisions.
Properly validate and secure JSON Web Tokens (strong signing algorithms, no sensitive data in payload).
