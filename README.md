# Python-Based Web Application Firewall (WAF) & Intrusion Detection System (IDS)

[![Language](https://img.shields.io/badge/Language-Python-blue.svg)](https://www.python.org/)
[![Category](https://img.shields.io/badge/Category-Security-red.svg)](https://owasp.org/www-project-top-ten/)

A hands-on, educational project to deepen my understanding of application security, network traffic analysis, and detection engineering. This WAF is being built from scratch in Python to identify and mitigate common security threats as defined by the OWASP Top 10.

## Project Vision & Goals

The primary goal is not to build a production-ready WAF, but to implement the core logic behind one. This involves:
1.  **Intercepting and Inspecting** HTTP/S traffic in real-time.
2.  **Analyzing** requests for malicious patterns (e.g., SQL Injection, XSS).
3.  **Blocking** identified threats before they reach the web application.
4.  **Logging and Alerting** on suspicious activity for analysis.

## Planned Features & Architecture

The project is being developed in phases:

### Phase 1: Core Traffic Interception (Proxy Engine)
-   [ ] Implement a basic man-in-the-middle (MITM) proxy using Python's `socket` or a library like `mitmproxy`.
-   [ ] Successfully receive HTTP requests from a client and forward them to the target server.
-   [ ] Intercept the server's response and forward it back to the client.

### Phase 2: Signature-Based Detection Engine
-   [ ] Develop a rule engine that uses regular expressions to match known attack patterns in request payloads.
-   [ ] **Targeted Threats:**
    -   SQL Injection (e.g., `' OR 1=1; --`)
    -   Cross-Site Scripting (XSS) (e.g., `<script>alert('XSS')</script>`)
    -   Directory Traversal (e.g., `../../etc/passwd`)
-   [ ] If a pattern is matched, the engine will flag the request as malicious.

### Phase 3: Action & Response Module
-   [ ] If a request is flagged, the WAF will take a pre-defined action (e.g., drop the request and return a `403 Forbidden` error).
-   [ ] Implement rate-limiting based on IP address to provide basic DoS protection.

### Phase 4: Logging & Alerting
-   [ ] Log all flagged requests to a file or console output.
-   [ ] The log entry will include the source IP, timestamp, the malicious payload, and the rule that was triggered.

## Technology Stack
*   **Language:** Python 3
*   **Core Libraries:** `socket`, `ssl`, `re` (for regex)
*   **Potential Libraries:** `mitmproxy`, `scapy` for more advanced packet inspection.

## Current Status
**Ongoing.** Project initialized. The foundational proxy structure and packet interception logic are currently under development.

## How to Run (Instructions to come)
_This section will be updated once the core functionality is stable._
