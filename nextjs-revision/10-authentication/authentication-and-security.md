# Authentication and authorization

- Authentication answers: **Who are you?**
- Authorization answers: **What are you allowed to do?**
- Session: server-recognized state associated with a user.
- Cookie: browser storage often used to carry a session identifier.
- JWT: signed token format; a JWT is not automatically encrypted.

Recommended checklist:
1. Use a maintained authentication library where appropriate.
2. Verify sessions on the server.
3. Enforce authorization close to the data or mutation.
4. Use secure cookie settings (`HttpOnly`, `Secure` in production, and appropriate `SameSite`).
5. Validate and sanitize inputs.
6. Keep secrets in server-only environment variables.
7. Do not rely only on hiding UI or redirecting in the browser.

Proxy/Middleware can help with early routing decisions, but it should not be the only authorization layer.
