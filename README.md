# LOCKIN — Android-installable PWA

LOCKIN is a local-first discipline, faith, accountability, and life-management app.

## Included
- Daily command center, commitments, progress ring, and streak display
- Urge intervention with trigger selection and a 10-minute reset timer
- Accountability logging and non-shaming lapse reflection
- Scripture library, saved verses, prayer journal, and faith reflections
- Motivational quotes
- Life dashboard for faith, learning, fitness, programming, social life, and rest
- Weekly review, activity log, and simple analytics
- Notification preferences, in-app notification permission request, and progress notifications
- Local data export/import and reset
- Service worker offline cache and installable manifest

## Install on Android
1. Deploy this folder to an HTTPS host (for example, a static hosting provider).
2. Open the HTTPS URL in Chrome on Android.
3. Use Chrome's menu → **Install app** or **Add to Home screen**.
4. Open LOCKIN from the home screen.
5. In Settings, enable notifications and choose reminder times.

A PWA must be served over HTTPS (or localhost during development) for service workers and installation.

## Important notification limitation
This version can send progress notifications immediately and schedule reminders while the app's page is active. Android may suspend or terminate a browser/PWA in the background, so JavaScript timers are **not reliable for exact scheduled notifications when the app is closed**. The included service worker can receive push notifications, but dependable closed-app delivery requires a push backend (Web Push/VAPID) or a native Android wrapper with Android AlarmManager/WorkManager. Do not treat the current timer scheduler as guaranteed alarms.

## Data and privacy
Data is stored in this browser's localStorage. It is not synced to a server. Clearing browser/site storage or uninstalling may erase it. Use Export Backup regularly. This is not a clinical treatment tool or a substitute for a trusted person or professional support.

## Run locally
For development, serve the directory from localhost, e.g.:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.
