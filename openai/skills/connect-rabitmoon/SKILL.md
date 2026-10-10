---
name: connect-rabitmoon
description: Connect an AI client to rabitmoon infography, check account access and credits, and explain the private-document generation workflow.
---

Use the client's OAuth connection for the rabitmoon server at
https://api.rabitmoon.com/mcp. Let the user sign in through its browser flow;
never collect passwords, authorization codes, tokens or provider API keys in chat.
Installation does not bypass beta eligibility. If OAuth fails, report the actual
error and ask the user to reconnect; do not substitute another person's account.

After connection, call get_account_usage and get_creation_guide. This verifies
access without starting generation. Explain the available balance, private owner
links, and that create/edit consume credits based on actual work. Do not promise
a fixed price or free failures. Do not create a sample unless the user asks.

Show one relevant example: creating a 4:5 carousel from supplied facts or editing
one page using the document's current revision. Read the server's workflow,
design, visuals and request-contract guides as needed. The live tool schema is
authoritative when a packaged example differs from the server.
