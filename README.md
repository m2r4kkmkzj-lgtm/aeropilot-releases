# AeroPilot releases

Windows installers, signed update feeds and release notes for AeroPilot Flight Deck.

## Download

[AeroPilot 0.3.7 preview](https://github.com/m2r4kkmkzj-lgtm/aeropilot-releases/releases/tag/v0.3.7)

Download the installer from the link in the release description (it is not attached under Assets):
[AeroPilot-0.3.7-Setup.exe](https://raw.githubusercontent.com/m2r4kkmkzj-lgtm/aeropilot-releases/v0.3.7/installers/AeroPilot-0.3.7-Setup.exe)

- Size 1,198,592 bytes
- SHA256 `63ca1cd2c1a36e15c10b99095a723abad537ca9aeacae38cd37f433acaebd717`

Close AeroPilot while safely parked before installing. Setup installs for your Windows account and creates an **AeroPilot** desktop shortcut.

Launch with that shortcut. It checks the signed preview channel before starting the app. Verified newer releases install into a new version folder and the previous version is kept. A running controller is never replaced. Opening a version folder's AeroPilot.exe directly skips the update check. Network availability and GitHub caching can delay update discovery.

Earlier preview installations can update to 0.3.7 through the signed preview channel on the next shortcut launch.

## What is included

- The AeroPilot Design 8.2 interface with its own version display (v0.3.7), and cleaner wording in the app and map.
- The existing flight controller, account and connected services. Their attribution and data-sharing disclosures are kept in **Settings → Sharing, connected services & third-party notices**.
- Per-user setup, a desktop shortcut and a Windows installed-app entry.
- RSA-signed HTTPS launch-time updates, version backups and command-line rollback.
- Uninstall registration. Flight logs, profiles and version backups are kept for recovery.

Default installation: `%LOCALAPPDATA%\AeroPilot`. Errors during update checks are written to `update.log` there. While AeroPilot is closed, the launcher supports `--rollback`, `--resume-updates` and `--uninstall`. Rollback pauses updates so the rejected release isn't immediately restored.

## Qualification

0.3.7 includes engine98, the stock Cirrus SF50 Vision Jet profile and the corrected version display. A350 Fix13 route-start stop, Fix14 pause-aware acknowledgements, Fix15 turn feed-forward and Fix16 no-fitting-stand taxi-in fallback are included alongside earlier improvements.

Claude documented one engine98/Fix14 flight LEMD to LERL with clean landing/rollout; taxi-in was not run. Fix15/16 are offline-tested only and released at the user's explicit request. Vision Jet profile selection is log-confirmed locally; no Vision Jet flight is qualified.

81 automated tests pass. Isolated install and all72payload hashes verified; native app visibly shows v0.3.7 without header overlap. Public HTTPS signed update feed, installer size and SHA256 verified. No new flight performed during publication. Second clean-PC/dependency acceptance, Authenticode signing and representative multi-aircraft flight qualification remain incomplete.

The hosted flight-tracking website is a separate service. This repository contains no personal telemetry, account credentials, private signing keys or development source.

The signed preview feed is `channels/preview.json`. The public verification key is attached to v0.3.2. The installed app pins that key and accepts only verified same-channel upgrades. Releases are immutable; the channel feed advances only after the matching installer has been published.

<details>
<summary>Data sources &amp; third-party notices</summary>

AeroPilot Flight Deck is built on the existing Aerotto 98 controller. The Aerotto account, its connected services (live map, flight logs, jobs and network features) and their attribution are retained unchanged. Optional flight-log sharing sends the controller's log of each flight to aerotto.com when enabled in Settings. Your callsign, aircraft, position and route can appear on the Aerotto live map; hide your flight in your Aerotto account settings. Map imagery and labels in the separate tracking website come from their providers (Esri, Maxar, Earthstar Geographics and the GIS User Community; © OpenStreetMap contributors), as credited on the map.

</details>