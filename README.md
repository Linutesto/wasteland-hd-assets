# Wasteland HD art

HD art for **Wasteland Reborn HD** (the Fallout 2 phone port,
[wasteland-reborn-installer](https://github.com/Linutesto/wasteland-reborn-installer)):
Fallout 2's art redrawn at twice the resolution by Qwen-Image-Edit 2511 on a
home RTX 4090, with the
[Wasteland HD tools](https://github.com/Linutesto/wasteland-hd-tools).
It's all here, ready to use: **you don't need a graphics card**.

## For players

The installer repository is the player guide and download entry point. It has the v1.4 APKs, Windows installers, installation guides and troubleshooting:

- [Wasteland Reborn — install and download](https://github.com/Linutesto/wasteland-reborn-installer#download)
- [HD art setup guide](https://github.com/Linutesto/wasteland-reborn-installer/blob/main/docs/INSTALL-WINDOWS.md#6-hd-art-hd-edition-only)

The HD app offers the published packs. The world pack is 440 MB (9,422 images); heads are 468 MB (1,352 images). Together they download to about 910 MB and take about 2 GB unpacked with the game. Keep at least 3 GB free on the phone. Critter art is in production; its first pack is not published and no date is promised.

## packs.json, for players

`packs.json` is the **catalogue of downloadable packs** — the file both
the Windows installer and the **Wasteland HD** app read to know what to
download and to check it arrived intact:

`https://raw.githubusercontent.com/Linutesto/wasteland-hd-assets/main/packs.json`

You never edit it. Each entry in the list is one pack:

| Field | What it means |
| --- | --- |
| `name` | the pack's id (`world`, `critters-01`, …) — shown in progress lines like `world: 42%` |
| `file` | the zip's name (e.g. `WastelandHD-World.zip`) |
| `covers` | in plain words what the pack redraws — this is the text the app shows when it offers the download |
| `url` | where the zip lives (a release of this repository) |
| `size` | size in bytes — the number behind the MB shown on screen |
| `frames` | how many PNG frames the zip contains |
| `sha256` | fingerprint of the zip; if it does not match, the download is refused and nothing is installed |

An **empty list** (`"packs": []`) simply means no pack is published yet:
the app then offers nothing and the game runs with the original art. As
packs are published here, the app starts offering them on its own — no
action needed.

## Use it (you need your own Fallout 2)

The art does nothing without a legally bought Fallout 2 (Steam, GOG or
Epic) installed through Wasteland Reborn. It contains no game files.

- **Easiest:** the Wasteland Reborn HD installer or the **Wasteland HD**
  app — see [For players](#for-players-install-it-with-the-installer-or-the-app)
  above.
- **From the command line:**
  `python -m wasteland_hd install --game <your game folder>` from the
  [tools](https://github.com/Linutesto/wasteland-hd-tools). It checks for
  the game first, then downloads the packs listed in `packs.json` (zips of
  this same art, attached to this repository's releases).
- **By hand:** the [manual copy](#manual-copy-only-if-you-are-not-using-the-app)
  steps above.

## What's in it

`hd/art/<type>/<name>/<direction>_<frame>.png`: one PNG per frame of the
original art, exactly twice its size, with the original's transparency. The
game loads one when it exists and draws the original art otherwise.

| Covered | Status |
| --- | --- |
| Floor and roof tiles, walls, scenery, items, misc: the whole game | done |
| Talking heads | published in v1.4 |
| Critters (people and creatures) | in production; first pack not published |

Every frame was checked against the original art. Frames the model redrew
in other colours (a red pistol turned brown, a dark floor turned into
planks) were redrawn, or left out when they still came out wrong. Floor
tiles were blended toward the original at their edges, so neighbouring
tiles meet without seams. The tools repository explains how, and has the
commands to make your own.

## Notice

A free, non-commercial fan project, not affiliated with or endorsed by
Bethesda Softworks, ZeniMax Media or Interplay Entertainment. Fallout and
Fallout 2 are trademarks of Bethesda Softworks LLC; the original art is
© its owners, and this art is derived from it. It is free and always will
be: never sell it. If you are a rights holder and want it removed, open an
issue on this repository and it will be taken down.
