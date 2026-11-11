# Data fetching and revalidation

Server Components can use `async` functions and `fetch`:
```tsx
type Post = { id: number; title: string };

export default async function PostsPage() {
  const response = await fetch("https://jsonplaceholder.typicode.com/posts", {
    next: { revalidate: 60 },
  });
  if (!response.ok) throw new Error("Failed to fetch posts");
  const posts: Post[] = await response.json();

  return <ul>{posts.slice(0, 5).map((post) =>
    <li key={post.id}>{post.title}</li>
  )}</ul>;
}
```

- Parallel fetching: start independent promises together with `Promise.all`.
- Sequential fetching: await one request before starting the next when there is a dependency.
- Revalidation: refresh cached data after a time interval or after a mutation.
- `revalidatePath()` and `revalidateTag()` can invalidate relevant cached data from supported server contexts.

Always handle HTTP errors and validate external data.
