# rewatchman-site

Personal site and OTA hosting for my projects. Lives at [rewatchman.com](https://rewatchman.com).

## What's here

**`index.html`** — the main site. A single-page portfolio with an about section, project cards, resource links, and a support section.

**`olive-branch/`** — static file hosting for the Olive Branch app's over-the-air database updates.
- `bible.db` — the SQLite Bible database served to the app
- `bible-version.json` — version manifest checked by the app on startup

## OTA Update Workflow

The Olive Branch app checks `bible-version.json` at launch. If the version is newer than what's installed, it downloads the updated `bible.db` automatically.

To push a new database version:
1. Build or update `bible.db` using the migration scripts in the [Olive Branch repo](https://github.com/sanoski/Olive-Branch-alpha)
2. Upload the new `bible.db` to the `olive-branch/` folder via the hosting panel
3. Bump the version number in `olive-branch/bible-version.json` and push to this repo

## Projects on the site

- [Olive Branch](https://github.com/sanoski/Olive-Branch-alpha) — offline Bible reader (React Native)
- [TimeWizard](https://github.com/sanoski/TimeWizard) — offline timesheet tracker (React Native)
- [Bible Study Tracker](https://github.com/sanoski/Bible-Study-Tracker) — terminal Bible reading tracker (Python)
- **VRS MOW Tracker** *(private)* — web app for tracking railroad tie installation. Logs daily counts, equipment downtime, and crew progress. Generates weekly PDF reports. Administered via Claude AI over MCP. Stack: Python, FastAPI, SQLite, ReportLab, FastMCP.
- **Yardmaster** *(private)* — self-hosted on-call scheduling system for a railroad MOW crew. Handles weekly rotation, per-person email notifications, and swap requests via email reply. Stack: Python, FastAPI, SQLite, APScheduler, IMAP/SMTP.
- **XGPS** *(internal)* — field tool for railroad signal maintainers. Locates grade crossings, provides directions, and references shutdown procedures. Fully offline. Stack: React Native, SQLite, OpenStreetMap, Leaflet.js.
