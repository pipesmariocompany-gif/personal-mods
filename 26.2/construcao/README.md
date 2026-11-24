# Construcao 0.1.0

Reveal a WorldEdit build inside a Flashback replay: random, bottom-up or top-down, at the exact spot it was copied from. No pasting, no positioning.

- **Needs:** Minecraft 26.2, Fabric Loader, Flashback 0.43+, WorldEdit (only to save the `.schem`). Client only.
- **Save the build:** `//wand`, mark the two corners, `//copy`, `//schem save <name>` (goes to `config/worldedit/schematics`).
- **Use:** in the Flashback editor, Add Element → Schematic. First `+` = start (0 layers), second `+` = end (finished). Click either keyframe to pick the file and the build type.
- **Options:** random / bottom-up / top-down; per layer random blocks or whole layer at once; constant speed or same time per layer; ease in/out; seed; original or manual position ("Move to camera", like `//paste`); rotation; editor-only full preview.
- **Recorded build:** "hide the recorded build" (on by default) turns the unbuilt blocks into air, so a build that is already in the recording disappears before the start and builds itself up to the end. Off = blocks appear over whatever is there.
- **How:** blocks are set on the replay server the same way as Flashback's own Block Override, so it works in preview, scrubbing and export, with light and block entities. Deleting/disabling the track brings the recorded blocks back.
- **Limits:** entities (item frames, armor stands, mobs) are not hidden; blocks change once per replay tick (20/s); only `.schem` (Sponge v1/v2/v3), not old MCEdit `.schematic`.
- **Backups:** projects with a Schematic track are copied to `config/construcao/backups` (Flashback deletes projects it can't read if the mod is removed).

Status: works in-game.
