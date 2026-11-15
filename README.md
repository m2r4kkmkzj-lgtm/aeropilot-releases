# AeroPilot releases

Windows installers, signed update feeds and release notes for AeroPilot Flight Deck.

## Download

[AeroPilot 0.3.3 preview](https://github.com/m2r4kkmkzj-lgtm/aeropilot-releases/releases/tag/v0.3.3)

Open **Assets** and download `AeroPilot-0.3.3-Setup.exe`. Close AeroPilot while safely parked before installing. Setup installs for your Windows account and creates an **AeroPilot** desktop shortcut.

Use that shortcut to launch: it checks the signed preview channel before starting the app. Verified newer releases install into a new version folder, preserving the previous version. A running controller is not replaced. Directly opening a version-folder AeroPilot.exe bypasses checking. Network availability and GitHub caching can delay update discovery.

Installer SHA256: `691310f700263ebb4b2917fd273939f6688cf4023409972cb4740b9a48e70014`.

## What is included

- AeroPilot Design 8.2 interface and own version display.
- Existing Aerotto 96 controller/account/services and attribution retained.
- Per-user setup, desktop shortcut and Windows installed-app entry.
- RSA-signed HTTPS launch-time updates, version backups and command-line rollback.
- Uninstall registration; flight logs, profiles and version backups are retained for recovery.

Default installation: `%LOCALAPPDATA%\AeroPilot`. Errors during update checks are written to `update.log` there. The launcher supports `--rollback`, `--resume-updates` and `--uninstall` while AeroPilot is closed. Rollback pauses updates to prevent immediately restoring the rejected release.

## Qualification

Native setup, shortcut launch, installed version display, 68 package hashes and Windows Programs and Features entry were verified on the development Windows PC. Public GitHub signed update download/activation was tested; 76 automated checks pass. This is a preview: second clean-PC/dependency acceptance and Windows Authenticode signing are not completed. No universal aircraft, flight-dynamics or gate-to-gate guarantee is made. This installer does not introduce a new flight-control fix or include the separate Fix9 engineering candidate.

The hosted flight-tracking website is a separate service. This repository does not contain personal telemetry, account credentials, private signing keys or the development source tree.

The signed preview feed is `channels/preview.json`. Public verification key is attached to v0.3.2; the installed app pins that key and accepts only verified same-channel upgrades. Releases are immutable; the channel feed advances only after the corresponding installer has been published.