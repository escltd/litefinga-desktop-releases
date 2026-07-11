# litefinga-desktop-releases

Public distribution repo for Litefinga Desktop binaries. **No application source** — only release artifacts and manifests.

## Role

| Item | Location |
|------|----------|
| Source + CI | Private `escltd/litefinga-desktop` |
| Public downloads | This repo — [GitHub Releases](https://github.com/escltd/litefinga-desktop-releases/releases) |
| Stable manifest | `manifest.json` (raw URL for auto-update clients) |
| Pre-release manifest | `manifest-prerelease.json` |

## Publishing (automated)

`litefinga-desktop/.github/workflows/release.yml` runs on `main` / PR / `workflow_dispatch`, then:

1. Creates a tag on the **private** desktop repo (version tracking).
2. Publishes **binaries** to **this** repo with `softprops/action-gh-release` + `DESKTOP_RELEASES_TOKEN`.
3. Commits updated `manifest.json` or `manifest-prerelease.json` on `main` here.

## Manual changes

Avoid hand-uploading releases — use desktop CI. You may edit README; manifest files are CI-owned.

## Parent workspace

See `../AGENTS.md`.
