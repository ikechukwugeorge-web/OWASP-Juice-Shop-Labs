# JWT Manipulation

## Overview

This lab explores how JSON Web Tokens are used for authentication and authorization in OWASP Juice Shop. The objective was to better understand how role information stored in a JWT can influence application behavior when security controls are not implemented correctly.

## Tools Used

Burp Suite

JWT.io

OWASP Juice Shop

Kali Linux

## What I Did

After authenticating to the application, I captured the issued JWT and examined its contents using JWT.io. I reviewed the token claims and performed role claim modifications within the authorized lab environment to observe how the application responded.

## What the Screenshots Show

The screenshots show the captured JWT, inspection of its claims, modification of the role value, and the application's HTTP responses during testing.

## What I Observed

During testing, I modified the role claim from a standard customer role to a higher privileged role within the lab environment. After the modification, the application returned an HTTP 200 response. I then restored the original role value and continued observing the application's behavior.

## What I Learned

This exercise helped me understand how JWTs carry authentication and authorization information and why applications must never rely solely on the contents of a token. I learned that JWT signatures, token validation, and proper server side authorization checks are essential for protecting privileged functionality.

I also gained a better understanding of how HTTP responses can provide useful information during security testing and why every authorization decision should be validated on the server rather than trusting client controlled data.

## Security Takeaways

Applications should always verify JWT signatures before accepting a token.

Authorization decisions should be enforced on the server for every request.

JWTs should be validated for integrity, expiration, and authenticity before granting access to protected resources.
