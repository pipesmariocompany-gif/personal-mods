# Cuspidor

All versions are kept in this folder. **Put only one of these jars in `mods` at a time.**

| Jar   | Changes                                                                                      | Status                  |
|-------|----------------------------------------------------------------------------------------------|-------------------------|
| 1.0.0 | first version                                                                                | works in-game           |
| 1.1.0 | area spitter block (sizes 3-6), random or organized mode; spitters ignore 1 solid block below | not tested in-game      |
| 1.2.0 | container block that traps cases, invisible in Flashback replays                             | not tested in-game      |
| 1.3.0 | cases lock in place after settling on support, lighter physics                               | tried in-game, heavy while many cases are loose |
| 1.3.1 | up to 300 per second, area outlets fire 3 stacked cases                                      | not tested in-game      |

The notes below describe 1.0.0; later versions change what the table lists.

## 1.0.0 (experimental)

A redstone block that spits game cases downward with rigid body physics (Bullet).

- **Needs:** Minecraft 26.2, Fabric Loader, Fabric API, the `livrosjogos` mod (the cases; not in this repo). **Windows 64-bit only** (bundled native library).
- **Use:** place the block (Redstone tab), right-click it, pick GTA V / GTA VI / Minecraft, set the rate and the total, Save. Power it with a lever.
- **When it fires:** the block turns invisible and the nearby powered lever/button is removed. When it reaches the total, or the pile reaches the outlet, the block disappears.
- **Blocked outlet:** if something is right below it when powered, nothing happens.
- **Options:** rate 1-20 per second; total 1-1000 (also the cap on cases per dimension).
- **Clear:** `/cuspidor limpar` removes the cases in the current dimension and any spitter still running (a running one can't be clicked or broken).
- **Physics:** runs on the server; cases collide with each other and with blocks. Resting cases sleep until something touches them. Players don't push them.
- **Performance:** in a standalone Bullet test (no Minecraft) physics took about 1 ms per tick with 100 cases, 4 ms with 300 and 22 ms with 600 (a tick is 50 ms). Start with 300 or less.
- **Flashback:** this mod adds an entity type, so replays recorded without it may crash while it is installed. Remove the jar to open them.
- **Bundled:** [Libbulletjme](https://github.com/stephengold/Libbulletjme) 23.2.0 (BSD-3-Clause / zlib / MIT); notices in `LICENSE-libbulletjme.txt` inside the jar.

1.0.0 status: works in-game, including Flashback (experimental).
