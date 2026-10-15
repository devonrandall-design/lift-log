# Pocketed ideas

Things we talked about and decided to park. Newest first within each section.

## Big ideas

### Crews: group accountability (pocketed Oct 13)
Turn pairing into small private groups so friends and family keep each other consistent.
- **Crews of 2–8**, invite only. Nobody outside the crew sees anything.
- **Personal weekly targets** (e.g. 4 sessions for one person, 2 for another). Progress is measured against your own number, so mixed levels stay on equal footing.
- **Crew board** as the home screen: who's on track this week, who's due, and a crew streak ("6 weeks in a row everyone hit their target").
- **Light social**: feed of finished workouts with one-tap reactions, PR callouts, "lifting now" presence, a gentle nudge button (max once a day).
- **Privacy per person**: share just check-ins, workout names, or full numbers.
- **Keep it encouraging**: no weight leaderboards, no shaming copy, a "rest week" toggle that pauses your target without breaking the crew streak.
- Effort: about 2–3 sessions for crews, targets, board, feed and reactions. Push notifications are a separate chunk.

### Push notifications (pocketed Oct 13)
Possible without a native app: iPhone supports push for home-screen web apps (iOS 16.4+), after each person taps "Allow notifications" once.
- **Best first use: rest timer done while the phone is locked.** Today the timer only works with the app on screen.
- Partner invites, "Kay finished Full Body B", PR shout-outs; later Crew nudges.
- Needs: notification keys, each phone's permission saved in Supabase, and a Supabase server function that sends them (on events, or scheduled for the rest timer).
- Limits: plain banners and sound only, no buttons or live lock-screen countdown. Stops if the home-screen icon is deleted.
- Effort: about 1–1.5 sessions.

### Apple Watch / Apple Health (pocketed Oct 13)
Web apps can't read Apple Health, so this needs one of:
1. **Shortcuts bridge** (~1–2 hrs, free): a Shortcut sends the latest watch strength workout (time, calories, avg heart rate) to Lift Log, matched to the session by time. One-way.
2. **Native wrapper with Capacitor** (~a day, $99/yr Apple Developer): reads heart rate/calories automatically and writes sessions to Health for Fitness rings. Built in Xcode, installed via TestFlight (re-upload every 90 days).
3. **Real Apple Watch app** (weeks): log sets and run the rest timer from the wrist.

### Renaming the app (pocketed Oct 14)
- **Display name** (home-screen label, welcome screen, tab title): a 2-minute code change. Keep it to about 12 characters so iPhone doesn't cut it off. Each person removes and re-adds the home-screen icon to see it; check Sync says "Up to date" first, then sign back in.
- **Web address**: rename the Vercel project for a free `name.vercel.app`, or buy a custom domain (~$10–15/yr). Same reinstall-and-sign-in.
- **Repo and Supabase project names**: cosmetic, optional.
- Could pair with a new icon.

## Features

- **"Working out now" for your partner**: a live card when the other person is mid-workout ("DeVon is lifting · Upper 1 · 38 min · on Bench Press"). Builds on the green online dot. ~30 min.
- **Send templates to your partner**: write a template into their account. Needs a write permission on top of today's read-only pairing.
- **Spreadsheet import**: bring in the ~185 sessions from the old sheet. Dry run first, with a "help me read these" list. Undated, so either import in order or space them out from a start date.
- **Plate shorthand entry**: type `2p 1q` in the weight box and it converts.
- **Pin-setting machines**: log `[6]`-style settings as their own unit.
- **Half and partial reps**: allow 6.5 instead of rounding.
- **Set tags**: strapped, wraps & sleeves, rolled to top, paused, partials. Tagged sets stay in history but are marked.
- **Repeat last workout** shortcut on the Workout tab.
- **Merge duplicate exercises** tool, in case one slips through.

## Open decisions
- Same exercise twice in one workout (e.g. heavy block, then back-off block): currently blocked. Allow it with a confirm?
- Should a template remember the version you used last time, or always reset to the version saved in the template?

## Small fixes and housekeeping
- **Header jumps when the keyboard opens** on iPhone (date chip floated over the clock). Pin the header properly.
- **Refresh the demo link** with hold sets.
- **Supabase**: turn off "Allow new users to sign up" once everyone's in. Consider leaked password protection.
