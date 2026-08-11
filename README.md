# STADIUM_BATTLE_FX_DS---Unofficial-Compatibility-Fork
This is an unofficial fork of StadiumBattleFX that lets it run on DRAMATIC_SHAPE and BATTLE_ART_VOXEL_FORK (absol89's DramaticShapeVoxelMod fork) in addition to Dramaless Shape, via a small separate bridge mod. Not affiliated with the original project.

What was actually changed

StadiumBattleFX hardcodes its live-model/camera companion lookup to the exact mod id DRAMALESS_SHAPE, in three places, with no fallback or config option:

main.lua
lib/EffectCacheScreen.lua
lib/StadiumAssets.lua

All three were changed from mod.find("DRAMALESS_SHAPE") to mod.find("DRAMATIC_SHAPE_COMPANION"). That's it -- no other logic was touched. Everything else in this fork is identical to the original 1.1.2.

DRAMATIC_SHAPE_COMPANION is a second, separate mod (required alongside this fork) that does the actual work: it looks for either DRAMATIC_SHAPE or BATTLE_ART_VOXEL_FORK, whichever is installed, and forwards their VoxelState, OverworldBattle, Stadium, and StadiumRom modules under its own id so this fork can find them where it expects Dramaless Shape to be.

Install
DRAMATIC_SHAPE or BATTLE_ART_VOXEL_FORK (your own install, whichever you use).
DRAMATIC_SHAPE_COMPANION.
STADIUM_BATTLE_FX_DS (this fork -- not the original STADIUM_BATTLE_FX, they conflict).
Getting the Stadium announcer audio into this fork

The voice pack is built locally from your own Pokemon Stadium ROM, and the build step already works correctly on the original StadiumBattleFX. If you'd rather reuse that than rebuild it a second time from this fork directly:

Download the original StadiumBattleFX from its releases page: https://github.com/anxiousintrovert/StadiumBattleFX/releases/latest
Install and enable it on its own (temporarily -- it can run without Dramaless Shape/Dramatic Shape at all for this step).
In-game: OPTIONS -> STADIUM ROM -> IMPORT, and select your own legally-owned Pokemon Stadium (USA v1.0) ROM.
Let the first-run STADIUM ATTACK FX screen finish building the cache. This generates a zip containing the extracted audio under an assets folder.
Extract that zip, and copy the audio files out of its assets folder into this fork's matching folder.
You can now disable/remove the original StadiumBattleFX install if you only wanted it for this step.
Please don't bother the original author about this

This fork exists because the original StadiumBattleFX intentionally doesn't support Dramatic Shape / Dramaless Shape alternatives -- that's the author's call to make, not an oversight, and not something to push them on. If you run into problems, please don't go report them to the original StadiumBattleFX repo or its author -- none of this is their responsibility to support or debug.

Post any errors from this fork here instead. Please include:

The exact error text / traceback.
Which voxel mod you have installed and its version.
Confirmation you're using STADIUM_BATTLE_FX_DS + DRAMATIC_SHAPE_COMPANION together (not the original StadiumBattleFX).
Versions this was built and tested against
StadiumBattleFX this fork is based on: 1.1.2 (this fork: 1.1.2-ds1)
DRAMATIC_SHAPE: tested against 1.8.2 -- full support (Stadium models, hit-adjacent camera staging; no hit-reaction pose or faint hand-off, same limits as running with an older Dramaless Shape release).
BATTLE_ART_VOXEL_FORK (absol89/DramaticShapeVoxelMod): tested against 1.7.9 -- camera staging only. This fork has no Stadium ROM extraction system, so Stadium models, hit reactions, faint hand-off, and attachment points are unavailable through it; battles fall back to flat sprites for those specifically.

Versions are a moving target -- if either voxel mod ships a later release, things may work better or worse than described above. Report what you see.

Credits
Dramaless Shape (github.com/artyrambles/DRAMALESS_SHAPE) and its authors/contributors, who designed and added the Stadium.hit / Stadium.faint public API this whole chain works around the absence of outside their project.
StadiumBattleFX (github.com/anxiousintrovert/StadiumBattleFX) -- the mod this fork patches three lookups in, nothing else.
The Stadium battle presentation concept this whole family of mods is built on originates from the original Stadium Battle mod by rootbeerronin (Discord).
