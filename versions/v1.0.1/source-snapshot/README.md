# Dead Space 2 Vortex Extension

Version 1.0.1 · Author: Rama2120

Adds Windows Dead Space 2 support to Vortex. Install this extension once, then
manage compatible game-folder mods with Vortex's normal install, enable, deploy,
disable, and purge controls. It is standalone and does not require the Dead Space
(2008) extension or any particular gameplay fix.

## Install the extension

1. Open Vortex and go to **Extensions** (enable Advanced mode if it is hidden).
2. Drop the downloaded extension ZIP into the extension installation drop area,
   or use **Install From File** if offered by your Vortex version.
3. Restart Vortex when prompted.
4. Find **Dead Space 2** in Games and choose **Manage**. If needed, scan for games.
5. If discovery fails, set the location manually to the folder containing both
   `deadspace2.exe` and `DS2DAT0.DAT`.
6. For hardlink deployment, set the mod staging folder on the same drive as the
   game. Install a compatible mod, enable it, and choose **Deploy Mods**.

This ZIP is a Vortex extension. Install it through Extensions, not as a normal
Dead Space 2 mod, and do not extract it into your game folder.

Manual extension installation is also supported: close Vortex and extract this
ZIP into `%APPDATA%\Vortex\plugins\game-deadspace2`. `index.js`, `info.json`, and
`gameart.png` must be directly inside that folder. Avoid installing duplicate
copies of the extension.

## Supported layouts

- Game-root DLL, INI, ASI, and configuration mods, including mouse-fix style files.
- ASI-loader packages that use `plugins` or `scripts` subfolders. These folders
  stay intact, including when an archive contains only the plugin folder.
- ReShade/ENB/SweetFX files and presets, preserving shader and texture folders.
- Ready-to-copy `DS2DAT*.DAT` replacements. This extension does not edit, merge,
  rebuild, or patch game data archives.
- TexMod `.tpf` packages, stored beneath `TexMod Packages` in the game folder.

The installer removes shared packaging folders while preserving known runtime
folders. A README outside the packaging folder does not prevent this. It accepts
Windows and forward-slash archive paths and ignores common macOS metadata.

Mixed packages keep their root DLL/configuration files as well as their textures.
Texture subfolders are preserved so similarly named packages do not silently
overwrite one another. Unsafe paths and duplicate output filenames are rejected.
FOMOD packages are left to Vortex's own FOMOD installer.

## TexMod textures

Vortex manages the texture package files; **TexMod is still required to load them
into the game**. After deployment, select the desired `.tpf` files from
`<game folder>\TexMod Packages` in TexMod and launch the game through TexMod.
Follow the texture author's store-specific launch instructions. This extension
does not automate TexMod, rename the game executable, or include TexMod itself.

## Game detection

Discovery tries these sources in order, validating the executable and data file
before accepting a folder:

1. Vortex's Steam helper, using app ID `47780` (including registered custom libraries).
2. Vortex's EA App / Origin helper, using the game name.
3. Common EA/Origin/retail registry paths, including machine/current-user keys and
   32-bit and 64-bit locations.
4. Common library paths on mounted Windows drive letters A through Z, plus a
   bounded search in top-level library folders.

The scan is read-only. It does not recursively search an entire disk. Deeply
nested, unregistered libraries and unusual installations can be selected manually.
Dead Space (2008), Dead Space (2023), and Dead Space 3 use separate integrations.

## Limits and troubleshooting

- A mod manager does not make every mod compatible with every store version.
  Follow each mod author's requirements. Loaders, fixes, ReShade, and TexMod are
  separate downloads; none are supplied by this extension.
- Archives offering multiple alternative installations must be reduced to the
  desired variant or installed according to their author's instructions. Review
  unusual archive layouts before deployment.
- Standalone patcher programs and EXE installers are not executed. Save files,
  user-profile `settings.txt`, and loose texture assets needing an external tool
  require their author's manual workflow. This extension targets the game folder.
- Vortex uses its normal file-conflict rules. Two mods supplying `dinput8.dll`,
  `d3d9.dll`, or the same DAT file cannot both occupy that destination. Follow
  the authors' compatibility or chaining instructions; the extension does not merge them.
- If Windows denies access to the game folder, use Vortex's normal permission
  prompt or move the game through its launcher to a writable library. This
  extension does not run administrator commands or modify folder permissions.
- To remove managed files, disable the relevant mods and deploy, or use Purge Mods.
  When replacing existing game files, retain backups and allow Vortex to handle
  its deployment backups. A launcher repair can restore original game files.

## Validation status

Local automated checks cover game registration, discovery fixtures, archive
layouts, unsafe paths, collisions, and staging/link/removal of harmless fixture
files. The drive-discovery path also found a real Steam installation, read-only.
API contracts were checked against installed Vortex 2.6.3 and Nexus documentation.

The author reports successful use of this extension in Vortex, including TexMod
mods, and has also confirmed that it works with a Dead Space 2 EA App installation.
These are user-reported acceptance checks, separate from the local automated
checks above. They do not establish a clean-install test, a purge test, or
compatibility with every individual mod. Origin and retail discovery have fixture
coverage, but have not been tested on a live installation.

Full extension source is the readable `index.js` included in this ZIP.

## Credits and license

Dead Space 2 integration: Rama2120. The earlier Dead Space (2008) extension was
used as a functional reference. No game files or third-party mod code/binaries
are bundled. Vortex and its APIs are provided separately by Nexus Mods.

The tile is original AI-generated atmospheric artwork prepared for this release;
it is not an official EA screenshot. Extension code and supplied artwork are
provided under the MIT License to the extent applicable; see `LICENSE.txt`.
Dead Space and related marks belong to Electronic Arts. This community extension
is not affiliated with or endorsed by EA or Nexus Mods.

## References

- [Vortex extension development](https://github.com/Nexus-Mods/Vortex/wiki/MODDINGWIKI-Developers-General-Creating-a-game-extension)
- [Vortex extension packaging](https://github.com/Nexus-Mods/Vortex/wiki/How-to-package-a-game-extension)
- [Extension upload instructions](https://github.com/Nexus-Mods/Vortex/wiki/How-to-upload-an-extension-to-nexus)
- [Dead Space 2 on Steam](https://store.steampowered.com/app/47780/Dead_Space_2/)
