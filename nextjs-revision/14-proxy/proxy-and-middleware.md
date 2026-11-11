# Middleware and Proxy

Next.js 16 uses the `proxy.ts` convention for request interception; earlier versions commonly use `middleware.ts`.

Typical uses:
- Redirect a user based on request information.
- Rewrite a URL.
- Add or modify request/response headers.
- Perform lightweight routing checks.

Next.js 16-style example:
```ts
import { NextResponse } from "next/server";
import type { NextRequest } from "next/server";

export function proxy(request: NextRequest) {
  if (request.nextUrl.pathname === "/old") {
    return NextResponse.redirect(new URL("/new", request.url));
  }
  return NextResponse.next();
}

export const config = {
  matcher: ["/old"],
};
```

Do not treat Proxy as a replacement for secure server-side authorization.
