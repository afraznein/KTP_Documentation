# KTP League CVAR Requirements

**Day of Defeat 1.3 Client Variable Settings**

[![Version](https://img.shields.io/badge/Version-Season%202026-blue)](#)
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
| `gl_clear` | `0` | When 1, makes cracks between textures visible |
| `gl_d3dflip` | `0` | When 1, makes cracks between textures visible |
| `gl_monolights` | `0` | Uniform light source with no shadows (OpenGL only) |
| `gl_nobind` | `0` | Replaces textures with alphanumeric characters when enabled |
| `gl_nocolors` | `0` | Disable colors (OpenGL only) |
| `gl_overbright` | `0` | Maximum brightness mode |
| `gl_picmip` | `0` | Texture mipmap level. High values reduce wall textures to solid-color blocks; locked to 0 to prevent contrast-wallhack abuse. **Do not change.** |
| `gl_playermip` | `0` | Player rendering quality. Higher = faster but lower quality |
| `r_drawentities` | `1` | Drawing player models and sprites (0=none, 1=normal, 2=no textures, 3=hitbox, 4=translucent hitboxes) |
| `r_drawviewmodel` | `1` | Toggles drawing player weapon model |
| `r_dynamic` | `1` | Dynamic lighting (flashlight reflections, etc.) |
| `r_fullbright` | `0` | Maximum brightness in local games only |
| `r_glowshellfreq` | `2.2` | Glow shell animation speed — DoD engine default. Used by flag-carrier glow shimmer. Enforced at the engine default value as an integrity check (catches autoexec overrides). **Do not change.** |
| `r_lightmap` | `0` | Software rendering - displays lightmaps (0-3) |
| `r_luminance` | `0` | Makes the map look blue/green when enabled |
| `r_traceglow` | `0` | Glow-shell trace debug — DoD engine default. Enforced at default as an integrity check. **Do not change.** |
| `texgamma` | `2` | Texture gamma level |

### Audio

| CVAR | Value | Description |
|------|-------|-------------|
| `s_show` | `0` | Shows on screen what sounds are played |

### Movement & Input

| CVAR | Value | Description |
|------|-------|-------------|
| `cl_bobcycle` | `0.8` | How frequently player view bobs while running |
| `cl_bobup` | `0.5` | Amount of movement before view-bob kicks in |
| `cl_pitchdown` | `89` | Maximum angle to look down |
| `cl_pitchup` | `89` | Maximum angle to look up |
| `cl_pitchspeed` | `225` | Keyboard look-up/down speed (degrees per second). Locked to GoldSrc default to prevent alias-based no-recoil scripts. **Do not change.** |
| `cl_yawspeed` | `210` | Keyboard look-left/right speed (degrees per second). Locked to GoldSrc default. **Do not change.** |
| `cl_anglespeedkey` | `0.67` | Multiplier applied to `cl_pitchspeed`/`cl_yawspeed` while +speed is held. Locked to GoldSrc default. **Do not change.** |
| `m_pitch` | `0.022` | Mouse pitch (up/down) speed sensitivity multiplier |
| `m_side` | `0.8` | Mouse side-strafe speed multiplier. Locked to GoldSrc default. **Do not change.** |

### Network & Prediction

| CVAR | Value | Description |
|------|-------|-------------|
| `cl_mousegrab` | `1` | Linux gold source update 2013. MOSS implications, no gameplay effect |
| `rate` | `100000` | Client to server transmission rate (bytes/sec). **Do not change.** |

#### Player-tunable network cvars (no enforcement)

These cvars affect your own client behavior. KTPCvarChecker does NOT enforce them — your choice. Defaults shown.

| CVAR | Default | Notes |
|------|---------|-------|
| `cl_lc` | `1` | Server-side lag compensation for YOUR shots. `0` disables rewind — you must lead targets by your full ping. **Self-handicap, not an exploit.** Some players prefer `0` to eliminate "shot through wall" feel; most leave it at `1`. |
| `cl_lw` | `1` | Client-side weapon prediction. `0` makes weapon animations server-authoritative (feels laggy at non-LAN ping). Setting `0` also disables lag compensation (gates require both `lc=1` AND `lw=1`). **Self-handicap, not an exploit.** |

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
| `lightgamma` | **1.809** - **3.0** | 2.5 | Lighting gamma value. Values below 1.809 crash DoD |
| `cl_bob` | **0** - **0.011** | 0.005 | Amount that view bobs while running |
| `cl_updaterate` | **100** - **120** | - | Updates requested from server per second. **KTP required.** |
| `cl_cmdrate` | **100** - **1000** | - | Times per second client updates the server. Useful range = ≤ your client fps; setting higher than fps wastes bandwidth. v7.25: ceiling raised from 500 to 1000 to enable testing high-resolution input on 1000fps clients. **KTP required.** |
| `ex_interp` | **0.01** - **0.05** | - | Interpolation time between updates. **KTP required.** |
| `fps_max` | **60** - **750** | - | Maximum frames per second. **KTP required.** |

---

## Quick Reference

### Network Settings (Copy/Paste)

```
cl_updaterate 101
cl_cmdrate 101
rate 100000
ex_interp 0.01
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

*Last Updated: April 2026 (v7.26 fixed `r_glowshellfreq` enforcement value 0 → 2.2 to match the DoD engine default — clients with the natural default were being kicked under the previous v7.24 enforcement of 0; that "0" rationale didn't actually block ESP attackers and broke flag-carrier glow rendering. v7.25 dropped cl_lc and cl_lw from enforcement after engine-source audit confirmed self-handicap-only behavior; raised cl_cmdrate ceiling 500→1000 for high-fps client testing. v7.24 had added 7 cvars: cl_pitchspeed / cl_yawspeed / cl_anglespeedkey / m_side for keyboard-look defense, gl_picmip / r_glowshellfreq / r_traceglow for visual-exploit defense — gl_picmip enforcement still active for picmip wallhack defense.)*

*Questions? Contact KTP Admins via Discord or the league website.*
