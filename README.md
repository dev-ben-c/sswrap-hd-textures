# sswrap HD textures for Starsiege (1999)

A fan-made HD texture pack for **Starsiege**, for use with
[sswrap](https://github.com/dev-ben-c/sswrap), the OpenGL wrapper that loads it.

About 4,900 of the game's textures (terrain, skies, Herc skins, buildings, weapon effects, the
splash screen and menu backgrounds), upscaled 4x with
[Real-ESRGAN](https://github.com/xinntao/Real-ESRGAN) (`realesrgan-x4plus`).
Tiling surfaces such as terrain were padded with their own wrapped edges before upscaling so
they stay seamless; skins and logos were padded by extending their edges instead. Textures that
belong together were upscaled as one image and cut apart again, so they still join seamlessly:
each sky's ring of panels, and the splash screen and menu backgrounds, which the game cuts into
tiles (sswrap's `tools/hd-textures/stitch.py`).

## Download and install

1. Install [sswrap](https://github.com/dev-ben-c/sswrap) first.
2. Download `sswrap-hd-textures-*.zip` from this repo's
   [Releases page](https://github.com/dev-ben-c/sswrap-hd-textures/releases).
3. Extract it into your Starsiege folder (next to `Starsiege.exe`), so that you end up with
   `sswrap_textures\load\` full of PNG files.
4. Make sure `sswrap.ini` has `TextureReplace=1` (the default). Start the game.

`sswrap.log` reports each replaced texture; a few seconds of extra loading the first time a map
loads is normal.

## Compatibility

- Made from the **retail release, version 1.004** (the "Starsiege Universe" disc). Textures are
  matched by an exact fingerprint of the game's own texture data, so other versions only benefit
  where their art is identical. The free Hi-Rez re-release is expected to match but is untested.
- Covers everything seen in the **multiplayer maps** and most vehicles. Campaign-only content is
  not included yet. To fill gaps for your own copy, use sswrap's `TextureDump` and
  `tools/hd-textures/build.sh`; it only adds textures that are missing.
- HUD and menu buttons and text are not covered: the game assembles them at runtime in a way
  that never produces the same texture twice. (sswrap smooths those itself.)
- Needs sswrap 0.3.0 or newer: it puts a texture back to its original size when the game
  repaints it at runtime (the main menu's video and animations).

## Known issues

- A few skies were only partly seen when the pack was made; a join to a panel that wasn't seen
  can still show a faint seam.
- Noisy surfaces (cracked mud, gravel) come out cleaner and slightly more "painted" than the
  originals; that is the upscaling model's style.

## Legal

This pack contains **upscaled versions of Starsiege's original artwork**, which remains the
property of its rights holders (originally Dynamix / Sierra On-Line). It is an unofficial,
non-commercial fan project, not affiliated with or endorsed by them, and is distributed in the
spirit of preservation for a game that has been re-released for free. You need your own copy of
Starsiege to use it. Rights holders who object can open an issue and the pack will be removed.

The text and scripts in this repository (not the textures) are MIT licensed.
