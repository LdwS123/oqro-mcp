# Security policy

This repository holds the documentation and the registry manifest (`server.json`) of the OQRO MCP server. The server itself runs at <https://oqro.io/api/mcp>; there is no server code here to run or install, so the repository has no dependencies.

## Report a vulnerability

Write to **contact@oqro.io** with "Security" in the subject. Please include what you found, the address or tool involved, and the steps to reproduce it. Do not open a public issue for a vulnerability.

We read every report, answer within 5 working days, and tell you when it is fixed. We do not take legal action against good-faith research that stays within these limits: no access to other people's data, no denial of service, no social engineering, and no testing against accounts you do not own.

The same contact is published at <https://oqro.io/.well-known/security.txt>.

## What the server does for security

- **Sign-in is required.** Every request to the endpoint needs an OAuth 2.1 access token (PKCE with S256 is mandatory; the authorization server and protected-resource metadata are at `https://oqro.io/.well-known/oauth-authorization-server` and `https://oqro.io/.well-known/oauth-protected-resource/api/mcp`). A request without a token gets HTTP 401 with a `WWW-Authenticate` header that points at that metadata.
- **Read-only.** All tools read public disclosures. No tool writes, sends, or changes anything, and none reaches a member's private data.
- **Stateless.** No session is kept on the server.
- **Data is cited.** Every row links the official filing it comes from; tool output is data for the model to quote, never instructions.
- **Limits.** Requests are rate limited and request bodies are size limited.

## Supported versions

Only the live server at <https://oqro.io/api/mcp> is supported. Its card, with the transport and the tool list, is at <https://oqro.io/.well-known/mcp>.
