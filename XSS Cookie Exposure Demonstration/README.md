# Cross Site Scripting Cookie Demonstration

## Overview

This lab explores the impact of Cross Site Scripting (XSS) in OWASP Juice Shop. The objective was to understand how malicious JavaScript can execute within a user's browser when an application does not properly sanitize user input.

## Tools Used

Burp Suite

OWASP Juice Shop

Web Browser

Kali Linux

## What I Did

I identified an XSS vulnerability within the application and executed a JavaScript payload in the authorized lab environment. I observed how the browser processed the injected script and examined the information that became accessible as a result of the vulnerability.

## What the Screenshots Show

The screenshots demonstrate successful XSS payload execution, the browser's response, and the effects of the vulnerability during testing.

## What I Learned

This exercise helped me understand that Cross Site Scripting allows malicious JavaScript to execute in the context of a trusted website. I learned how this can expose browser data, manipulate page content, or perform actions on behalf of a user when appropriate security controls are missing.

The lab also reinforced the importance of validating and encoding user input, implementing Content Security Policy, and protecting authentication data with secure cookie settings where appropriate.

## Security Takeaways

Applications should validate and encode untrusted input before displaying it.

Content Security Policy helps reduce the impact of XSS attacks.

Sensitive session information should be protected using secure cookie attributes and strong authentication controls.

Developers should regularly test applications for XSS vulnerabilities during the secure development process.
