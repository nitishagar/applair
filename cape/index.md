---
layout: default
title: "cape — Privacy Policy"
---

# cape — Privacy Policy

*Last updated: 2026-04-25*

**cape** is a self-directed nicotine-taper tracker for adults 18 and older.

## Summary

**cape stores every piece of personal data on your device.** Nothing you enter — your starting intake, daily check-ins, craving logs, notes, milestones, or the generated taper plan — is transmitted off the device. cape has no backend server, no account system, and does not use any analytics or crash-reporting SDK.

## Data we collect

| Category | What | Where it lives | Shared? |
|---|---|---|---|
| Health & fitness | Daily nicotine intake (mg), craving intensity & timestamp, breathing-session completion | Device-local SQLite database (Android internal storage) | No |
| App preferences | Onboarding completion flags, streak counter, reminder time | Android SharedPreferences | No |
| Device-generated | Local timezone (for scheduling daily reminders) | Not persisted; used in-memory for the Android notification alarm | No |

We do **not** collect: identifiers, email, location, contacts, messages, photos, audio, or any advertising ID.

## How data is used

Data is used **only** to render your own in-app dashboards, compute your taper plan and streak, and schedule the local reminder notification. It never leaves the device.

## Third parties

cape uses the following open-source libraries. None of them transmit your data off the device in cape's configuration:

- Drift / sqlite3 — local database
- flutter_local_notifications + permission_handler — local daily reminder alarms
- shared_preferences — local key/value storage
- fl_chart, flutter_animate, confetti — UI only (no network)

cape does not integrate with any ads SDK, tracking SDK, analytics SDK, or crash-reporting SDK.

## Permissions

- **`POST_NOTIFICATIONS`** (Android 13+) — to show your daily check-in reminder.

No other runtime permission is requested.

## Your controls

- **Delete all data** — uninstall the app. Android removes all of cape's private storage on uninstall.
- **Pause reminders** — toggle in Settings → Reminder.
- **Export** — the Settings screen offers a local export of your entries as a JSON file you keep yourself.

## Not a medical device

cape is an educational tool. It is **not a medical device** and does not provide medical advice. If you are pregnant, have a heart condition, or have been advised by a physician not to reduce nicotine abruptly, consult your doctor before using cape.

## Children

cape is age-gated to users aged 18 and older. Minors should not use cape.

## Changes to this policy

Material changes will be noted in the *Last updated* line at the top of this page and called out in the app's release notes for the relevant version.

## Contact

Questions or concerns? Please open a public issue at <https://github.com/nitishagar/cape/issues>. I read every issue.
