# Lift Log

A workout tracker for progressive overload, built as a home-screen web app (PWA).

- `index.html`: the whole app (logging, rest timer, history, search, templates, plate helper)
- `sw.js`: lets it open without signal at the gym
- `manifest.webmanifest` and the icon images: home-screen name and icon

Data is saved on each phone for now. Use **Settings → Back up my data** regularly.
Syncing between phones (Supabase) comes next.

Deployed on Vercel as a static site, no build step.
