<div align="center">

**Version 1.0.0 - [`7ef78ff`](https://github.com/RATR2/repack/commit/7ef78ff8cf93a97778ea0953cfb6c0b4532a8103)**

Finally, we made it to modrinth:
https://modrinth.com/plugin/repacked_2

And because of this we are now on version 1.0.0.

Added
- Settings screens: /repack opens a hub with your own settings and, with repack.settings, the server's config.yml. /repack builder opens a block builder, and there is an item builder too. Everything they do is also in the API (RepackAPI.create, edit, createItem, editItem).
- Custom items that are not blocks: items/<id>.yml with a name, lore, glint, a model from models/, item components or an exact item saved from the game. Skript has custom item "ruby" and the API has RepackAPI.item and registerItem.
- Ripple effects: /repack distortion spawn, RepackAPI.ripple and the Skript effect. distortion.enabled switches ripples and shake off. The permissions are repack.distortion.spawn, repack.distortion.debug and repack.distortion.shake.
- Screen shake: /repack shake <players> <strength> <ticks> [rate balance roll], RepackAPI.shake and the Skript effect "shake player's screen with strength 0.5 for 40 ticks". It fades out. 1.21.6 and newer, and before 26.3 only with Fabulous graphics. Needs repack.distortion.shake.
- Animated text (r4tshader): text in a trigger color is drawn as a moving gradient. Set up in text-effects in config.yml, 1.21.6 and newer.
- Bone models and animations: a model with a rotated group, a freely rotated cube, a cube outside -16 to 32 or an animation is split into bones, one item display each, so it works on every client from 1.21.4 without shaders. Blockbench animations play on blocks as loop, once (then settles back) or hold, and display.animation-mode overrides it. Animations named idle (loops), place (plays on placing, block cannot be broken meanwhile) and break (display.break-animation: delay, linger or off) play on their own.
- /repack animate <animation|none> [loop|once|hold|default] [pos], RepackAPI.playAnimation and stopAnimation, and the Skript effects "play animation ... on custom block at ..." and "stop the animation of custom block at ...".
- Skyboxes: files in skyboxes/ (a panorama .png, a .glsl, or builtin:gradient, stars, clouds), placed by dimension, world and biome with priority and permission. /repack skybox set|off|clear|list, RepackAPI.setSkybox and Skript. 1.21.6 and newer, up to 24 skies.
- resource-pack.send: false lets another plugin send the pack, resource-pack.export writes the zips to a folder, and repack-all.zip serves every client version from one zip.

Changed
- Models no longer become blocks by themselves. Set auto-blocks: true for the old behavior (it replaces create-block-files, which is migrated for you).
- When a settings file is updated the previous version goes in backups/, and only one version back is kept.
- proxy-block is gone from config.yml: each block names its own proxy.block. Mesh elements in a model are skipped with a warning.

Fixed
- Players standing on the edge of a block are no longer pulled back while the pack loads: the blocks around the body and under the feet are left alone.
- Groups in Blockbench 5 files keep their pivot and name; before the pivot was read as 0, 0, 0.
- Old packs in the packs folder are cleaned up: packs nothing refers to are deleted after an hour instead of a day, and also when the server starts.

Replace the jar with the server stopped, then run /repack build. If you relied on every model becoming a block, set auto-blocks: true.

R4T, Out.

tags:
version="1.0.0"
release
modrinth

</div>

<sub>Technical version: `0.1.3-snapshot-nightly`</sub>
