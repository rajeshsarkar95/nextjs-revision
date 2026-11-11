# SEO and Metadata

Static metadata:
```tsx
import type { Metadata } from "next";

export const metadata: Metadata = {
  title: "Products | My Store",
  description: "Explore our products.",
};
```

Dynamic metadata:
```tsx
import type { Metadata } from "next";

type Props = { params: Promise<{ id: string }> };

export async function generateMetadata({ params }: Props): Promise<Metadata> {
  const { id } = await params;
  return { title: `Product ${id}` };
}
```

Other SEO files/concepts:
- `sitemap.ts`: sitemap generation.
- `robots.ts`: crawler rules.
- Open Graph metadata: social sharing previews.
- Use descriptive titles, descriptions, canonical URLs where appropriate, and meaningful image alt text.
