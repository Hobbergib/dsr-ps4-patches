# Dark Souls Remastered (PS4) – GoldHEN graphics patches

GoldHEN game patches for **Dark Souls: Remastered** on PS4 that remove some of the remaster's post-processing and lighting additions.

| Patch | What it does |
|---|---|
| **Motion Blur Off** | Turns off the camera motion blur. Switches the blur pass off and sets its strength to 0, so it also covers PS4 Pro checkerboard rendering. |
| **Depth of Field Off** | Removes the near and far depth of field blur. Forces the DoF strength from each area's lighting settings to 0, the same as areas that have no DoF. |
| **Player Lantern Off** | Removes the light the remaster adds around the player, for darker, original-style lighting. Dark areas become much darker. |

Each patch is a separate toggle, so use any combination.

## Compatibility

- **Tested:** CUSA08495 (US), game version **01.03**, on a jailbroken PS4 with GoldHEN.
- Other regions (CUSA08432, CUSA08526, CUSA08692) may use the same program, but they haven't been tested, so they aren't listed in the file.
- Requires GoldHEN with the game patch plugin enabled. The older PS4HEN does not support game patches.

## Install

1. Copy `patches/xml/CUSA08495.xml` to `/data/GoldHEN/patches/xml/CUSA08495.xml` on the PS4, for example over GoldHEN's FTP server (port 2121):
   ```sh
   curl -T patches/xml/CUSA08495.xml ftp://<PS4-IP>:2121/data/GoldHEN/patches/xml/
   ```
2. Turn on the patches you want in GoldHEN's patch menu.
3. Fully close and restart the game. Patches are applied when the game starts.

### Keeping other patches for this game

GoldHEN reads **one XML file per title ID**. Copying this file over an existing `CUSA08495.xml` replaces it, including patches from GoldHEN's own patch download, such as *Restore Debug Camera*. To keep both, paste the `<Metadata>` blocks from this file into your existing `CUSA08495.xml`, just before its closing `</Patch>` tag.

Using GoldHEN's "download/update patches" option may overwrite a merged file with the official version.

## How it works

All patches change bytes in the game's program while it's in memory. Nothing on disk is modified. Each line in the XML has a comment explaining the instruction or value it changes.

## Credits

Patches by Hobbergib.
