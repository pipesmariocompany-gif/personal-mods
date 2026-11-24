# Holofote 0.4.0

Pixelated volumetric spotlights (PSX look) you can animate in Flashback replays.

- **Needs:** Minecraft 26.2, Fabric Loader, Fabric API, Flashback 0.43+. Client only. OpenGL only.
- **Use:** in the Flashback editor, Add Element → Holofote. Each `+` keyframe toggles the light (on with a flicker, then off). Edit color, angle, range, intensity, edge softness per keyframe.
- **Test light:** F8 drops one where you look.
- **Config:** `config/holofote.properties` (pixel size, samples, block shadows, cutout on/off). Reloads on F8.
- **Off when:** an Iris shaderpack is active.
- **Shadows:** blocks block the beam (no light through roofs).
- **Cutout:** players, villagers, mobs and livrosjogos books inside/behind the beam stay clean (no PSX dither on them). `recorte=0` turns it off.

Status: 0.4.0 adds the cutout. Not tested in-game yet (0.3.1 fixed the AMD driver crash from 0.3.0).
