# schedule-wallpaper

A small, self-contained HTML tool that turns your daily schedule into a clean black wallpaper — white text, laid out as a table (laptop) or a stacked list (phone) — so you can set it as your desktop/lock screen and glance at your plan all day.

No install, no build step, no backend. Just one HTML file that runs entirely in the browser.

**Live demo:** `https://<your-username>.github.io/schedule-wallpaper/`

## Features

- Add as many time + description rows as you need (default: one row, `+` to add more)
- Smart time parsing — type `9A`, `1P`, `14`, or `9:30 PM` and it auto-formats to `09:00 AM`, `01:00 PM`, `02:00 PM`, `09:30 PM`
- Optional custom title
- Choose output size:
  - **Laptop** — 1920 × 1080 (two-column table layout)
  - **Phone** — 1080 × 2392 (stacked list layout, designed separately for portrait screens)
- Generates a black-background PNG you can preview and download
- **Upload JSON** — load a schedule from a `.json` file (the upload dialog shows the exact format required)
- **Download JSON** — save your current schedule as a `.json` file, so you can back it up or re-load it later without retyping

## JSON format

```json
{
  "title": "TODAY'S SCHEDULE",
  "items": [
    { "time": "7:00 AM", "description": "Wake up & stretch" },
    { "time": "9A", "description": "Deep work block" },
    { "time": "14", "description": "Lunch" }
  ]
}
```

- `items` is required — a non-empty array
- Each item needs `time` and `description` (or `desc`) as strings
- `time` accepts flexible formats (`7:00 AM`, `9A`, `1P`, `14`, etc.) — auto-formatted on generate
- `title` is optional

## Running locally

Just open `index.html` in any modern browser — no server needed.

## Hosting for free on GitHub Pages

1. Push this repo to GitHub (keep it public for free Pages hosting).
2. Go to **Settings → Pages**.
3. Under "Build and deployment," set Source to **Deploy from a branch**, pick `main` and the `/` (root) folder, then Save.
4. Your site goes live at `https://<your-username>.github.io/schedule-wallpaper/` within a minute or two.

## Tech

Plain HTML, CSS, and JavaScript. Uses the Canvas API to render the wallpaper image and the Blob/File APIs for JSON import/export. Fonts (Poppins, JetBrains Mono) are loaded from Google Fonts CDN.
