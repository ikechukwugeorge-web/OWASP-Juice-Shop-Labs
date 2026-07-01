# Authentication Testing and JWT Analysis

## Overview

This lab documents my authentication testing in OWASP Juice Shop using Burp Suite and other security tools. The objective was to better understand how authentication requests are processed, how JSON Web Tokens (JWTs) are used, and how weak credentials or authentication weaknesses can affect application security.

## Tools Used

Burp Suite

JWT.io

John the Ripper

Kali Linux

OWASP Juice Shop

## What I Did

I captured the login request using Burp Suite Proxy and examined the HTTP request. I sent the request to Repeater to better understand how the application handled authentication requests during testing.

After successfully authenticating within the lab, I examined the JSON Web Token issued by the application using JWT.io to understand the information stored inside the token. I also analyzed password related data available within the authorized lab exercise and used John the Ripper to demonstrate how weak passwords can be recovered from password hashes in a controlled environment.

Finally, I used the recovered credentials to access the corresponding account within the Juice Shop lab and observe the application's behavior after successful authentication.

## What the Screenshots Show

The screenshots demonstrate the authentication workflow throughout the exercise, including the captured login request, request analysis in Burp Suite, JWT inspection, password hash analysis with John the Ripper, and successful authentication within the OWASP Juice Shop application.

## What I Learned

This exercise helped me understand how web applications process authentication requests and how Burp Suite can be used to inspect and analyze HTTP traffic during security assessments.

I learned how JSON Web Tokens are structured and how they can contain useful information for understanding an application's authentication process. Decoding a JWT also helped me better understand token based authentication and why sensitive information should never be exposed unnecessarily.

Working with John the Ripper reinforced the importance of strong password policies and secure password storage. It demonstrated how weak passwords can be recovered if an attacker obtains password hashes.

Overall, this lab improved my understanding of authentication workflows, HTTP request analysis, token based authentication, password security, and the importance of implementing secure authentication mechanisms to protect user accounts.

## Security Takeaways

Strong passwords should be enforced for all users.

Password hashes should be protected using modern hashing algorithms and appropriate security practices.

Authentication tokens should be generated and validated securely.

Applications should implement secure authentication controls to reduce the risk of unauthorized account access.
