# AeroPilot releases

Windows installers, signed update feeds and release notes for AeroPilot Flight Deck.

## Download

[AeroPilot 0.4.2 preview](https://github.com/m2r4kkmkzj-lgtm/aeropilot-releases/releases/tag/v0.4.2)

Download the installer from the link in the release description (it is not attached under Assets):
[AeroPilot-0.4.2-Setup.exe](https://raw.githubusercontent.com/m2r4kkmkzj-lgtm/aeropilot-releases/a0367fb4631f3204a5aa29d94523e0aaf11a9b5c/installers/AeroPilot-0.4.2-Verified-Setup.exe)

- Size 1,302,528 bytes
- SHA256 `bbcc4c33062aa8b9b52e6b29f069660e6e607615da5037c2459cc8b7e74507e4`

Close AeroPilot while safely parked before installing. Setup installs for your Windows account and creates an **AeroPilot** desktop shortcut.

Launch with that shortcut. It checks the signed preview channel before starting the app. Verified newer releases install into a new version folder and the previous version is kept. A running controller is never replaced. Opening a version folder's AeroPilot.exe directly skips the update check. Network availability and GitHub caching can delay update discovery.

Earlier preview installations can update to 0.4.2 through the signed preview channel on the next shortcut launch.

## What is included

- The AeroPilot Lime Glass interface with its own version display (v0.4.2), and cleaner wording in the app and map.
- The existing flight controller, account and connected services. Their attribution and data-sharing disclosures are kept in **Settings → Sharing, connected services & third-party notices**.
- Per-user setup, a desktop shortcut and a Windows installed-app entry.
- RSA-signed HTTPS launch-time updates, version backups and command-line rollback.
- Uninstall registration. Flight logs, profiles and version backups are kept for recovery.

Default installation: `%LOCALAPPDATA%\AeroPilot`. Errors during update checks are written to `update.log` there. While AeroPilot is closed, the launcher supports `--rollback`, `--resume-updates` and `--uninstall`. Rollback pauses updates so the rejected release isn't immediately restored.

## Qualification

0.4.2 contains the Lime Glass interface, destination hero, callsign greeting and Flight Core 1.0 presentation (based on the existing engine98; attribution retained). Fix19 adjusts A350 flare pitch, sharp stand-corner lead and terminal-zone acceleration handling. Map names/borders, desktop logo and Vision Jet profile are retained. It supersedes unpublished0.4.1.

Fix18 completed an A350-900 LEMD-to-LEBB gate-to-gate flight on17November with flare float, stand-corner cut and gate overspeed recorded. Fix19 addresses those findings but is offline-only, NOT flown. Published at user request without a test flight; no A350 Final promotion or all-aircraft qualification.

93/93 automated checks PASS during publication,72source manifest hashes verified, Claude recorded local installation PASS. Public HTTPS feed RSA signature, download size and SHA256 verified. No simulator commands or main installation changes during publication. Some historical helper harnesses retain documented pre-existing failures. Second clean-PC/dependency and Authenticode qualification remain incomplete.

Download correction: use the verified installer link above. Initial tag upload failed checksum verification; it was not distributed through the signed updater. Tag history remains preserved; correct bytes are linked by immutable commit.

The hosted flight-tracking website is a separate service. This repository contains no personal telemetry, account credentials, private signing keys or development source.

The signed preview feed is `channels/preview.json`. The public verification key is attached to v0.3.2. The installed app pins that key and accepts only verified same-channel upgrades. Releases are immutable; the channel feed advances only after the matching installer has been published.

<details>
<summary>Data sources &amp; third-party notices</summary>

AeroPilot Flight Deck is built on the existing Aerotto 98 controller. The Aerotto account, its connected services (live map, flight logs, jobs and network features) and their attribution are retained unchanged. Optional flight-log sharing sends the controller's log of each flight to aerotto.com when enabled in Settings. Your callsign, aircraft, position and route can appear on the Aerotto live map; hide your flight in your Aerotto account settings. Map imagery and labels in the separate tracking website come from their providers (Esri, Maxar, Earthstar Geographics and the GIS User Community; © OpenStreetMap contributors), as credited on the map.

</details>

