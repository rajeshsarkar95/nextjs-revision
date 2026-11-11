# Route Handlers

A `route.ts` file defines HTTP endpoints inside the `app` directory.

Example: `app/api/users/route.ts`
```ts
import { NextResponse } from "next/server";

export async function GET() {
  return NextResponse.json([{ id: 1, name: "Asha" }]);
}

export async function POST(request: Request) {
  const body = await request.json();
  // Validate body and save it using your database layer.
  return NextResponse.json({ received: body }, { status: 201 });
}
```

Supported method exports include `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `HEAD`, and `OPTIONS`.

- `PUT`: commonly replaces a resource.
- `PATCH`: commonly updates part of a resource.
- `DELETE`: removes a resource.
- Validate input, authenticate/authorize requests, and return suitable status codes.
