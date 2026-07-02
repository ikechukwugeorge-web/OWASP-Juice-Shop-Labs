Authentication Testing and JWT Analysis
Overview
This lab focused on testing authentication mechanisms in the OWASP Juice Shop, a deliberately vulnerable web application. The primary goals were to identify weaknesses in the login process, analyze JSON Web Tokens (JWTs), and demonstrate the risks of weak password storage.
Tools Used

Burp Suite (Proxy, Repeater)
jwt.io
John the Ripper
Kali Linux
OWASP Juice Shop

Attack Workflow & Key Steps

Login Request Interception
Used Burp Suite Proxy to capture the login request. Sent it to Repeater to analyze and manipulate the authentication flow.
SQL Injection for Authentication Bypass
Exploited a SQL Injection vulnerability in the login form using the payload ' or 1=1-- to log in as the administrator account without knowing the actual password.
JWT Token Analysis & Manipulation
Extracted the JWT token from the successful login response.
Used jwt.io to decode the token and analyzed its structure (Header, Payload, Signature).
Successfully modified the token by changing the role from admin to superadmin and setting the algorithm to none, demonstrating a Broken Authentication vulnerability.
Password Hash Analysis
Extracted the admin password hash (0192023a7bbd73250516f069df18b500) from the response.
Used John the Ripper to crack the MD5 hash, recovering the plaintext password admin123.

Screenshots Included

Burp Suite capturing and manipulating login requests
SQL Injection bypass
JWT decoding and manipulation on jwt.io
Password cracking with John the Ripper
Successful login as administrator/superadmin

Key Learnings

Web applications often fail to properly sanitize user input in authentication forms, allowing SQL Injection attacks.
JSON Web Tokens are widely used for session management, but poor implementation (weak signing algorithms, sensitive data in payload) can lead to complete account takeover.
Password hashing without proper algorithms (e.g., MD5) is insufficient against offline cracking tools.
Understanding HTTP traffic analysis with Burp Suite is essential for identifying authentication weaknesses.

Security Takeaways for Developers

Always use prepared statements or parameterized queries to prevent SQL Injection.
Implement strong JWT signing algorithms (RS256, ES256) and never store sensitive data in the payload.
Use modern password hashing algorithms (bcrypt, Argon2) with proper salting.
Enforce strong password policies and implement account lockout mechanisms.
