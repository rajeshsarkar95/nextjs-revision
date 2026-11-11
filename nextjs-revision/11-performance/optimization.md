# Performance optimization

- Use `next/image` for responsive image optimization.
- Use `next/font` to manage fonts efficiently.
- Lazy-load heavy client components when useful.
- Keep Client Component boundaries small.
- Avoid unnecessary client-side JavaScript.
- Use streaming and `Suspense` for slow independent sections.
- Measure with browser performance tools and real-user metrics.
- Optimize database queries and API payloads.

Example:
```tsx
import Image from "next/image";

export default function Avatar() {
  return <Image src="/avatar.png" alt="User avatar" width={96} height={96} />;
}
```
The image file should exist in `public/avatar.png`.
