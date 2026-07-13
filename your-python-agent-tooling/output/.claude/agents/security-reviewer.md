---
name: security-reviewer
description: "[PLACEHOLDER] — hardcoded credentials, unsafe API usage, missing input validation, insecure storage; when to use"
tools: "[PLACEHOLDER]"
model: "[PLACEHOLDER]"
---

<!--
TODO: security-reviewer sub-agent.
It receives a PR diff and checks for: hardcoded API keys, tokens, passwords, or secrets;
SQL built via string formatting instead of parameterized queries/an ORM; disabled TLS
verification; missing input validation on user-supplied data; a production entrypoint left in
debug mode; unsafe deserialization (eval()/pickle on untrusted data). Cover the clean-file case.
-->

[PLACEHOLDER]
