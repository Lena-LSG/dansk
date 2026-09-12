# Security Policy

## Supported versions

This is a personal project served directly from the `main` branch with no versioned release channel. Security fixes are applied to `main` and take effect on the next deployment, which happens automatically on push.

## Reporting a vulnerability

Please report suspected security vulnerabilities using **GitHub's private vulnerability reporting** feature on this repository, rather than opening a public issue:

1. Go to the **Security** tab of this repository.
2. Select **Report a vulnerability**.
3. Describe the issue, the impact, and steps to reproduce it if known.

This keeps the report private between you and the maintainer until a fix is available. Please do not disclose the issue publicly (including in a public issue, pull request or discussion) until it has been resolved.

You should expect an initial response within a few days. This project has a single maintainer, so response and fix times will vary with availability rather than following a fixed service-level agreement.

## Scope

This repository is a single static HTML file with no server-side component. Relevant areas for security review include:

- The Supabase client configuration embedded in `index.html`
- Authentication and session handling
- How history and streak data is read from and written to Supabase
- Client-side rendering of any user-controlled or remote data (for example, cross-site scripting via question content or stored history)

### Out of scope / by design

- The Supabase **anon/publishable key** embedded in `index.html` is intended to be public. It is not a secret, and finding it in the page source is not itself a vulnerability. Access to user data is controlled by Row Level Security policies on the Supabase project, not by keeping this key hidden. A report showing that a Row Level Security policy is missing, incorrect or bypassable is very much in scope and appreciated.
- The Supabase **service role key** is never used in this app and must never appear in this repository. If you find one, please report it immediately as a critical issue.
- This site is served over HTTPS with a certificate managed by GitHub Pages; certificate/TLS configuration issues at the GitHub Pages platform level are not this project's responsibility to fix, but are still worth reporting so they can be tracked.
