# Changelog

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project follows [Semantic Versioning](https://semver.org/spec/v2.0.0.html) on a best-effort basis. As this app has no version number of its own (it deploys directly from `main`), entries are grouped by date instead.

## [Unreleased]

### Added

- Repository governance documentation: `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, and GitHub issue/pull request templates.

## 2026-09-11

### Added

- History and streak are now synced to Supabase, keyed to the signed-in account, with a `localStorage` cache retained for offline resilience. Previously these were `localStorage`-only and did not follow the user across devices.

## 2026-06-23

### Added

- Responsive desktop and large-screen layout, replacing the mobile-first single-panel design with a rail-based layout for wider viewports.

### Fixed

- Several authentication reliability issues, including a race condition during initialisation and a hang on sign-in.

## 2026-05-23 to 2026-05-24

### Added

- New Supabase backend, question bank and authentication, replacing the previous data source.
- Client-side caching of the question bank, and request timeouts on backend calls, to avoid the UI hanging on a slow or failed connection.

## 2026-04-07

### Added

- Spaced-repetition learning logic and an expanded question set.

## 2026-03-12

### Added

- Initial one-page web app, deployed via GitHub Pages with a custom domain (`CNAME`).
