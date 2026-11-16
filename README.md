# AeroPilot releases

Windows installers, signed update feeds and release notes for AeroPilot Flight Deck.

## Download

[AeroPilot 0.4.0 preview](https://github.com/m2r4kkmkzj-lgtm/aeropilot-releases/releases/tag/v0.4.0)

Download the installer from the link in the release description (it is not attached under Assets):
[AeroPilot-0.4.0-Setup.exe](https://raw.githubusercontent.com/m2r4kkmkzj-lgtm/aeropilot-releases/v0.4.0/installers/AeroPilot-0.4.0-Setup.exe)

- Size 1,212,416 bytes
- SHA256 `04208f44e67262b2835cedb2dc7b56e9021f4b55418ac8c4c185aad8f105c10b`

Close AeroPilot while safely parked before installing. Setup installs for your Windows account and creates an **AeroPilot** desktop shortcut.

Launch with that shortcut. It checks the signed preview channel before starting the app. Verified newer releases install into a new version folder and the previous version is kept. A running controller is never replaced. Opening a version folder's AeroPilot.exe directly skips the update check. Network availability and GitHub caching can delay update discovery.

Earlier preview installations can update to 0.4.0 through the signed preview channel on the next shortcut launch.

## What is included

- The AeroPilot Design 8.2 interface with its own version display (v0.4.0), and cleaner wording in the app and map.
- The existing flight controller, account and connected services. Their attribution and data-sharing disclosures are kept in **Settings → Sharing, connected services & third-party notices**.
- Per-user setup, a desktop shortcut and a Windows installed-app entry.
- RSA-signed HTTPS launch-time updates, version backups and command-line rollback.
- Uninstall registration. Flight logs, profiles and version backups are kept for recovery.

Default installation: `%LOCALAPPDATA%\AeroPilot`. Errors during update checks are written to `update.log` there. While AeroPilot is closed, the launcher supports `--rollback`, `--resume-updates` and `--uninstall`. Rollback pauses updates so the rejected release isn't immediately restored.

## Qualification

0.4.0 contains Claude’s engine98/Fix18 package (EXE6EEFA6DB,helperD2297D72): A350 graded bend speeds, straight-line cross-track hold, revised steering/look-ahead/tight-turn rolling thrust, runway taxi-route fallback and revised flare pitch. Desktop map names/borders, version display, logo fix and stock Vision Jet profile are retained.

Fix17 completed LEMD pushback and about six minutes of taxi-out before MSFS exited. Fix18 and revised landing behavior are NOT flight-qualified. This preview was published at the user’s explicit request; no A350 Final promotion. Vision Jet profile presence/earlier local selection do not establish flight qualification.

84/84 automated checks PASS during publication;72source manifest hashes verified; Claude recorded isolated installation PASS. Published HTTPS feed RSA signature, installer size and SHA256 verified. No new simulator flight or main-install update performed. Second clean-PC/dependency acceptance, Authenticode signing and representative multi-aircraft flight qualification remain incomplete.

The hosted flight-tracking website is a separate service. This repository contains no personal telemetry, account credentials, private signing keys or development source.

The signed preview feed is `channels/preview.json`. The public verification key is attached to v0.3.2. The installed app pins that key and accepts only verified same-channel upgrades. Releases are immutable; the channel feed advances only after the matching installer has been published.

<details>
<summary>Data sources &amp; third-party notices</summary>

AeroPilot Flight Deck is built on the existing Aerotto 98 controller. The Aerotto account, its connected services (live map, flight logs, jobs and network features) and their attribution are retained unchanged. Optional flight-log sharing sends the controller's log of each flight to aerotto.com when enabled in Settings. Your callsign, aircraft, position and route can appear on the Aerotto live map; hide your flight in your Aerotto account settings. Map imagery and labels in the separate tracking website come from their providers (Esri, Maxar, Earthstar Geographics and the GIS User Community; © OpenStreetMap contributors), as credited on the map.

</details>

