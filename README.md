# AeroPilot releases

Windows installers, signed update feeds and release notes for AeroPilot Flight Deck.

## Download

[AeroPilot 0.4.3 preview](https://github.com/m2r4kkmkzj-lgtm/aeropilot-releases/releases/tag/v0.4.3)

Download the installer from the link in the release description (it is not attached under Assets):
[AeroPilot-0.4.3-Setup.exe](https://raw.githubusercontent.com/m2r4kkmkzj-lgtm/aeropilot-releases/v0.4.3/installers/AeroPilot-0.4.3-Setup.exe)

- Size 1,307,648 bytes
- SHA256 `1c433b5329b06cc4ebca16eff6176ed19bedb4f64f5a4d523277d60d768ccf0e`

Close AeroPilot while safely parked before installing. Setup installs for your Windows account and creates an **AeroPilot** desktop shortcut.

Launch with that shortcut. It checks the signed preview channel before starting the app. Verified newer releases install into a new version folder and the previous version is kept. A running controller is never replaced. Opening a version folder's AeroPilot.exe directly skips the update check. Network availability and GitHub caching can delay update discovery.

Earlier preview installations can update to 0.4.3 through the signed preview channel on the next shortcut launch.

## What is included

- The AeroPilot Lime Glass interface with its own version display (v0.4.3), and cleaner wording in the app and map.
- The existing flight controller, account and connected services. Their attribution and data-sharing disclosures are kept in **Settings → Sharing, connected services & third-party notices**.
- Per-user setup, a desktop shortcut and a Windows installed-app entry.
- RSA-signed HTTPS launch-time updates, version backups and command-line rollback.
- Uninstall registration. Flight logs, profiles and version backups are kept for recovery.

Default installation: `%LOCALAPPDATA%\AeroPilot`. Errors during update checks are written to `update.log` there. While AeroPilot is closed, the launcher supports `--rollback`, `--resume-updates` and `--uninstall`. Rollback pauses updates so the rejected release isn't immediately restored.

## Qualification

0.4.3 adds an FBW A380X-only speed/V/S/lights batch. It routes native-AP enroute thrust through the existing speed controller rather than fixed climb thrust, limits the requested IAS by the existing profile Mach ceiling, and stabilizes nominal climb V/S while retaining underspeed reduction and bounded simulator-time slew. Light InputEvents are mapped from inspected FBW/Asobo templates. Earlier brake release, steering and boxed takeoff fixes are retained. A350 helper/profile bytes remain unchanged from the preceding experimental A380 package; A350 Fix19 remains unflown.

Earlier A380 flight verified brake release, takeoff thrust and AP1 but showed302kt at8993ft against250kt target. The new batch is OFFLINE-TESTED ONLY: no flight or physical light response is qualified. No A350 Final promotion or all-aircraft acceptance.

93/93 app checks PASS; JIT2087 existing package methods plus6newpolicy methods PASS; original/extended SmokeA380 execution PASS;17/17newpolicy checks PASS;23runnable A350 regression suites PASS. Two pre-existing crashing harnesses and the stale StandTurn harness are not counted as passes. Local reinstall verified all74payload hashes; previous experimental build archived with0.4.2rollback retained. Published HTTPS signature/hash/size verified. Second clean-PC/Authenticode and actual flight stability remain incomplete.

The hosted flight-tracking website is a separate service. This repository contains no personal telemetry, account credentials, private signing keys or development source.

The signed preview feed is `channels/preview.json`. The public verification key is attached to v0.3.2. The installed app pins that key and accepts only verified same-channel upgrades. Releases are immutable; the channel feed advances only after the matching installer has been published.

<details>
<summary>Data sources &amp; third-party notices</summary>

AeroPilot Flight Deck is built on the existing Aerotto 98 controller. The Aerotto account, its connected services (live map, flight logs, jobs and network features) and their attribution are retained unchanged. Optional flight-log sharing sends the controller's log of each flight to aerotto.com when enabled in Settings. Your callsign, aircraft, position and route can appear on the Aerotto live map; hide your flight in your Aerotto account settings. Map imagery and labels in the separate tracking website come from their providers (Esri, Maxar, Earthstar Geographics and the GIS User Community; © OpenStreetMap contributors), as credited on the map.

</details>

