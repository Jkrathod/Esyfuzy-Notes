## CRLF

#### In a CRLF injection attack, the attacker injects malicious code into a web application's input field, along with the CR and LF characters. When the input is processed by the application, the CR and LF  characters are consider as a newline character, which causes the application to insert a new line into the output. 

`Senario`

```
Imagine a web application that allows e to leave comments. 
These comments are later displayed on a webpage without proper validation or encoding.

An attacker identifies that the application doesn't handle CRLF characters correctly. 
They aim to manipulate how the application generates its HTTP responses.

Hello%0D%0AInjected-Header: Malicious-Content%0D%0A%0D%0AAttack-Payload

```

#### Here are a few common scenarios where CRLF injection can occur:

HTTP Response Splitting: Attackers can inject CRLF characters in user-provided input, 
like URL parameters or form fields, to manipulate the HTTP response sent by the server. 
This can lead to cache poisoning, session fixation, or cross-site scripting (XSS) attacks.

Email Header Injection: By injecting CRLF characters into email headers, attackers can control or modify email content, 
potentially leading to phishing attacks or unauthorized email actions.

HTTP Header Injection: CRLF injection in HTTP headers can allow attackers to create malicious responses or conduct attacks like HTTP response splitting.

`Impact:`

Depending on the application's behavior and the attacker's intentions, this attack can lead to various outcomes:

If the web server doesn't correctly handle the injected header, it might treat it as a new header, 
potentially leading to cache poisoning, session fixation, or other security issues.
The injected content could lead to XSS attacks if the attacker can control the JavaScript contex
