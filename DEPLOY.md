# BMO2026 NHL Pool Tracker — Deployment Package

## Season dates
- Regular season start: **September 29, 2026** (inclusive)
- Regular season end: **April 10, 2027** (inclusive)
- NHL game type: **2 — regular season only**
- Preseason and playoffs are never scored.

## Current roster data
This package contains **19 participants**, each with **27 picks**, for **513 roster spots**.

## Local run
```bash
npm install
npm start
```
Then open `http://localhost:3000`.

## Render
Use the repository root as Render's Root Directory. Build command:
```text
npm install
```
Start command:
```text
npm start
```
Node runtime. Free web service is sufficient for the tracker.

## Environment variables
- `PORT` — provided by Render automatically.
- `NHL_API_BASE` — optional; defaults to `https://api.nhle.com/stats/rest/en`.
- `ADMIN_PASSPHRASE` — optional; defaults to `bmo2026admin`.
- `REFRESH_TOKEN` — optional protection for the manual refresh API.

## Before opening day
The tracker builds a roster-only baseline from the 19 supplied rosters. All 513 roster spots are visible and have 0 NHL points. No NHL stats are fetched before September 29.

## On opening day
At/after September 29, the normal NHL sync becomes active. The scheduled refresh runs at 6:00 AM America/Toronto, and the Refresh button can be used after a game night.

## Data persistence
SQLite is stored in `pool.db`. For production, attach persistent storage if the hosting provider/service plan supports it; otherwise the service filesystem can reset on replacement/redeploy.
