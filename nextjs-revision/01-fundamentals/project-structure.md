# Project structure

```text
my-app/
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   ├── loading.tsx
│   ├── error.tsx
│   └── api/
│       └── users/
│           └── route.ts
├── components/
├── public/
├── lib/
├── next.config.ts
├── package.json
└── tsconfig.json
```

- `app/`: routes and route-level UI.
- `page.tsx`: makes a route publicly accessible.
- `layout.tsx`: shared UI around child routes.
- `loading.tsx`: loading UI for a route segment.
- `error.tsx`: error boundary UI for a route segment.
- `public/`: static assets served from the root URL.
- `next.config.ts`: framework configuration.
- `lib/`: a common place for reusable utilities (convention, not mandatory).
