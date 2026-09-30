# Audience scoring — voting site

**[Open the audience site](https://aarjavjain2020-cmyk.github.io/audience-scoring-vote/)** · **[Open the administrator site](https://audience-scoring-admin-aj2020.aarjavjain2020.workers.dev)**

This repository contains the phone-friendly audience interface. GitHub Pages publishes `dist/`. It reads the current song and closed-song results from the separate [audience-scoring-admin](https://github.com/aarjavjain2020-cmyk/audience-scoring-admin) Cloudflare Worker and sends scores to its API.

Set the admin Worker's HTTPS origin in `dist/config.js` for the event. The admin API must allow the GitHub Pages origin `https://aarjavjain2020-cmyk.github.io` through `AUDIENCE_ORIGIN`.

The score form accepts whole numbers from 0 to 20. A device ID is retained in browser storage for convenience; the admin API enforces one vote per device ID per song in its database. The results tab lists only closed songs. It updates every ten seconds and animates changed bar heights.

The competition has four audition days and a Day 5 final. Contestant IDs distinguish identical names. The results tab offers each day, combined auditions, and the final. Charts default to averages out of 20; the gray toggle shows totals on this page only. The table always shows averages and vote counts. Finalists are marked after the administrator confirms the combined top 10 or 15 and any ballot choices at the cutoff. Final votes start from zero and are separate from auditions. No minimum vote count applies; zero-vote averages are shown as a dash.

The server-side device limit is a deterrent, not proof of one person per vote. Clearing browser data or using another device can produce another device ID.
