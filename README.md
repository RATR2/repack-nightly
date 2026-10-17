<div align="center">

**Version 0.1.2 - [`05f2b6b`](https://github.com/RATR2/repack/commit/05f2b6b31993bded00fe71f880cde4f099d237fd)**

Added
- The pack is rebuilt by itself a few seconds after you save a model or block file, quietly: nobody online is sent anything. Players who join get the newest build (resource-pack.join-latest-build: false gives them only the pack last pushed).
- /repack push sends the pack to everyone online, or /repack push <player> to one player. /repack reload now reads the block files, builds the pack and pushes it to everyone online. /repack build only builds.
- While a client reloads a pack Repack sent it, the player is held for 20 seconds at most: they cannot be hurt, move, attack or interact, they see no other entities, and the blocks around them look like black concrete. It cannot start again for two minutes. Switch it off with resource-pack.invulnerable-while-loading, the black blocks with resource-pack.black-blocks-while-loading, and set the size with resource-pack.loading-radius.
- Operators see a progress boss bar while the pack builds (workflow.progress-bar). workflow.build-on-change turns the automatic rebuild off.
- Converted models are cached in plugins/Repack/cache/models, so a build only converts the models that changed. /repack build fresh ignores the cache.
- guide.md for server owners and dev.md for Skript and the Java API.
- Nightly builds of every commit are published to RATR2/repack-nightly.

Fixed
- Pack downloads are served in parallel, so one slow player no longer holds up everyone else's.
- A malformed .bbmodel is an error for that file only instead of stopping the whole build, and a model with a cube outside the range the game loads is left out with an error.
- Block files with names that cannot be ids (spaces, dots) are reported instead of silently breaking saved blocks.
- Pack files are written safely, a damaged one is repaired by the next build, and old unused packs are deleted after a day.
- /give shows the amount it actually gave, /repack push counts only the players who could get a pack, and a model is no longer spawned twice when it is shown twice.
- The log warns when players would be told to download the pack from localhost.

tags:
version="0.1.2"
release

</div>

<sub>Technical version: `0.1.2-snapshot-nightly`</sub>
