# Navigation

Use `next/link` for normal navigation:
```tsx
import Link from "next/link";
export default function Menu() {
  return <Link href="/dashboard">Dashboard</Link>;
}
```
Client navigation hooks come from `next/navigation` and require a Client Component:
```tsx
"use client";
import { useRouter, usePathname, useSearchParams } from "next/navigation";

export function Controls(){
  const router = useRouter();
  const pathname = usePathname();
  const searchParams = useSearchParams();

  return (
    <button onClick={() => router.push("/login?from=dashboard")}>
      Go from {pathname}; query: {searchParams.get("from")}
    </button>
  );
}
```
- `useRouter()`: imperative navigation, refresh, back, forward, replace.
- `usePathname()`: current pathname.
- `useSearchParams()`: read query-string values.
- `redirect()`: server-side redirect helper from `next/navigation`.
