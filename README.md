# BARdemoTNL26.Widgets.Legacy

Demo repository for the Techorama NL 2026 session **Your Pipeline Is the Target: A DevOps Field Guide to Modern Supply Chain Security** by Brian Randell (Tuesday October 27, 2026, 14:30).

This is the bad state. The workflow in `.github/workflows/build.yml` has twelve findings and is kept exactly as shown on the slide. **Do not copy it.** The corrected pipeline is in [BARdemoTNL26.Widgets](https://github.com/devopsfm/BARdemoTNL26.Widgets).

## What each demo shows and where it lives

| Demo | What you see | Where |
|---|---|---|
| D1 Secret Protection | Push protection blocks a token at push time. A bypassed push on the `leaked-token` branch opened an alert anyway, and the ruleset on `main` blocks that pull request until the alert is resolved. | Pull request from `leaked-token`, Security, Secret scanning |
| D3 Pinning | The `pinned` branch differs from `main` only by replacing every tag with a full commit SHA and a version comment, produced with [pinact](https://github.com/suzuki-shunsuke/pinact) 5.0.2. | `git diff main..pinned` |
| D3 CodeQL on workflows | Code scanning read `build.yml` and reports missing permissions, code injection from the pull request title, and an untrusted checkout under `pull_request_target`. | Security, Code scanning, and the open pull request from `show-alerts` |

The workflow never runs to completion here. It targets a self-hosted runner that does not exist and a secret that was never set. That is fine; CodeQL scans the file, not the run.

## Credits

Case studies and the five-pillar framing from *Threats from the Shadows* (2026) by Ken Muse and Mickey Gousset, used with permission.
