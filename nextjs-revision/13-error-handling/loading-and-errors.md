# Loading and error handling

- `loading.tsx`: route-segment loading UI; Next.js uses Suspense behavior.
- `error.tsx`: route-segment error boundary; must be a Client Component.
- `global-error.tsx`: root-level error UI.
- `not-found.tsx`: custom not-found UI.
- `notFound()`: programmatically trigger not-found handling.

Example `app/dashboard/loading.tsx`:
```tsx
export default function Loading() {
  return <p>Loading dashboard...</p>;
}
```

Example `app/dashboard/error.tsx`:
```tsx
"use client";

export default function ErrorPage({
  error,
  reset,
}: {
  error: Error & { digest?: string };
  reset: () => void;
}) {
  return (
    <section>
      <p>Something went wrong.</p>
      <button onClick={() => reset()}>Try again</button>
    </section>
  );
}
```
Do not expose sensitive internal error details to end users.
