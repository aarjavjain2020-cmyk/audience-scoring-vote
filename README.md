# Audience scoring — voting site

**[Open the audience site](https://aarjavjain2020-cmyk.github.io/audience-scoring-vote/)** · **[Open the administrator site](https://audience-scoring-admin-aj2020.aarjavjain2020.workers.dev)**

This repository contains the phone-friendly audience interface. GitHub Pages publishes `dist/`. It reads the current song and closed-song results from the separate [audience-scoring-admin](https://github.com/aarjavjain2020-cmyk/audience-scoring-admin) Cloudflare Worker and sends scores to its API.

Set the admin Worker's HTTPS origin in `dist/config.js` for the event. The admin API must allow the GitHub Pages origin `https://aarjavjain2020-cmyk.github.io` through `AUDIENCE_ORIGIN`.

The score form accepts whole numbers from 0 to 20. A device ID is retained in browser storage for convenience; the admin API enforces one vote per device ID per song in its database. The results tab lists only closed songs. It updates every ten seconds and animates changed bar heights.

The server-side device limit is a deterrent, not proof of one person per vote. Clearing browser data or using another device can produce another device ID.
