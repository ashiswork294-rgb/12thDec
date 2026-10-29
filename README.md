# BarReady

BarReady is a local-first, responsive study planning web app for Nepal Bar Council exam preparation. It uses semantic HTML, CSS, vanilla JavaScript, and Chart.js from a CDN (with a graceful no-chart fallback). There is no backend, build step, or API key.

> **Important:** Starter syllabus topics and sample MCQs are illustrative planning content, not a definitive official syllabus or verified official Nepal Bar Council questions. Confirm examination dates, syllabus and legal content using current official sources.

## Files

- `index.html` — app structure and navigation
- `style.css` — responsive visual system, light/dark themes
- `app.js` — application state, timers, CRUD, charts, import/export
- `README.md` — setup and deployment instructions

## Run locally

1. Download and unzip the BarReady archive.
2. Open `index.html` in a modern browser. Most features work without a local server.
3. If your browser restricts local file behavior, run a static local server from this folder, for example:
   - Python: `python3 -m http.server 8000`
   - Then visit `http://localhost:8000`.

Internet access is needed for the Google Fonts and Chart.js CDN assets. The app itself and its core records run locally; charts degrade gracefully if Chart.js cannot load.

## Deploy on GitHub Pages

1. Create a new GitHub repository, for example `barready`.
2. Upload `index.html`, `style.css`, `app.js`, and `README.md` to the repository root.
3. Open the repository **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select your main branch and the `/ (root)` folder, then save.
6. Wait for GitHub Pages to publish the site and open the URL it provides.

No build process or backend is required. Whenever you update the source files and push them to the selected branch, Pages republishes the static site.

## Data, backups and privacy

- Records are stored in `localStorage` in the browser profile and origin where you use BarReady.
- Use **Settings & data → Export JSON** regularly to download a backup.
- To restore a backup, choose the JSON file under **Import backup**. BarReady validates the basic data shape and asks before replacing existing records.
- Import replaces the current app data in that browser. Export first if you need both copies.
- **Reset data** deletes current local app data after confirmation.
- Data does not sync between devices, browsers, profiles, or different Pages origins. Clearing browser data may delete it. This app does not send your study data to a server.

## Features

- Dashboard with dynamic local-date countdown and study time today
- Pomodoro, short focus, 50-minute, custom countdown, and stopwatch modes
- Timer-recorded sessions and manual/offline study logs
- Editable sample subjects and syllabus topics with status, priority, notes, search and filters
- Daily/weekly study tasks and revision scheduling
- MCQ question bank, answer feedback, explanations and attempt history
- Subjective practice tasks with saved drafts and optional self-reflection
- Analytics based on saved sessions, date-range filters and session history
- Session editing/deletion, JSON import/export, configurable exam dates, daily target and theme
- Responsive desktop sidebar and mobile navigation

## Notes and limitations

- The initial exam dates are set to December 12–13, 2026, and can be edited in Settings.
- The countdown uses the browser's local calendar date. Timer sessions are saved when you select **Finish & save**; a completed countdown does not silently create a session. Resetting or pausing never logs time.
- Timer elapsed time is measured by interval ticks while the page is active; this simple static implementation does not guarantee precise catch-up if the tab or browser is suspended. For best results, keep the tab open during a session.
- Chart.js is loaded from a CDN; if it is blocked or unavailable, chart panels show a fallback message and saved totals/history remain usable.
- Data import checks key arrays and session records, but it is not a cryptographic or exhaustive schema validator. Only import backups you trust.
- No cloud sync, accounts, legal advice, authoritative legal grading, or official question verification is provided.
- Use current official exam notices and legal primary sources to verify exam dates, syllabus and substantive legal material.

## QA checklist for a first run

- Open each sidebar section and verify the active page changes.
- Start a timer, pause, resume, reset, then finish and save a session.
- Add a manual study log; confirm the dashboard, history and analytics reflect it once.
- Edit and delete a session; confirm totals recalculate.
- Add and update a syllabus topic and planner task.
- Export JSON, import it after confirmation, and test reset only after backing up.
- Test the mobile navigation at a narrow viewport.
