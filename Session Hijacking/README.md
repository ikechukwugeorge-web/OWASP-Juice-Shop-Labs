Session Hijacking via Reflected XSS in OWASP Juice Shop Summary of Attack: I identified a Reflected XSS vulnerability in the search functionality of the OWASP Juice Shop application. By injecting a malicious payload, I was able to steal the victim's session token (JWT). Attack Flow:

Discovered Reflected XSS in the search bar using payloads like:HTML Developed a cookie stealer payload:HTML Set up listener on attacker machine:Bashnc -lvnp 4444 Captured the JWT token from the victim’s session when they interacted with the site. Hijacked the session by setting the stolen token as a cookie in the browser using developer tools:JavaScriptdocument.cookie = "token=STOLEN_JWT_TOKEN; path=/";

Impact:

Successfully impersonated the victim user without knowing their credentials. Demonstrated how XSS can lead to full account takeover via session hijacking.

Tools Used: Burp Suite, Firefox Developer Tools, Netcat Key Learning:

Reflected XSS can be chained with cookie stealing for session hijacking. Proper output encoding and CSP (Content Security Policy) are critical defenses.
