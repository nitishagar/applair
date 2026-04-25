---
layout: default
title: "cape — Play Store Data Safety"
---

# cape — Google Play Data Safety Declaration

This page is the source of truth for the **Data Safety** section of the cape Play Store listing. Copy the values below into the Play Console when prompted.

## Data collection & sharing summary

| Question | Answer |
|---|---|
| Does the app collect or share any user data? | **Yes** (stored on-device only; not transmitted) |
| Is all of the user data collected by the app encrypted in transit? | **N/A — no data leaves the device** |
| Do you provide a way for users to request that their data be deleted? | **Yes — uninstalling the app removes all app-local data** |

## Data types collected

| Category / Type | Collected | Shared | Processed ephemerally | Required / Optional | Purposes |
|---|---|---|---|---|---|
| Health & fitness → Health info (nicotine mg, craving intensity) | Yes | No | No | Required | App functionality |
| App activity → App interactions (streak, breathing-session completion) | Yes | No | No | Required | App functionality |
| Personal info → Other (free-text note on check-ins and cravings) | Yes | No | No | Optional | App functionality |

Note: "Collected" in Google's terms here means "the app records this on device." None of it is sent to any server.

## Security practices

- ✅ Data is encrypted in transit — **N/A (no transmission)**
- ✅ You can request data be deleted — **users can uninstall to remove all data**
- ✅ Committed to Play Families Policy — N/A (adults only, 18+ age gate)
- ✅ Independent security review — **No** (solo developer, open-source app)

## Third-party SDKs

cape integrates **no** analytics, advertising, tracking, crash-reporting, or identity SDKs.

## Links

- Full privacy policy: <https://nitishagar.github.io/privacy/cape/>
- App source: <https://github.com/nitishagar/cape>
- Issues / contact: <https://github.com/nitishagar/cape/issues>
