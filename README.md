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

## Deploying Firebase rules

The site works in solo mode (via localStorage) out of the box. To enable live multi-user sync:

```bash
cd ~/Code/projects/jack-bday-nyc
firebase login                          # one-time browser auth
firebase deploy --only database         # pushes database.rules.json
```

Once rules deploy, the green "live" dot in the top bar lights up and changes sync across all users in real time.

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
