# Litefinga Desktop — public releases

**Public** download repo for Litefinga Desktop executables. Source code stays in the private `litefinga-desktop` repository; this repo only hosts **release binaries** and a small **manifest** for installers / auto-update.

## Download

Open [Releases](https://github.com/escltd/litefinga-desktop-releases/releases) and pick your platform:

| Platform | First install | Auto-update channel |
|----------|---------------|---------------------|
| Windows x64 | `litefinga-desktop-{version}-windows-amd64.msi` | `…-windows-amd64.zip` |
| macOS Apple Silicon | `…-darwin-arm64.dmg` | `…-darwin-arm64.zip` (`.app`) |
| macOS Intel | `…-darwin-amd64.dmg` | `…-darwin-amd64.zip` (`.app`) |
| Linux x64 | `…-linux-amd64.deb` | `…-linux-amd64.tar.gz` |

Binaries are **unsigned** in MVP builds — macOS Gatekeeper / Windows SmartScreen may warn until code signing is added. In-app updates verify **SHA256SUMS** from each GitHub release.

## Latest stable (machine-readable)

[`manifest.json`](manifest.json) — updated on each **stable** publish:

```json
{
  "version": "v0.2.0",
  "prerelease": false,
  "assets": {
    "windows-amd64-msi": "https://...",
    "darwin-arm64": "https://...",
    "linux-amd64": "https://..."
  },
  "checksums": {
    "windows-amd64-msi": "sha256:..."
  }
}
```

Pre-releases use [`manifest-prerelease.json`](manifest-prerelease.json) (optional beta channel).

Asset keys ending in `-update` are for the in-app updater only (not linked from the marketing site).

## How releases are published

CI in **private** `litefinga-desktop` builds on native Windows, macOS, and Linux runners, then pushes a matching GitHub Release **here** with `SHA256SUMS`.

## Pre-releases

Desktop PR builds publish pre-release assets here too (tag `vX.Y.Z-pre.{pr}`).
