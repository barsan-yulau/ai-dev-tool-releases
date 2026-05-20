# ai-dev-tool-releases

Public mirror for [ai-dev-tool](https://github.com/barsan-yulau/ai-dev-tool) release assets, serving the auto-updater payload via GitHub Pages.

This repository contains **only built artifacts** — no source code. The project source lives in the (private) `ai-dev-tool` repository.

## What's served

- `latest.json` — Tauri updater manifest pointing at the most recent signed release.
- Per-version asset directories under `releases/v<version>/` containing the signed MSI, signature, NSIS installer, release notes, and checksums for each release.

## Auto-update endpoint

```
https://barsan-yulau.github.io/ai-dev-tool-releases/latest.json
```

Embedded in `src-tauri/tauri.conf.json` of every signed release from v0.4.1 onward.

## Signature trust

All MSI artifacts published here are signed with minisign (ed25519) using a private key that lives only on the maintainer's machine, outside any repository. The matching public key is embedded in every installed copy of ai-dev-tool, so the updater verifies the signature before any installation occurs. Anyone who downloads from this mirror can verify the signature independently against the published public key.

## License

The artifacts here are subject to the same license as the source project (MIT).
