# Holofote 0.3.1

Pixelated volumetric spotlights (PSX look) you can animate in Flashback replays.

- **Needs:** Minecraft 26.2, Fabric Loader, Fabric API, Flashback 0.43+. Client only. OpenGL only.
- **Use:** in the Flashback editor, Add Element → Holofote. Each `+` keyframe toggles the light (on with a flicker, then off). Edit color, angle, range, intensity, edge softness per keyframe.
- **Test light:** F8 drops one where you look.
- **Config:** `config/holofote.properties` (pixel size, samples, block shadows on/off). Reloads on F8.
- **Off when:** an Iris shaderpack is active.
- **Shadows:** blocks block the beam (no light through roofs).

Status: 0.3.1 fixes the AMD driver crash from 0.3.0. Not tested in-game yet.
