# SAT Canvas Studio Cloud

A GitHub Pages-ready SAT scratchpad app with:

- Khan-style drawing canvas
- paste / drag images onto the canvas
- move and resize pasted images
- Google Drive save through Google OAuth
- Google Drive autosave after the first cloud save
- local download/open backup
- College Board Desmos tab
- SAT reference sheet tab

## 1. Create a GitHub repo

Upload these files to a GitHub repository:

- `index.html`
- `config.js`
- `README.md`

Then enable GitHub Pages from the repository settings.

For a project site, the final URL usually looks like:

`https://YOUR-USERNAME.github.io/YOUR-REPO/`

The OAuth origin you register with Google is only the origin part:

`https://YOUR-USERNAME.github.io`

## 2. Create the Google OAuth Client ID

1. Go to Google Cloud Console.
2. Create/select a project.
3. Enable the Google Drive API.
4. Configure the OAuth consent screen.
5. Create credentials → OAuth Client ID → Web application.
6. Add Authorized JavaScript origins:
   - `https://YOUR-USERNAME.github.io`
   - Optional for testing: `http://localhost:8080`
7. Copy the client ID.
8. Paste it into `config.js`.

## 3. Test locally before GitHub Pages

Run a local server in this folder:

```bash
python3 -m http.server 8080
```

Open:

`http://localhost:8080`

Do not test Google sign-in from a raw `file://` path.

## 4. How saving works

- Click **Sign in with Google**.
- The first cloud save creates `SAT Canvas Studio Project.satcanvas` in Google Drive.
- After that, edits autosave to the same Drive file during that browser session.
- Use **Download Copy** sometimes as a safety backup.

## Note

For your own personal use, keep the Google OAuth app in testing mode and add your Google account as a test user if Google asks. If you want other people to use it widely, Google may require extra OAuth app verification depending on the scopes and publishing setup.
