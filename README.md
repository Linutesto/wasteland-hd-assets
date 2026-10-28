# Wasteland HD art

HD art for **Wasteland Reborn HD** (the Fallout 2 phone port,
[wasteland-reborn-installer](https://github.com/Linutesto/wasteland-reborn-installer)):
Fallout 2's art redrawn at twice the resolution by Qwen-Image-Edit 2511 on a
home RTX 4090, with the
[Wasteland HD tools](https://github.com/Linutesto/wasteland-hd-tools).
It's all here, ready to use: **you don't need a graphics card**.

## Use it (you need your own Fallout 2)

The art does nothing without a legally bought Fallout 2 (Steam, GOG or
Epic) installed through Wasteland Reborn. It contains no game files.

- **Easiest:** the Wasteland Reborn HD installer, or
  `python -m wasteland_hd install --game <your game folder>` from the
  [tools](https://github.com/Linutesto/wasteland-hd-tools). It checks for
  the game first, then downloads the packs listed in `packs.json` (zips of
  this same art, attached to this repository's releases).
- **By hand:** clone this repository and copy its `hd/` folder into the
  game's `data/` folder (PC), or into
  `Android/data/io.github.imbaner.fallout2ce.hd/files/profiles/<profile>/data/`
  (phone).

## What's in it

`hd/art/<type>/<name>/<direction>_<frame>.png`: one PNG per frame of the
original art, exactly twice its size, with the original's transparency. The
game loads one when it exists and draws the original art otherwise.

| Covered | Status |
| --- | --- |
| Floor and roof tiles, walls, scenery, items, misc: the whole game | done |
| Critters (people and creatures) | not yet |

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
