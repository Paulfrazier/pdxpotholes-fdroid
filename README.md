# PDX Potholes — personal F-Droid repo

Hosts the [PDX Potholes](https://github.com/Paulfrazier/pothole-reporter) Android app as a
self-built **F-Droid repository** so it can be installed and auto-updated through the F-Droid
client. Published to GitHub Pages at
**https://paulfrazier.github.io/pdxpotholes-fdroid/**.

## How it works

- `apks/app-release.apk` — the signed release APK (built by CI in the app repo, signed with the
  stable release key).
- `.github/workflows/pages.yml` — installs `fdroidserver`, signs a repo index with the same
  release key (so the repo fingerprint is stable), and deploys `repo/` + a landing page to Pages.

## Updating to a new app version

1. Build a new signed APK in the app repo (bump `versionCode`/`versionName`).
2. Replace `apks/app-release.apk` here and push. CI regenerates the repo; F-Droid clients see an
   in-place update (same signing key).

## Add it on a phone

Open https://paulfrazier.github.io/pdxpotholes-fdroid/ in the phone browser and tap
**Add this repo to F-Droid** (the page carries the repo URL + signing fingerprint).
