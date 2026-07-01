# Insecure Direct Object Reference

## Overview

This lab documents my exploration of an Insecure Direct Object Reference (IDOR) vulnerability in OWASP Juice Shop. The objective was to understand how improper authorization checks can allow users to access resources that should belong to other users.

## Tools Used

Burp Suite

OWASP Juice Shop

Kali Linux

## What I Did

I analyzed application requests and identified object references used by the application. I tested whether modifying these references could provide access to information or resources that should normally require additional authorization.

## What the Screenshots Show

The screenshots demonstrate the requests that were tested, the modified object references, and the application's responses during the IDOR exercise.

## What I Learned

This exercise helped me understand that authentication alone is not enough to secure an application. Even when a user is logged in, the application must verify that the user is authorized to access every requested resource.

I also learned that predictable identifiers can become a security risk when proper server side authorization checks are missing. This reinforced the importance of validating every request on the server before returning sensitive information.

## Security Takeaways

Applications should enforce authorization checks for every request.

Access to resources should always be verified on the server side.

Developers should avoid relying only on client side controls to protect sensitive data.
