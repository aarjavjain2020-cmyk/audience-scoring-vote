# Audience scoring — voting site

This repository contains the phone-friendly audience interface. It reads the current song and closed-song results from the separate `audience-scoring-admin` site and sends scores to its API.

The site is static. Its deployment output is `dist/`. Set the admin site's HTTPS origin in `dist/config.js` for the event. The admin API must allow this site's exact origin through `AUDIENCE_ORIGIN`.

The score form accepts whole numbers from 0 to 20. A device ID is retained in browser storage for convenience; the admin API enforces one vote per device ID per song in its database. The results tab lists only closed songs. It updates every three seconds and animates changed bar heights.

The server-side device limit is a deterrent, not proof of one person per vote. Clearing browser data or using another device can produce another device ID.
