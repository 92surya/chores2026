# Chores

A single-page chores tracker. The live app is [GitHub Pages](https://92surya.github.io/chores2026/). After you sign in with Google, chores are stored in **`chores-tracker-data.json`** in your Drive, so Safari, Chrome, laptop, and phone all show the same list.

`localStorage` is only a cache for that browser. Opening the HTML file from disk (`file://`) cannot share data across browsers, and Google sign-in requires the https Pages URL.

## Files

| File | Role |
| --- | --- |
| `index.html` | What GitHub Pages serves. Keep identical to the latest tracker. |
| `chores-tracker_5.html` | Current version. Edit this (or a new `_6`), then copy to `index.html`. |
| Older `chores-tracker*.html` | Leave alone unless you still need a Safari backup from `_4`. |

## First-time setup

### 1. Google Cloud (once)

1. Create a project in [Google Cloud Console](https://console.cloud.google.com/).
2. Enable **Google Drive API**.
3. OAuth consent screen → External. Add your Gmail as a **test user** (enough for personal use).
4. Credentials → OAuth client ID → **Web application**.
5. Authorized JavaScript origins (origin only, no path): `https://92surya.github.io`
6. Copy the client ID (`….apps.googleusercontent.com`).

Paste it into `EMBEDDED_GOOGLE_CLIENT_ID` in both `chores-tracker_5.html` and `index.html`, then push. You can also paste it under **Data** in the app for the current browser.

### 2. GitHub Pages

Repo **Settings → Pages → Deploy from branch → `main` / `/ (root)`**.

### 3. Move existing Safari chores

1. Open `chores-tracker_4.html` in Safari and click **Download backup**.
2. Open the Pages URL, **Data → Sign in with Google** (creates the Drive file).
3. **Data → Import backup** and choose that JSON file.

## Using it

Sign in on each new browser once. Edits debounce-save to Drive. **Data** also has download/import backup. Last write wins if two devices save at the same time.
