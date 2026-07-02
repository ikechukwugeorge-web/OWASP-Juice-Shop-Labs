Content Discovery using Burp Suite Intruder
Overview
Performed automated content discovery on the OWASP Juice Shop web application using Burp Suite Intruder to identify hidden directories, files, and API endpoints that were not directly linked or advertised.
Tools Used

Burp Suite (Proxy, Intruder, Site Map)
OWASP Juice Shop

Methodology & Steps

Initial Reconnaissance
Browsed the application while capturing all traffic with Burp Suite Proxy to build an initial site map.
Wordlist Preparation
Used common web application wordlists (e.g., directory brute-force lists) containing common endpoints like /admin, /api, /login, /users, etc.
Intruder Attack
Sent a base request to the application root and used Burp Intruder in Sniper mode to fuzz directory and file paths.
Analyzed the results based on response status codes (especially 200 OK, 301, 403).
Key Discoveries
Successfully identified several hidden or sensitive endpoints, including:
/admin and /administration (Broken Access Control)
/api/Users (User data exposure)
/rest/admin/application-configuration (Configuration disclosure)
Various other REST API paths


What I Learned

The importance of automated content discovery in web application penetration testing.
How to effectively use Burp Suite Intruder for directory and parameter fuzzing.
Interpreting different HTTP status codes (200, 403, 500, etc.) to identify potentially vulnerable or hidden resources.
Real-world applications often have many unlinked but accessible endpoints that can significantly expand the attack surface.

Security Takeaways

Developers should avoid "security by obscurity" — all sensitive endpoints must be properly protected with authentication and authorization.
Regular directory brute-forcing should be part of every web application security assessment.
Proper server configuration (e.g., disabling directory listing) helps reduce information disclosure risks.
