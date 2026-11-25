# Holofote 0.5.0

Pixelated volumetric spotlights (PSX look) you can animate in Flashback replays.

- **Needs:** Minecraft 26.2, Fabric Loader, Fabric API, Flashback 0.43+. Client only. OpenGL only. Iris optional.
- **Use:** in the Flashback editor, Add Element → Holofote. Each `+` keyframe toggles the light (on with a flicker, then off). Edit color, angle, range, intensity, edge softness per keyframe.
- **Test light:** F8 drops one where you look.
- **Config:** `config/holofote.properties` (pixel size, samples, block shadows, cutout on/off). Reloads on F8.
- **Two holofotes in one mod:** without a shaderpack the vanilla holofote draws inside the world (after solid blocks). With an Iris shaderpack on (BSL etc.) the vanilla one turns off and the shader holofote draws on top of the shaderpack's final image, using its depth. Switches by itself within ~1 s when you toggle shaders.
- **Shader options:** `shader=0` turns the light off while a shaderpack is on; `forcaShader` scales brightness only in shader mode (default 1.0).
- **Debug log:** `diag=1` in the config writes GPU readback diagnostics to the log on each F8 / first track light. Off by default.
- **Shadows:** blocks block the beam (no light through roofs).
- **Cutout:** players, villagers, mobs and livrosjogos books inside/behind the beam stay clean (no PSX dither on them). `recorte=0` turns it off.
- **GPUs:** checked offline on both AMD GPUs of a Ryzen 5 3500U laptop (Vega 8 and Radeon 540X, driver 26.5.2): same image, no GL errors, ~5 ms per light pass on the 540X.

Status: 0.5.0 adds the shader holofote and reads the depth mode from the real GL clip-control state. The beam shaders were verified offline in all three depth conventions (vanilla reverse-Z, Iris 0..1, Iris -1..1). Not tested in-game yet; this also covers the 0.4.1 AMD crash fix and the 0.4.0 cutout, which have not run in-game either.
