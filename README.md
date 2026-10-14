# Lift Log

A workout tracker for progressive overload, built as a home-screen web app (PWA).

- `index.html`: the whole app (logging, rest timer, history, search, templates, plate helper, sync)
- `sw.js`: lets it open without signal at the gym
- `manifest.webmanifest` and the icon images: home-screen name and icon

## Sync

Each person signs in with email + password (Settings → Sync). Everything saves on the
phone first, then copies to that person's own row in the Supabase `user_data` table.
Row-level security only lets a signed-in user read or write their own row.

Deployed on Vercel as a static site, no build step.

## Partners

Two accounts can pair (Settings → Partner). Once paired, each can read the other's
workouts (read-only), see when the other has the app open (`presence`), and react to
the other's workouts with 👍 ❤️ 💪 (`reactions`). Row-level security keeps all of this
between the two paired accounts.
