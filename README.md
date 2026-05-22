# WhatsApp Chat Viewer Web App

This is a Flask web app that converts a WhatsApp-exported .txt file into a visually similar, searchable HTML chat mimicking WhatsApp UI.

## Features

- Upload .txt chat export and optional media zip.
- Displays chat in WhatsApp-like bubbles with avatars, timestamps, and authors.
- Supports images, videos, and file attachments (displays/links them).
- Phone-like UI mockup for authentic feel.
- Sent messages (green, right-aligned) vs received (white, left-aligned) based on your name.
- Dark mode for WhatsApp dark theme.
- Long-press (hold 1 second) on messages to view full date/time info.
- Feels like reading old chats with scroll and layout.
- Print to PDF directly from browser for exact WhatsApp lookalike.

## Setup

This repository now includes a static GitHub Pages version in `index.html`, `styles.css`, and `script.js`.

### Static site

1. Open `index.html` in any browser.
2. Upload your exported WhatsApp `.txt` file or paste the exported text.
3. Select your identity and view the chat in WhatsApp style.
4. This version works on GitHub Pages because it does not require a Python backend.

### Flask app

If you want the backend Flask version instead, use:

1. Install dependencies: `pip install -r requirements.txt`
2. Run the app: `python app.py`
3. Open http://127.0.0.1:5000 in browser.

## Deployment

This app is ready to deploy on Render or any Python web host.

- Ensure `requirements.txt` includes Flask and gunicorn.
- Use `Procfile` with `web: gunicorn app:app --bind 0.0.0.0:$PORT`.
- Add `runtime.txt` with the Python version.
- Push the repo to GitHub and connect it in Render.

## Notes

- Assumes UTF-8 text encoding.
- The app auto-detects message authors from the chat export.
- Google Drive paste link support allows the site to download the `.txt` directly.
- Media `.zip` files are extracted and served from the app's media folder.
