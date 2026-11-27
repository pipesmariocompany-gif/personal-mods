# Holofote 0.6.1

Pixelated volumetric spotlights (PSX look) you can animate in Flashback replays.

- **Needs:** Minecraft 26.2, Fabric Loader, Fabric API, Flashback 0.43+. Client only. OpenGL only. Iris optional.
- **Use:** in the Flashback editor, Add Element → Holofote. Each `+` keyframe toggles the light (on with a flicker, then off). Edit color, angle, range, intensity, edge softness per keyframe.
- **Test light:** F8 drops one where you look.
- **Config:** `config/holofote.properties` (pixel size, samples, block shadows, cutout on/off). Reloads on F8.
- **Two holofotes in one mod:** without a shaderpack the vanilla holofote draws inside the world (after solid blocks). With an Iris shaderpack on (BSL etc.) the vanilla one turns off and the shader holofote draws on top of the shaderpack's final image, using its depth. Switches by itself within ~1 s when you toggle shaders.
- **Shader options:** `shader=0` turns the light off while a shaderpack is on; `forcaShader` scales brightness only in shader mode (default 1.0).
- **Cinematic shader light (0.6.0):** in shader mode the beam is a smooth volumetric light: forward scattering (brighter looking into the light), drifting dust, block shadows from a per-light shadow map, edge-aware smoothing and upscale, soft lamp halo.
- **Right-click a keyframe** to adjust it. *Look* (saved per keyframe): volume/density, dispersion, dust, lamp halo. *Quality* (all holofotes, saved to `holofote.properties` on this PC): preset Rapido / Equilibrado / Bonito / Maximo, light resolution, samples, shadow cycles, shadow sharpness, smoothing cycles, plus a live GPU cost readout.
- **Cost (Radeon 540X, 1080p, beam filling the screen):** Rapido ~3 ms, Equilibrado ~7 ms, Bonito ~15 ms, Maximo ~55-65 ms (for export). The small editor preview costs much less.
- **Debug log:** `diag=1` in the config writes GPU readback diagnostics to the log on each F8 / first track light. Off by default.
- **Shadows:** blocks block the beam (no light through roofs).
- **Cutout:** players, villagers, mobs and livrosjogos books inside/behind the beam stay clean (no PSX dither on them). `recorte=0` turns it off.
- **GPUs:** checked offline on both AMD GPUs of a Ryzen 5 3500U laptop (Vega 8 and Radeon 540X, driver 26.5.2): same image, no GL errors, ~5 ms per light pass on the 540X.

Status: works in-game (0.6.1 draws the vanilla holofote in a Flashback replay export, no shaderpack). 0.6.1 fixes the light going invisible after the game recreates its screen texture, e.g. when switching replays without restarting: the mod now re-attaches that texture every frame. The cause was reproduced offline on both AMD GPUs; the replay-switch case itself has not been re-tested in-game yet, and 0.6.1 has not been re-tested with a shaderpack. 0.6.0 (tested with Iris + BSL) added the cinematic shader light and its keyframe controls; 0.5.0 added the shader holofote switch, 0.4.1 the AMD crash fix, 0.4.0 the cutout.
