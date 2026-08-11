# STADIUM_BATTLE_FX_DS - Unofficial Compatibility Fork
Unofficial fork of StadiumBattleFX supporting DRAMATIC_SHAPE and BATTLE_ART_VOXEL_FORK (absol89's DramaticShapeVoxelMod) via a small bridge mod. Not affiliated with the original project.
Changes:

StadiumBattleFX hardcodes mod lookup for DRAMALESS_SHAPE in three files:
main.lua
lib/EffectCacheScreen.lua
lib/StadiumAssets.lua


Modified these to mod.find("DRAMATIC_SHAPE_COMPANION").
No other logic changed; everything else remains identical to v1.1.2.

How it works:

DRAMATIC_SHAPE_COMPANION (required) forwards modules from either DRAMATIC_SHAPE or BATTLE_ART_VOXEL_FORK.
Supports models, camera, and stadium features through this forwarding.

Installation:

Install either DRAMATIC_SHAPE or BATTLE_ART_VOXEL_FORK.
Install DRAMATIC_SHAPE_COMPANION.
Install STADIUM_BATTLE_FX_DS (this fork, not the original).

Getting Stadium Announcer Audio:

Use the original StadiumBattleFX to build the voice pack:
Download from original release.
Enable it temporarily.
In-game: OPTIONS -> STADIUM ROM -> IMPORT, select your ROM.
Extract the generated audio files into this fork’s assets folder.
Then, disable the original.



Notes:

The original StadiumBattleFX does not support DRAMATIC_SHAPE / Dramaless Shape — this fork adds that support.
Errors should be reported here with details:
Exact error/traceback
Voxel mod version
Confirm you're using STADIUM_BATTLE_FX_DS + DRAMATIC_SHAPE_COMPANION

Built/tested against:
StadiumBattleFX 1.1.2-ds1
DRAMATIC_SHAPE 1.8.2
BATTLE_ART_VOXEL_FORK 1.7.9




Credits:

Dramaless Shape for API foundation.
StadiumBattleFX as the base mod.
Original stadium battle concept by rootbeerronin.
