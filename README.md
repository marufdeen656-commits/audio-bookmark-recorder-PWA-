AUDIO BOOKMARK RECORDER
=======================
A voice recorder that works offline. Mark highlighted (yellow) segments while
recording or during playback, jump to any segment, loop it, and export notes.

FILES IN THIS PACKAGE
  index.html               the whole app (HTML, CSS and JavaScript in one file)
  manifest.json            makes the app installable
  sw.js                    service worker (offline support)
  icon-192.png, icon-512.png, icon-maskable-512.png, apple-touch-icon.png

IMPORTANT: HOSTING (READ THIS FIRST)
  Browsers only allow microphone access and offline installation on a secure
  page. That means the app MUST be served over HTTPS (or from localhost).
  Opening index.html directly from a folder or file manager will NOT allow
  the microphone. This is a browser rule, not a bug.

  Easy ways to host it (all free, all HTTPS):
    1. Netlify Drop: go to app.netlify.com/drop and drag the unzipped folder in.
    2. Cloudflare Pages or GitHub Pages: upload all the files.
    3. Any web host with an SSL certificate: upload all the files to one folder.

  Upload ALL files, keeping them in the same folder.

  To test on your computer:
    Open a terminal in the unzipped folder and run:  python3 -m http.server
    Then open http://localhost:8000

HOW TO USE
  1. Open your hosted link and tap the red button to record. Allow the microphone.
  2. Tap the yellow flag once to start a segment, tap again to lock it.
  3. Tap a segment to jump to it. Use the loop button to repeat it.
  4. Library button: all saved recordings. Settings: label prefix, skip interval.
  5. "Load Sample Memo" adds a demo recording so you can try the player.
  6. "Export Notes" downloads your segments as a Markdown file.

INSTALL AS AN APP
  Android (Chrome): menu > Install app / Add to Home screen.
  iPhone (Safari): Share button > Add to Home Screen.
  Desktop (Chrome/Edge): install icon in the address bar.

OFFLINE
  After the first visit over HTTPS, the app is cached and opens without
  internet. Recordings are stored on the device in the browser (IndexedDB).

NOTES AND LIMITS
  - Recordings stay on the device. Clearing browser data deletes them.
    Back up important recordings.
  - Recording format depends on the browser (WebM on Chrome/Android/desktop,
    MP4 on Safari/iPhone).
  - If you edit any file after publishing, change CACHE_VERSION at the top of
    sw.js (for example 'v1' to 'v2') so returning users receive the update.
  - Microphone permission is chosen by the user in the browser. It cannot be
    bundled in a zip file.

BROWSER SUPPORT
  Current Chrome, Edge, Firefox, and Safari (iOS 14.5+/macOS) with HTTPS.
