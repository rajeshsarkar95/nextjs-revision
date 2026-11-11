# Dynamic routes

A folder named `[param]` creates a dynamic route.

Example structure:
```text
app/
└── products/
    └── [id]/
        └── page.tsx
```

Modern App Router example:
```tsx
type Props = {
  params: Promise<{ id: string }>;
};

export default async function ProductPage({ params }: Props) {
  const { id } = await params;
  return <h1>Product: {id}</h1>;
}
```

Other patterns:
- `[slug]`: one dynamic segment.
- `[...slug]`: catch-all segments.
- `[[...slug]]`: optional catch-all segments.
