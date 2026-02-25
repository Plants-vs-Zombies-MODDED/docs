---
icon: brackets-curly
---

# API Reference

Welcome to the API reference for the Plants vs. Zombies: MODDED level sharing platform. It supports uploading, downloading, browsing, favoriting, and reporting levels. It also supports admin moderation and metadata edits.

* Source repo: [https://github.com/ROBlNET13/pvzm-backend](https://github.com/ROBlNET13/pvzm-backend)
* Production base URL: `https://backend.pvzm.net`
* All routes are under `/api/*`

### Rate limits

The API returns HTTP `429` with a `Retry-After` header. The error body may include `retryAfterSeconds`.

Documented limits in the schema:

* Upload level: **1 per 60 seconds per I**
* Download level: **5 per 5 seconds per IP**
* Toggle favorite: **30 per 10 seconds per IP**
