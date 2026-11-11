# Build and deployment

Local production check:
```bash
npm run build
npm start
```

Common deployment checklist:
- Set production environment variables in the hosting platform.
- Never commit `.env` files or secrets.
- Confirm database network access and production credentials.
- Configure allowed image hosts if using remote images.
- Check build logs and runtime logs.
- Test authentication, API routes, redirects, and error states.
- Use HTTPS and secure cookie settings.

Common platforms include Vercel and Node.js-compatible hosting providers.
