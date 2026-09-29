# EmDash Cloudflare Test

Minimal Cloudflare deployment used to verify the fork before Salotto-specific work starts

## Resources

Wrangler provisions these resources on first deploy if they do not already exist:

- Worker: `emdash-test`
- D1: `emdash-test`
- R2: `emdash-test-media`

The test intentionally does not configure a custom domain, Cloudflare Access, Cloudflare Images/Stream, AI Search, marketplace plugins, or sandboxed plugins

## Local development

```bash
pnpm dev
```

Open:

```text
http://localhost:4321/_emdash/admin
```

EmDash runs migrations automatically on first request

## Preview

```bash
pnpm build
pnpm preview
```

## Deploy

```bash
pnpm deploy
```

After deployment, open the Worker URL and then `/_emdash/admin`

## Next checks

Verify the standard EmDash behavior before adding Salotto-specific code:

- initial setup and authentication
- admin usability on desktop and mobile
- collections and schema editing
- rich-text editing
- drafts, publishing, and revisions
- media upload to R2
- redirects
- theme behavior

Sandboxed plugins can be enabled later by adding a Worker Loader binding and sandbox configuration
