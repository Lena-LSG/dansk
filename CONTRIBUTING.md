# Contributing

Thank you for your interest in this project. It began as a personal tool and is maintained on a best-effort basis, but contributions, bug reports and suggestions are genuinely welcome.

## Before you start

For anything beyond a trivial fix (typos, small copy changes), please open an issue first to discuss the change. This avoids wasted effort on a pull request that does not fit the project's direction.

## Development setup

Follow the [Local development](README.md#local-development) section of the README. No build step or dependency installation is required.

## Branching and commits

- Branch from `main`.
- Use a short, descriptive branch name, e.g. `fix/streak-date-comparison`.
- Write commit messages in the imperative mood ("Fix", not "Fixed" or "Fixes"), and explain *why* a change was made when the reason is not obvious from the diff itself.
- Keep commits focused. A pull request that mixes an unrelated refactor with a bug fix is harder to review and harder to revert if something goes wrong.

## Code style

- This project is deliberately a single static HTML file with no build tooling. Please do not introduce a bundler, framework or dependency without discussing it in an issue first.
- Match the existing style of the surrounding code rather than introducing a new convention.
- Do not add comments that restate what the code does. Comments should explain a non-obvious constraint, trade-off or workaround.

## Security-sensitive changes

Anything touching the Supabase client configuration, authentication, or how history/streak data is read from or written to Supabase should be treated as security-sensitive. In particular:

- Never commit a secret API key. The anon/publishable key already present in `index.html` is intentionally public; the service role key must never appear anywhere in this repository.
- Never widen a database permission or Row Level Security policy without explaining why in the pull request description.
- If you believe you have found a vulnerability rather than a bug, please follow [SECURITY.md](SECURITY.md) instead of opening a public issue.

## Testing before submitting

There is no automated test suite for this project. At minimum, before opening a pull request, load the page locally and manually exercise the screens your change affects, in both English and Danish, and in both light and dark mode if relevant.

## Pull requests

- Describe what changed and why, not just what.
- Link the issue it resolves, if any.
- Note which browser(s) you tested in.

## Reporting bugs

Please use the bug report issue template and include:

- Steps to reproduce
- What you expected to happen
- What actually happened
- Browser and operating system
