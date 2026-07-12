# ஸ்ரீ சுயம்பு குரூப்ஸின் — வாடிக்கையாளர் பதிவு
## Hosting Instructions (இதை இணையத்தில் ஏற்ற வழிமுறைகள்)

This folder contains everything needed to host the app as a real website:
- `index.html` — the app itself
- `manifest.json` — lets mobile users "install" it as a home-screen app
- `icon-192.png`, `icon-512.png` — app icons

Note: this version does **not** include an offline service worker (`sw.js`). An earlier
version had one to work offline, but it was causing phones to keep showing an old cached
copy of the app even after updates were uploaded — which looked like bugs "coming back."
Since a reliable internet connection is available when using the app, it's simpler and
safer to always load the current file directly. (`index.html` also actively removes any
old service worker a phone may have installed from a previous version, so this fixes
itself automatically the first time someone opens the updated link.)

**Why host it instead of just opening the file?**
- Android/Chrome shows a "this file is not safe" warning for HTML files opened directly (e.g. shared via WhatsApp). Hosting it as a real website removes this warning completely.
- Microphone permission is only remembered permanently by the browser when the site has a real address (https://...). Opening it as a local file cannot reliably remember the permission — this is a browser security rule, not something fixable in code.
- Once hosted, agents can open the link once, tap "Add to Home Screen," and use it like a normal app icon from then on.

---

## ✅ Recommended: GitHub Pages (100% free, forever, no time limit)

1. Go to **github.com** and create a free account (if you don't have one).
2. Click the **+** icon (top right) → **New repository**.
   - Name it anything, e.g. `srivelan-nagar-crm`
   - Set it to **Public**
   - Click **Create repository**
3. On the new repository page, click **"uploading an existing file"** (or drag-and-drop).
4. Drag in all 4 files from this folder: `index.html`, `manifest.json`, `icon-192.png`, `icon-512.png`.
5. Click **Commit changes**.
6. Go to the repository's **Settings** tab → **Pages** (left sidebar).
7. Under "Build and deployment" → Source, choose **Deploy from a branch**, Branch: **main**, Folder: **/ (root)** → **Save**.
8. Wait ~1 minute, then refresh — GitHub will show your live link, something like:
   `https://yourusername.github.io/srivelan-nagar-crm/`
9. Open that link on your phone in **Chrome**. Tap the mic once, allow permission — it will now be remembered permanently.
10. Optional: tap Chrome's menu (⋮) → **"Add to Home screen"** — the app icon appears on the phone like a normal app, no browser address bar.

This link works forever, for free, from any phone, anywhere with internet.

---

## Alternative: Netlify

Netlify also offers free hosting, but a site created without signing in is deleted after **1 hour** unless you create a free account and "claim" it right after uploading. If you'd rather use Netlify:
1. Go to **app.netlify.com** and sign up free.
2. Drag this whole folder onto the Netlify dashboard's drop zone.
3. Netlify gives you a live `https://yoursite.netlify.app` link immediately — since you're signed in, it stays live permanently.

---

## Updating the app later
If you ever want changes made to the app, just replace `index.html` in the repository (or Netlify folder) with the new version and it updates instantly — the link stays exactly the same, so nobody has to change bookmarks or reinstall.
