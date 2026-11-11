# App Router file conventions

| File | Purpose |
|---|---|
| `page.tsx` | Route UI |
| `layout.tsx` | Shared layout |
| `template.tsx` | Re-created layout-like wrapper on navigation |
| `loading.tsx` | Suspense-based loading UI |
| `error.tsx` | Segment error boundary; must be a Client Component |
| `global-error.tsx` | Root-level error UI |
| `not-found.tsx` | Not-found UI |
| `route.ts` | HTTP request handler |
| `default.tsx` | Fallback UI for parallel routes |

A folder does not become a page until it contains a `page.tsx` (or a `route.ts` for an endpoint).
