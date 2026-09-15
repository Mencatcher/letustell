# hayknz site

## Adding a new track (this is the only workflow you need)

1. Open `tracks.json`.
2. Copy one entry and edit it:
   ```json
   {
     "id": "new-track-id",
     "title": "New Track",
     "description": "Official visual for New Track by hayknz.",
     "video": "newtrack.mp4",
     "color": "#0f6e56"
   }
   ```
   - `id` must be unique, lowercase, no spaces (used in the URL).
   - `video` must match the exact filename (and exact capitalization) of the
     video file you place in this same folder.
3. Put the video file in this folder (same level as `index.html`).
4. Run:
   ```
   python3 build.py
   ```
   This creates `track-new-track-id.html` and refreshes `tracks-data.js`
   automatically.
5. Upload/commit: the video file, the updated `tracks.json`, the new
   `track-new-track-id.html` file, and the refreshed `tracks-data.js`.
   The homepage grid reads `tracks-data.js` directly — you never edit
   `index.html` by hand to add a track.

## Previewing on your own computer

Just double-click `index.html` — it works straight from the unzipped
folder, no local server needed. (Earlier drafts used `fetch()` to load
track data, which browsers block for local files; this version loads
`tracks-data.js` as a plain script instead, which isn't affected by that
restriction.)

## Before going live

Replace `REPLACE-WITH-YOUR-DOMAIN.com` in `index.html` and
`track-template.html` with your real domain, then re-run `python3
build.py` so the generated pages pick up the change.

## Keep everything in one folder

All files — `index.html`, `styles.css`, the videos, the images, and every
`track-*.html` — must stay in the same folder, flat (no subfolders). If
your zip tool ever creates a subfolder on extract, move everything back up
to one level before uploading.

## Known open item

`whit.png` / `whitee.png` are blank/near-white images in the current
upload — worth swapping for real photos before publishing.
