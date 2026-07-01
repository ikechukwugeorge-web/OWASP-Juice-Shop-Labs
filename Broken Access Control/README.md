# Broken Access Control

## Overview

This lab focuses on testing broken access control vulnerabilities in OWASP Juice Shop. The goal was to understand how restricted resources can sometimes be accessed without proper authorization.

## What I Did

* Navigated through the application as a normal user
* Attempted to access restricted pages or resources
* Observed application responses when accessing unauthorized areas
* Analyzed how the application handles permission checks

## What I Observed

I observed that certain actions or pages behaved differently depending on how access was attempted. Some requests returned access denied responses, while others revealed that access control was not properly enforced in all cases.

## What I Learned

This exercise helped me understand how broken access control occurs when an application fails to properly restrict user actions based on roles or permissions.

I learned that attackers can potentially access sensitive functions or data if authorization checks are weak or missing. I also learned the importance of enforcing access control on both the frontend and backend, not just relying on the user interface.

## Key Takeaway

Proper authorization must be enforced on the server side to prevent unauthorized access to protected resources.
