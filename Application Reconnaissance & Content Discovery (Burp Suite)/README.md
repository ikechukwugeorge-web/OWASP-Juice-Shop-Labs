Application Reconnaissance using Burp Suite
Overview
Performed initial reconnaissance on the OWASP Juice Shop application to understand its structure, endpoints, and request/response behavior using Burp Suite as a web proxy.
Tools Used

Burp Suite (Proxy, Site Map, HTTP History)
Firefox Browser
OWASP Juice Shop (10.0.2.4:3000)

Methodology & Steps

Proxy Configuration
Configured Burp Suite Proxy and set the browser to route traffic through it.
Traffic Interception
Accessed the application and captured all HTTP requests and responses in real time.
Application Mapping
Used Burp Suite’s Site Map feature to automatically discover and visualize the application’s directory structure and endpoints.
Request Analysis
Reviewed the HTTP History tab to analyze request methods, parameters, headers, and response codes.

Key Observations

Successfully intercepted all browser-to-application traffic.
Identified multiple endpoints including /admin, /login, /api/Users, and various REST API paths.
Discovered publicly accessible admin functionality, indicating Broken Access Control.
Mapped the overall application architecture through passive crawling.

What I Learned

How to effectively configure and use Burp Suite as an intercepting proxy for web application testing.
The importance of reconnaissance in identifying hidden or sensitive endpoints.
How web applications communicate via HTTP and how valuable information can be gathered from request/response analysis.
Understanding the Site Map feature helps build a clear picture of the target application’s attack surface.

Security Takeaways

Developers should avoid exposing sensitive endpoints publicly.
Proper access controls should be implemented from the early stages of development.
Comprehensive reconnaissance is the foundation of every successful web application penetration test.
