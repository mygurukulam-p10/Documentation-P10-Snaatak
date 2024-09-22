# Generic CI Operation: Credential Scanning


### Introduction
Credential scanning is a process used in Continuous Integration (CI) to automatically check code for sensitive information like passwords, API keys, or tokens. It helps ensure that no critical data is accidentally shared in the codebase or in public repositories, which could lead to security issues.

As part of the CI pipeline, where code is built and tested automatically, credential scanning ensures that sensitive information doesn’t slip through unnoticed. This process is especially important in modern, fast-paced development environments where mistakes can happen.

### What is Credential Scanning?
Credential scanning is simply the act of scanning through your code, configuration files, or logs to check for sensitive information, like:

- **Passwords**
- **API keys**
- **Tokens (used to access services securely)**

If any of these are found in the code, they could be a security risk because attackers could steal and misuse them. Credential scanners identify patterns that match sensitive data, helping you catch and fix these issues early.

