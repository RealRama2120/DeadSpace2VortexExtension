# Version 1.0.2 verification

Verified on October 13, 2026.

- Metadata: Rama2120, version 1.0.2, numeric Nexus game ID 2500.
- JavaScript syntax, 640 by 360 PNG below 1 MB, and exact six root ZIP files passed.
- Every extracted package hash matches its packaging source.
- Existing packaged-source regression suite: 42 passed, zero failed, 0 skipped.
- Runtime `index.js`, artwork, and license are identical to the previous 1.0.1 package.
- Original historical archives and checksum sidecars are preserved unchanged.

The existing read-only installed-Steam detection check passed. It does not launch the game or deploy mods into its installation.
The test suite's deployment/removal fixture uses harmless generated files in its
own test-artifacts folder. No game was launched or modified for this release.
This metadata update does not establish new gameplay or storefront compatibility.

Install ZIP SHA-256: `7cbb443dc4cb2c167af6406f59d0b82f243231c1e7dfd95b1b1550801ab1d317`

Runtime source SHA-256: `fb4c3ed693a6c177be1e8ee9a34e5d8e604f07a6171b290b59b689801fe3ecae`

Nexus page: https://www.nexusmods.com/site/mods/2347
