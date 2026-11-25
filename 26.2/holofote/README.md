# Holofote 0.4.1

Pixelated volumetric spotlights (PSX look) you can animate in Flashback replays.

- **Needs:** Minecraft 26.2, Fabric Loader, Fabric API, Flashback 0.43+. Client only. OpenGL only.
- **Use:** in the Flashback editor, Add Element → Holofote. Each `+` keyframe toggles the light (on with a flicker, then off). Edit color, angle, range, intensity, edge softness per keyframe.
- **Test light:** F8 drops one where you look.
- **Config:** `config/holofote.properties` (pixel size, samples, block shadows, cutout on/off). Reloads on F8.
- **Debug log:** `diag=1` in the config writes GPU readback diagnostics to the log on each F8 / first track light. Off by default.
- **Off when:** an Iris shaderpack is active.
- **Shadows:** blocks block the beam (no light through roofs).
- **Cutout:** players, villagers, mobs and livrosjogos books inside/behind the beam stay clean (no PSX dither on them). `recorte=0` turns it off.

Status: 0.4.1 fixes a native crash on AMD (atio6axx.dll in glReadPixels) when the first track light turned on: the debug readback used the pixel-pack state Minecraft leaves behind after a screenshot copy (`GL_PACK_ROW_LENGTH`) and wrote past its buffer. Readbacks now reset and restore pack state, and the debug readback is off by default. Verified offline on a Vega 8; the cutout from 0.4.0 has still not run in-game.
