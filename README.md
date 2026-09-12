# DANSK — Citizenship Test Prep (Web)

A single-page web app for practising the Danish citizenship test (Indfødsretsprøven), served at [dansk.lenagibson.eu](https://dansk.lenagibson.eu/). It shares its Supabase backend and question bank with the companion Android app, [dansk-app](https://github.com/Lena-LSG/dansk-app).

## Contents

- [Features](#features)
- [Tech stack](#tech-stack)
- [Local development](#local-development)
- [Deployment](#deployment)
- [Security](#security)
- [Contributing](#contributing)
- [Licence](#licence)

## Features

- Practice Quiz, Full Mock Test, Exam Simulator, Weak Spots, and Flashcards modes
- Bilingual English/Danish interface
- Spaced-repetition progress tracking, with history and streak synced to Supabase and cached in `localStorage` for offline resilience
- Dark mode

## Tech stack

This is intentionally a single static HTML file (`index.html`) with no build step, bundler or framework: plain JavaScript and the [Supabase JS client](https://supabase.com/docs/reference/javascript/introduction), loaded from a CDN. This keeps the app trivial to self-host and to audit.

## Local development

No build step is required. Serve the file with any static file server, for example:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

The Supabase project URL and anon key are set directly in `index.html`. If you want to point a local copy at your own Supabase project rather than the production one, edit the `createClient(...)` call near the top of the script. See [Security](#security) for why this is safe to do in a client-side file.

## Deployment

This site is deployed with GitHub Pages, serving directly from the root of the `main` branch. `CNAME` configures the custom domain. Pushing to `main` deploys automatically; there is no separate build or release process.

## Security

See [SECURITY.md](SECURITY.md) for the vulnerability disclosure process. Worth noting explicitly, since this is a static client-side app with no server component of its own:

- The Supabase **anon/publishable key** embedded in `index.html` is intended to be public. It is not a secret; access to user data is controlled by Row Level Security policies on the Supabase project, not by keeping this key hidden.
- The Supabase **service role key** is never used here and must never appear in this repository.
- There is no server-side code in this repository at all, so most classes of server-side vulnerability (injection, SSRF, and so on) do not apply here; the attack surface is the client-side code and the Supabase project's own configuration.

## Contributing

Contributions are welcome. Please read [CONTRIBUTING.md](CONTRIBUTING.md) and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) before opening a pull request.

## Licence

Released under the [MIT Licence](LICENSE).
