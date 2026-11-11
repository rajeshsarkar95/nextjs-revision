# Rendering strategies

| Strategy | Meaning | Common use |
|---|---|---|
| CSR | Browser renders UI using JavaScript | Highly interactive client UI |
| SSR | HTML is generated on the server for a request | Request-specific pages |
| SSG | HTML is generated ahead of time | Stable content |
| ISR | Static output is refreshed after deployment | Content that changes periodically |
| Streaming | UI is sent in chunks as parts become ready | Slow data sections |

Important: modern Next.js rendering and caching behavior is configurable and has changed across versions. Do not assume every `fetch()` is cached by default; check the version-specific docs and set caching/revalidation intentionally.
