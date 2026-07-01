# OWASP Juice Shop Application Recon Burp Suite

## What Burp Suite Was Used For

Burp Suite was used as a web proxy tool to intercept and analyze HTTP traffic between the browser and the OWASP Juice Shop application.

## What I Did

* Configured Burp Suite Proxy to capture traffic from the browser
* Accessed OWASP Juice Shop at 10.0.2.4:3000
* Monitored HTTP requests and responses in real time
* Used the Site map feature to visualize application structure
* Reviewed HTTP history to analyze captured requests
* Identified available endpoints within the application

## What I Observed

* All browser requests were successfully intercepted by Burp Suite
* The application generated multiple HTTP requests when navigating different pages
* The Site map automatically built a structure of the application endpoints
* HTTP history displayed detailed request and response data

## What I Learned

This exercise helped me understand how Burp Suite is used during the reconnaissance phase of a web application security assessment.

I learned how web applications communicate through HTTP requests and how a proxy can be used to intercept and analyze that traffic.

I also learned that mapping an application’s structure is an important first step in penetration testing because it reveals potential entry points for further security testing.
