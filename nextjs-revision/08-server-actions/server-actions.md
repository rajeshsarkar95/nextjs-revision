# Server Actions

A Server Action is an asynchronous function that runs on the server and can be invoked from supported React/Next.js interactions.

```tsx
// app/actions.ts
"use server";

export async function saveName(formData: FormData) {
  const name = String(formData.get("name") ?? "").trim();
  if (!name) throw new Error("Name is required");
  // Validate authorization and persist data securely.
}
```

```tsx
// app/page.tsx
import { saveName } from "./actions";

export default function Page() {
  return (
    <form action={saveName}>
      <input name="name" required />
      <button type="submit">Save</button>
    </form>
  );
}
```

Security reminders:
- Treat Server Actions as public-facing mutation endpoints.
- Authenticate and authorize inside the action.
- Validate all input on the server.
- Do not trust hidden form fields or client-side validation alone.
