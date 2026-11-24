---
name: connect-rabitmoon
description: Connect an AI client to rabitmoon infography, check account access and credits, and explain the private-document generation workflow.
---

1. In rabitmoon Account → MCP connections, select the user's AI client. Add the
   remote Streamable HTTP server at https://api.rabitmoon.com/mcp using OAuth
   discovery and automatic client registration. For ChatGPT, install the remote
   server connection in the intended workspace.
2. Start the client's sign-in action. The user chooses the rabitmoon account
   and approves access in the browser. Keep passwords, authorization codes,
   tokens and provider API keys out of chat. Use an active rabitmoon account.
3. If sign-in fails, check whether the client supports CIMD or DCR, the
   callback differs from its registration, or the account lacks access. For a
   callback mismatch, share only the client name and callback host, port and
   path with support. Exclude query parameters and fragments.

After connection, call get_account_usage and get_creation_guide. This verifies
access without starting generation. Explain the available balance, private owner
links, and that create/edit consume credits based on actual work. Do not promise
a fixed price or free failures. Do not create a sample unless the user asks.

Show one relevant example: creating a 4:5 carousel from supplied facts or editing
one page using the document's current revision. Read the server's workflow,
design, visuals and request-contract guides as needed. The live tool schema is
authoritative when a packaged example differs from the server.
