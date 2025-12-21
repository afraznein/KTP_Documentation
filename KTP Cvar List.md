# KTP League CVAR Requirements

**Day of Defeat 1.3 Client Variable Settings**

[![Version](https://img.shields.io/badge/Version-Season%202025-blue)](#)
[![Game](https://img.shields.io/badge/Game-Day%20of%20Defeat%201.3-green)](#)

> All players must use these CVAR settings during KTP matches. Fixed values are mandatory unless a range is specified. The KTP server will automatically check and enforce these values.

---

## Table of Contents

- [Fixed Value CVARs](#fixed-value-cvars)
  - [Graphics & Rendering](#graphics--rendering)
  - [Audio](#audio)
  - [Movement & Input](#movement--input)
  - [Network & Prediction](#network--prediction)
  - [HUD & Interface](#hud--interface)
- [Range-Based CVARs](#range-based-cvars)

---

## Fixed Value CVARs

These CVARs must be set to the exact value specified. The server will automatically correct any deviations.

### Graphics & Rendering

| CVAR | Value | Description |
|------|-------|-------------|
| `fastsprites` | `0` | Sets the complexity of smoke sprites. 0 looks the best (range: 0-2) |
| `gl_affinemodels` | `0` | Texture autocorrection on models. 0 = enabled for proper perspective |
| `gl_alphamin` | `0.25` | Minimum alpha blending level |
| `gl_clear` | `0` | When 1, makes cracks between textures visible |
| `gl_cull` | `1` | Renders only visible objects. 0 will slow FPS |
| `gl_d3dflip` | `0` | When 1, makes cracks between textures visible |
| `gl_dither` | `1` | Toggles dithering. Set to 0 if your card renders >16 bit color |
| `gl_keeptjunctions` | `1` | Toggles showing of cracks between textures |
| `gl_lightholes` | `1` | Toggles light holes |
| `gl_monolights` | `0` | Uniform light source with no shadows (OpenGL only) |
| `gl_nobind` | `0` | Replaces textures with alphanumeric characters when enabled |
| `gl_nocolors` | `0` | Disable colors (OpenGL only) |
| `gl_overbright` | `0` | Maximum brightness mode |
| `gl_palette_tex` | `1` | Toggles paletted textures |
| `gl_picmip` | `0` | Rendering quality. Higher = faster but lower quality (range: 0-2) |
| `gl_playermip` | `0` | Player rendering quality. Higher = faster but lower quality |
| `gl_round_down` | `3` | Texture rounding down value. Higher = faster but lower quality |
| `r_bmodelinterp` | `1` | Brush model position interpolation (smooths presentation) |
| `r_drawentities` | `1` | Drawing player models and sprites (0=none, 1=normal, 2=no textures, 3=hitbox, 4=translucent hitboxes) |
| `r_drawviewmodel` | `1` | Toggles drawing player weapon model |
| `r_dynamic` | `1` | Dynamic lighting (flashlight reflections, etc.) |
| `r_fullbright` | `0` | Maximum brightness in local games only |
| `r_glowshellfreq` | `2.2` | Frequency of shimmering on glowing shells (flags/keys) |
| `r_lightmap` | `0` | Software rendering - displays lightmaps (0-3) |
| `r_traceglow` | `0` | Includes monsters in glow sprite occlusion checking |
| `r_wadtextures` | `0` | Enables wad textures |
| `r_luminance` | `0` | Makes the map look blue/green when enabled |
| `texgamma` | `2` | Texture gamma level |

### Audio

| CVAR | Value | Description |
|------|-------|-------------|
| `ambient_fade` | `100` | Distance at which ambient sounds fade away |
| `ambient_level` | `0.3` | Sound level for ambient sounds |
| `s_show` | `0` | Shows on screen what sounds are played |

### Movement & Input

| CVAR | Value | Description |
|------|-------|-------------|
| `cl_bobcycle` | `0.8` | How frequently player view bobs while running |
| `cl_bobup` | `0.5` | Amount of movement before view-bob kicks in |
| `cl_upspeed` | `320` | Climb up speed of a player |
| `cl_movespeedkey` | `0.3` | Movement speed for keyboard use |
| `cl_yawspeed` | `210` | Turning speed (server limited) |
| `cl_pitchspeed` | `225` | Speed at which the pitch changes |
| `cl_pitchdown` | `89` | Maximum angle to look down |
| `cl_pitchup` | `89` | Maximum angle to look up |
| `cl_anglespeedkey` | `0.67` | Speed that direction keys change view angle |
| `m_pitch` | `0.022` | Mouse pitch (up/down) speed sensitivity multiplier |
| `m_side` | `0.8` | Mouse strafing speed sensitivity multiplier |
| `lookspring` | `0` | Automatic view centering when mlook is deactivated |
| `lookstrafe` | `0` | Mouse strafing when mlook is active |
| `cl_gaitestimation` | `1` | Estimated player stepping motion. Disable to reduce "ice skating" |

### Network & Prediction

| CVAR | Value | Description |
|------|-------|-------------|
| `cl_fixtimerate` | `7.5` | Msec per frame of "clock drift" fixup for server timestamp sync |
| `cl_lc` | `1` | Server-side hit computation and lag compensation. **Do not change.** |
| `cl_lw` | `1` | Client-side weapon firing prediction. **Do not change.** Disabling also disables lag compensation. |
| `cl_mousegrab` | `1` | Linux gold source update 2013. MOSS implications, no gameplay effect |

### HUD & Interface

| CVAR | Value | Description |
|------|-------|-------------|
| `hud_takesshots` | `1` | Auto-save a scoreboard screenshot at the end of a map |
| `cl_showevents` | `0` | Shows events like weapon firing (events listed in dod/events/) |

---

## Range-Based CVARs

These CVARs must be within the specified range. Values outside the range will be corrected by the server.

| CVAR | Range | Default | Description |
|------|-------|---------|-------------|
| `lightgamma` | **1.81** - **3.0** | 2.5 | Lighting gamma value. Values below 1.81 crash DoD |
| `cl_smoothtime` | **0** - **0.1** | 0.1 | View smoothing after prediction error. 0 shows actual player positions (may cause jumps) |
| `cl_bob` | **0** - **0.011** | 0.005 | Amount that view bobs while running |
| `cl_updaterate` | **100** - **120** | - | Updates requested from server per second. Lower for more players. **KTP required.** |
| `cl_cmdrate` | **100** - **500** | - | Times per second client updates the server. **KTP required.** |
| `rate` | **100000** - **1000000** | - | Client to server transmission rate (bytes/sec). **KTP required.** |
| `ex_interp` | **0** - **0.03** | - | Interpolation time between updates. Set to 0 for auto (1/cl_updaterate). **KTP required.** |
| `fps_max` | **60** - **500** | - | Maximum frames per second. **KTP required.** |

---

## Quick Reference

### Network Settings (Copy/Paste)

```
cl_updaterate 101
cl_cmdrate 101
rate 100000
ex_interp 0
fps_max 100
```

### Verify Your Settings

To check your current CVAR values in-game, open the console (`~`) and type the CVAR name without a value:

```
] cl_updaterate
"cl_updaterate" is "101"
```

---

## Important Notes

1. **Automatic Enforcement**: The KTP server automatically checks and corrects CVARs that are out of compliance
2. **cl_filterstuffcmd**: Must be set to `0` to allow the server to correct your CVARs
3. **Recording**: These settings do not affect your ability to record demos or run MOSS
4. **Performance**: If you experience performance issues, contact a KTP admin before changing any locked CVARs

---

*Last Updated: December 2025*

*Questions? Contact KTP Admins via Discord or the league website.*
