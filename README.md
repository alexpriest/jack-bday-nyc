# Jackhattan

Jack's birthday week planning site — June 5–11, 2026. NYC + Westchester.

**Live:** https://prjcts.alxprst.co/jack-bday-nyc/

## What it does

- **Hour-by-hour calendar grid** — Notion/Cron-style time view per day. Drag events between days, or up/down to retime (snaps to 15 min). Same-day overlap detected and auto-laid-out in lanes.
- **List view** — card-stack alternative for fast rearranging.
- **Day range filter** — zoom to weekend only, weekdays, adults-only, or just the Vanguard day.
- **Candidates pool** — alternative activities not in the plan. Drag any candidate directly into a calendar day, or use "+ Add" on the comparison-table rows to promote spots into the pool.
- **+ Custom activity** — add anything that's not in the preset library (specific dinners, kid events, late additions) without code changes.
- **Per-day notes** — text area per day for questions, reminders, who's coming. Synced.
- **Comparison tables** — restaurants / bars / spas. Duckbill's picks highlighted gold, Kit's picks green, with verdicts and Michelin star counts.
- **Stone Barns countdown** — banner timing the moment Resy reservations open (Fri May 15, 7am ET on a rolling 30-day window).
- **Travel hints** — events in NYC show transit time from White Plains.
- **Adults-only / Family / Mixed day tags** — clear at a glance which days need childcare.
- **Live multi-user sync** — Firebase Realtime DB. Presence avatars in the top bar, plan state synced across everyone with the link.

## Stack

- Single-file `index.html` (no build step)
- Firebase Realtime Database (reuses `stoweaways-2026` project under `jack-bday/*` namespace)
- SortableJS for drag-and-drop in list view
- Native HTML5 D&D for calendar
- GitHub Pages hosting

## Firebase setup

**No deployment needed.** The app uses existing Stoweaways Firebase rule paths with namespaced keys:
- Presence: `/users/jbn-<uid>` (existing `/users/$uid` rule allows write)
- Plan state: `/checklist/jackhattan-plan/<uid>` (existing checklist rule allows string write per uid)

Both work immediately against the live `stoweaways-2026` project — no `firebase deploy` required. The green "live" dot in the top bar should light up as soon as anyone has the page open.

The `database.rules.json` file in this repo is a documentary copy showing what dedicated rules would look like — kept for future reference if you ever want to migrate to dedicated paths. Not currently used.

## Local dev

```
open index.html
```

Changes save automatically to localStorage. Edit, refresh, commit, push — GitHub Pages rebuilds in ~30 seconds.

## Anchors

- **Sun 6/7 8pm** — Kurt Rosenwinkel Quintet @ Village Vanguard (locked, tickets via Miranda)
- **Fri 5/15** — Stone Barns Resy opens (book Wed 6/10 or Thu 6/11)
- **Tue 6/9** — Le Bernardin lunch (Resy 1st-of-month drop already in window)
- **Sun 6/7 afternoon** — Bathhouse Flatiron spa
