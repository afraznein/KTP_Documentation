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

> 📖 For the full explanation of these settings — how GoldSrc networking works, why each value is what it is, and when it's legitimate to deviate — see the **[KTP Netcode Guide](http://74.91.112.242/netcode/)**.

| CVAR | Value | Description |
|------|-------|-------------|
| `rate` | `100000` | Client to server transmission rate (bytes/sec). **Do not change.** |

#### Player-tunable network cvars (no enforcement)

These cvars affect your own client behavior. KTPCvarChecker does NOT enforce them — your choice. Defaults shown.

| CVAR | Default | Notes |
|------|---------|-------|
| `cl_mousegrab` | `1` | Whether the engine confines your mouse cursor to the game window. Client-only — the server never sees it, no gameplay/aim effect (aim uses raw input regardless). `1` makes the cursor catch monitor corners and break on alt-tab / multi-monitor in windowed mode. **Recommended: `0` for windowed or multi-monitor play, `1` for exclusive fullscreen.** (No longer enforced as of KTPCvarChecker 7.30.) |
| `cl_lc` | `1` | Server-side lag compensation for YOUR shots. `0` disables rewind — you must lead targets by your full ping. **Self-handicap, not an exploit.** Some players prefer `0` to eliminate "shot through wall" feel; most leave it at `1`. **Recommended: 1.** |
| `cl_lw` | `1` | Client-side weapon prediction. `0` makes weapon animations server-authoritative (feels laggy at non-LAN ping). Setting `0` also disables lag compensation (gates require both `lc=1` AND `lw=1`). **Self-handicap, not an exploit.** **Recommended: 1.** |
| `cl_fixtimerate` | `7.5` | How aggressively your client corrects its local clock toward the server's timestamp (ms of correction allowed per frame). No competitive surface — clock sync happens regardless. The default is a known cause of **weapon viewmodel animation skipping** in GoldSrc; if your weapon animations stutter, lower it (toward `0`) for smoother viewmodels. **Recommended: 7.5 unless you see weapon skipping.** |
| `cl_smoothtime` | `0.1` | How long (seconds) your client takes to visually smooth out prediction-error corrections on YOUR OWN movement (teammate bumps, knockback, edge landings). During the smoothing window your rendered position lags the server-authoritative one — a small aim discrepancy. `0.01` blends the correction over ~one update interval: effectively instant accuracy without single-frame snapping (old league convention). **Recommended: 0.01. High-ping players (100ms+) can use the 0.1 default for comfort — their corrections are larger and more frequent.** |

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
| `cl_updaterate` | **100** - **120** | - | Updates requested from server per second. The client internally caps processing at **102** — values 103-120 pass the check but do nothing, so set exactly `102`. **KTP required.** |
| `cl_cmdrate` | **100** - **1000** | - | Times per second client updates the server. Useful range = ≤ your client fps; setting higher than fps wastes bandwidth. v7.25: ceiling raised from 500 to 1000 to enable testing high-resolution input on 1000fps clients. **KTP required.** |
| `ex_interp` | **0.01** - **0.05** | - | Interpolation time between updates. **Set 0.01** on a clean connection. Raise ONLY for loss/jitter on your own connection (check `net_graph 1`): 0.02 rides through a single lost packet; 0.02-0.03 for chronically jittery routes; above 0.03 has no legitimate case. Ping alone — yours or your opponents' — is not a reason: latency delays the stream uniformly and lag compensation accounts for it (the server rewinds by ping + interp, so higher interp costs reaction time, not hit registration). **KTP required.** |
| `fps_max` | **60** - **750** | - | Maximum frames per second. **KTP required.** |

---

## Quick Reference

### Recommended Settings (Copy/Paste)

```
rate 100000          // locked by the server — anything else is auto-corrected
cl_updaterate 102    // the true client maximum (client caps at 102 internally)
cl_cmdrate 101       // match your fps_max — can't send more packets than frames
ex_interp 0.01       // one update interval of buffer; you see enemies closest to true position
fps_max 100          // full physics fidelity; use your monitor refresh (144/240) if higher
cl_lc 1              // lag compensation for your shots — 0 means leading by your full ping
cl_lw 1              // client weapon prediction — 0 also disables lag compensation
cl_fixtimerate 7.5   // client clock-sync speed (default) — lower toward 0 only if weapon animations skip
cl_smoothtime 0.01   // near-instant prediction-error correction — 0.1 default is the high-ping comfort option
```

If you run a higher frame cap than 100, raise `cl_cmdrate` to match it (e.g. `fps_max 240` → `cl_cmdrate 250`).

Full reasoning behind every value, plus troubleshooting: **[KTP Netcode Guide](http://74.91.112.242/netcode/)**.

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

*Last Updated: July 2026 (quick-reference refreshed against the live fleet config + KTPCvarChecker 7.29: `cl_updaterate` recommendation corrected 101 → 102 [true client cap], per-setting context added, `cl_lc`/`cl_lw`/`cl_fixtimerate`/`cl_smoothtime` guidance added to the player-tunable section. Prior update April 2026: v7.26 fixed `r_glowshellfreq` enforcement value 0 → 2.2 to match the DoD engine default — clients with the natural default were being kicked under the previous v7.24 enforcement of 0; that "0" rationale didn't actually block ESP attackers and broke flag-carrier glow rendering. v7.25 dropped cl_lc and cl_lw from enforcement after engine-source audit confirmed self-handicap-only behavior; raised cl_cmdrate ceiling 500→1000 for high-fps client testing. v7.24 had added 7 cvars: cl_pitchspeed / cl_yawspeed / cl_anglespeedkey / m_side for keyboard-look defense, gl_picmip / r_glowshellfreq / r_traceglow for visual-exploit defense — gl_picmip enforcement still active for picmip wallhack defense.)*

*Questions? Contact KTP Admins via Discord or the league website.*
