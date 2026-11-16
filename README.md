# AeroPilot releases

Windows installers, signed update feeds and release notes for AeroPilot Flight Deck.

## Download

[AeroPilot 0.3.6 preview](https://github.com/m2r4kkmkzj-lgtm/aeropilot-releases/releases/tag/v0.3.6)

Download the installer from the link in the release description (it is not attached under Assets):
[AeroPilot-0.3.6-Setup.exe](https://raw.githubusercontent.com/m2r4kkmkzj-lgtm/aeropilot-releases/v0.3.6/installers/AeroPilot-0.3.6-Setup.exe)

- Size 1,179,136 bytes
- SHA256 `29e1e78c06366c69b8acbe09b65ae61895d448d0e181a5261a1f09f29be0fe7f`

Close AeroPilot while safely parked before installing. Setup installs for your Windows account and creates an **AeroPilot** desktop shortcut.

Launch with that shortcut. It checks the signed preview channel before starting the app. Verified newer releases install into a new version folder and the previous version is kept. A running controller is never replaced. Opening a version folder's AeroPilot.exe directly skips the update check. Network availability and GitHub caching can delay update discovery.

Earlier preview installations can update to 0.3.6 through the signed preview channel on the next shortcut launch.

## What is included

- The AeroPilot Design 8.2 interface with its own version display (v0.3.6), and cleaner wording in the app and map.
- The existing flight controller, account and connected services. Their attribution and data-sharing disclosures are kept in **Settings → Sharing, connected services & third-party notices**.
- Per-user setup, a desktop shortcut and a Windows installed-app entry.
- RSA-signed HTTPS launch-time updates, version backups and command-line rollback.
- Uninstall registration. Flight logs, profiles and version backups are kept for recovery.

Default installation: `%LOCALAPPDATA%\AeroPilot`. Errors during update checks are written to `update.log` there. While AeroPilot is closed, the launcher supports `--rollback`, `--resume-updates` and `--uninstall`. Rollback pauses updates so the rejected release isn't immediately restored.

## Qualification

0.3.6 includes A350 Fix9 native altitude-capture acceptance, Fix10 geometric hairpin look-ahead, Fix11 slower hairpins and Fix12 straight-pushback heading hold. Fix12 has one documented gate-to-gate simulator flight (LEBB to LEMD, 16 November 2026). Stand alignment, route-start geometry and straight taxi overspeed remain under investigation. The newer version-98/Fix13 candidate is not included.

80 automated tests pass. All 68 source-package hashes and the public signed preview feed/download signature, size and SHA256 were verified. Claude recorded an isolated scratch installation with 68 matching hashes. Native installation/UI checks from 0.3.4 are historical; no new 0.3.6 native installation was performed during publication.

This is a preview. Second clean-PC/dependency acceptance, Authenticode signing and representative multi-aircraft flight qualification remain incomplete. No universal aircraft or gate-to-gate guarantee is made.

The hosted flight-tracking website is a separate service. This repository contains no personal telemetry, account credentials, private signing keys or development source.

The signed preview feed is `channels/preview.json`. The public verification key is attached to v0.3.2. The installed app pins that key and accepts only verified same-channel upgrades. Releases are immutable; the channel feed advances only after the matching installer has been published.

<details>
<summary>Data sources &amp; third-party notices</summary>

AeroPilot Flight Deck is built on the existing Aerotto 96 controller. The Aerotto account, its connected services (live map, flight logs, jobs and network features) and their attribution are retained unchanged. Optional flight-log sharing sends the controller's log of each flight to aerotto.com when enabled in Settings. Your callsign, aircraft, position and route can appear on the Aerotto live map; hide your flight in your Aerotto account settings. Map imagery and labels in the separate tracking website come from their providers (Esri, Maxar, Earthstar Geographics and the GIS User Community; © OpenStreetMap contributors), as credited on the map.

</details>