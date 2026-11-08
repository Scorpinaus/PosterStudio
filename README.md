# Poster Studio — local development package

Source snapshot: 8 November 2026. Start here after extracting the ZIP.

This package contains the website source corresponding to saved Sites version 11 and a copy of the installed Poster Studio skill. The website and skill files are unchanged. Package-only launch tools and documentation are added alongside them. The planned critique/iteration upgrade has NOT been implemented.

## Start the editor on Windows

1. Install Node.js 22.13 or newer if it is not already installed. Check with `node --version`.
2. Extract the entire ZIP into a normal folder, for example `C:\dev\Poster_Studio_Local_Development`. Do not run it inside the ZIP viewer.
3. Double-click `Start_Local_Editor.cmd`, or open a terminal in this folder and run:

```powershell
node tools/local-editor.mjs
```

4. Open **http://127.0.0.1:8080** in your browser. Keep the terminal open; press Ctrl+C to stop.

This mode needs no `npm install`, Cloudflare account, ChatGPT sign-in, or external server. Bundled fonts, OCR files, and PDF dependencies are included. Node.js and a modern browser must already be installed for use without internet. This is a local web application, not an installed desktop application or an offline AI assistant.

The launcher omits the hosted-chat controls from the HTML it serves, without editing the original HTML file. Manual editing, browser-local projects, import tools, and Canvas exports use the existing editor code. Source changes appear after browser refresh.

## Contents

| Path | Contents |
| --- | --- |
| `website/` | Complete tracked website source, lockfile, tests, migrations, bundled assets, and server code |
| `skills/poster-studio/` | Installed skill snapshot, interface metadata, and icon |
| `tools/` | Dependency-free local editor launcher and its HTTP smoke test |
| `docs/LOCAL_DEVELOPMENT.md` | Editor-only and full backend development instructions |
| `docs/SKILL_DEVELOPMENT.md` | Skill editing and hosted-versus-local tool limitations |
| `docs/VERSION_CONTROL.md` | Start a private repository and coordinate releases |
| `docs/CRITIQUE_WORKFLOW_PLAN.md` | Planned enhancement, clearly separated from implemented code |
| `SOURCE_MANIFEST.json` | Exact source identifiers and skill fingerprint |
| `FILE_CHECKSUMS.sha256` | Hashes for all package files except the checksum list itself |
| `VERIFICATION.md` | Checks run and limits of verification |

## Bring your posters across

This is a source package, not a backup of your poster projects. Open the online editor, then use **Project → Back up project with history** for each project you want. On the local editor, choose **Project → Import project file** and select that backup. For hosted projects, first open their local editing copy in the online editor, then back it up.

Browser storage is tied to the exact origin. `127.0.0.1:8080`, `localhost:8080`, a different port, and the online website have separate drafts. Keep using the same address and browser, and export backups before clearing browser data. The local version does not automatically synchronize with the website.

## What is not included

No credentials, personal poster projects, production database or object-storage contents, installed Node dependencies, or original Git repository history are included. `SOURCE_MANIFEST.json` records provenance; initialize your own Git history using the guide. The hosted skill still needs its connected online tools. No live website deployment or installed skill update was performed to create this package.

See `docs/LOCAL_DEVELOPMENT.md` for developing the complete backend rather than only the editor.
