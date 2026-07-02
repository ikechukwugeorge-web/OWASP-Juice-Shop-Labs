Insecure Direct Object Reference (IDOR) Exploitation
Overview
Conducted testing for Insecure Direct Object Reference (IDOR) vulnerabilities in the OWASP Juice Shop application to demonstrate how insufficient authorization checks can allow users to access objects belonging to other users.
Tools Used

Burp Suite (Proxy & Repeater)
OWASP Juice Shop
Kali Linux

Methodology & Steps

Identified Object References
While logged in as a standard user, I captured requests to user-related endpoints (e.g., /api/users, /rest/user) using Burp Suite.
IDOR Testing
Modified object identifiers (e.g., user IDs) in the requests:
Changed /api/users/1 to /api/users/2, /api/users/3, etc.
Tested access to other users' profiles, data, and resources.

Privilege Context
Repeated the tests after escalating to administrator/superadmin level via JWT manipulation to observe differences in access.

Key Findings

Successfully accessed other users' information by modifying numeric IDs in API requests.
Demonstrated that the application failed to properly verify whether the authenticated user was authorized to access the requested objects.
Highlighted how predictable object references combined with missing server-side authorization checks create significant security risks.

What I Learned

Authentication (proving "who you are") is not the same as Authorization (proving "what you are allowed to do").
IDOR vulnerabilities are common when object references (IDs, filenames, etc.) are predictable and not properly validated on the server.
Server-side authorization checks must be implemented for every sensitive request, regardless of the user's authentication status.
Tools like Burp Suite Repeater are highly effective for systematically testing IDOR vulnerabilities.

Security Takeaways for Developers

Always perform server-side authorization checks before returning any object.
Avoid using predictable, sequential identifiers for sensitive resources.
Consider using random, non-sequential, or UUID-based references where appropriate.
Follow the principle of least privilege for all authenticated users.
