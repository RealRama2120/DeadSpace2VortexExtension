# Changelog

## 1.0.2 - 2026-10-13

- Added numeric Nexus Mods game ID `2500` to `info.json` for automatic Vortex catalogue discovery.
- Updated version metadata and publication documentation.
- Runtime code, game discovery, mod deployment, artwork, and license are unchanged from 1.0.1.

## 1.0.1 — 2026-09-24

The author confirmed that the extension works with a Dead Space 2 EA App
installation.

- Updated the validation notes to include the author's EA App test.
- Kept Origin and retail installation support clearly marked as not yet tested
  on a live installation.
- No runtime code, installation behavior, or artwork changes from 1.0.0.

## 1.0.0 — 2026-09-24

Stable release following the author's successful use of the extension in Vortex,
including TexMod mods.

- Promoted the tested 0.1.0 implementation to version 1.0.0.
- Updated release documentation and Nexus upload guidance to reflect the author's
  test and the remaining EA App / Origin and retail coverage limits.
- No runtime code, installation behavior, or artwork changes from 0.1.0.

## 0.1.0

Initial standalone beta release for Dead Space 2.

- Steam, EA App / Origin, registry, mounted-drive, and manual game discovery.
- Executable and data-file validation before accepting an installation.
- Root-folder mod deployment with preserved ASI plugin and ReShade folders.
- Shared archive-wrapper removal, including packages with an external README.
- TexMod package management, retaining other files in mixed archives.
- Path and destination-collision checks.
- Original 640 x 360 game tile, full readable source, documentation, and MIT license.
