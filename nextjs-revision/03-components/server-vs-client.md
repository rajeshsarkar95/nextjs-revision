# Server Components vs Client Components

## Server Components
In the App Router, components are Server Components by default. They can fetch data on the server and keep server-only logic out of the browser bundle.

## Client Components
Add `"use client"` at the top of a file when a component needs state, effects, event handlers, or browser APIs.

```tsx
"use client";

import { useState } from "react";

export default function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => setCount((n) => n + 1)}>Count: {count}</button>;
}
```

## Rules to remember
- Keep the Client Component boundary as small as practical.
- Server Components can render Client Components.
- Do not pass non-serializable values (such as ordinary functions) from Server Components to Client Components as props, except supported Server Action patterns.
- Never expose secrets in Client Component code.
