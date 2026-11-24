# Is ReShade permitted in league play? A ballot item

The ruleset does not mention ReShade. This item asks the league to decide whether it is allowed, and on what terms.

**No ruleset text changes in this PR.** The options below are for the vote. Whichever passes gets written into the ruleset in a follow-up PR, with the Spanish and Portuguese translations after it.

---

## What ReShade is

ReShade is a free post-processing tool. It sits between the game and your screen and changes the finished picture: colour, brightness, contrast, sharpening and similar effects. It installs as a DLL in the game folder and loads when the game starts. Settings are saved as presets, and a player can switch presets at any time, including mid-match.

People use it for different reasons: to make an old game look better, to ease eye strain, or to help with colour blindness. The same controls can also help you see. Raising brightness in dark corners, boosting contrast, or sharpening edges can make a player in shadow easier to spot.

Some shaders also read the depth buffer, which records how far away each pixel is. That lets an effect pick out shapes by distance rather than by lighting. ReShade's standard download is built to switch depth access off when it detects online play, but other builds and modified copies do not.

## Where the ruleset stands today

The nearest rules are §3.4, which lists *"any external program giving unfair advantage"* as cheating, and §3.5, which allows *"only default game files"* plus a short table of exceptions. Neither names ReShade. §3.4 turns on whether there is an advantage, which depends on the preset, and §3.5's table was written for game files like HUDs and crosshairs. Admins have not ruled whether either one covers it, which is why this needs a vote.

## What the anti-cheat can and cannot tell

KTPAntiCheat checks the files in the game folder, so it sees ReShade's DLL when ReShade is installed there. From client version 0.8.4 (not yet released), it also records ReShade's settings file, the preset that file names and ReShade's log, if they are in the game folder, so an admin can read the preset a player had saved. It does not look inside the running game, so it cannot tell whether ReShade's effects are switched on, and the preset it records is the one saved on disk, which a player can change at any time. That matters most for option B.

---

## The options

### Option A: ReShade is permitted

Any preset, any shader.

- **For players:** nothing to check or remove. Use it or don't.
- **For enforcement:** nothing to enforce. The league accepts that some players will tune presets for visibility, and that this is part of the game.
- **Draft text:** a row in the §3.5 table: *ReShade (any preset): Allowed.*

### Option B: ReShade is permitted with limits

ReShade is allowed, but only for cosmetic changes. Two ways to write the limit:

- **B1, an approved list:** the league publishes a set of approved presets, and only those may be used in a match.
- **B2, a description:** any preset is allowed as long as it uses no depth-buffer shaders and does not brighten shadows, outline players, or otherwise make players easier to see.

What it means:

- **For players:** you can keep ReShade, but you are responsible for your preset staying inside the limit. Under B1 that is easy to check; under B2 you have to judge it yourself.
- **For enforcement:** the anti-cheat can confirm ReShade is installed, but not that its effects are on or that the preset follows the rule. From client version 0.8.4 it records the saved preset file, so an admin can check it by hand without asking for it; before that, admins would have to ask for the file. A preset can be changed at any moment, so a check shows what was saved, not necessarily what was running during the match. B1 also means someone has to maintain the list.
- **Draft text:** a row in the §3.5 table: *ReShade: Allowed only with [an approved preset / a preset that uses no depth-buffer shaders and does not increase the visibility of players]*, plus a short sub-rule saying players must provide their preset file when an admin asks (Rule 3.8.a's 24 hours).

### Option C: ReShade is prohibited

ReShade and similar post-processing injectors may not be running during a match.

- **For players:** anyone who uses it, for any reason, has to remove it or turn it off before matches. That includes players who use it for comfort or colour blindness.
- **For enforcement:** the simplest of the three. The anti-cheat sees ReShade's DLL in the game folder. It cannot tell whether the effects were switched on, so the rule should make having ReShade installed during a match the violation, which the anti-cheat can see.
- **Draft text:** a row in the §3.5 table: *ReShade and other post-processing injectors: **NOT Allowed**.*

---

## Things to weigh whichever way you vote

- **Other tools do the same thing.** ReShade is one of several ways to change the finished picture. A ban on ReShade does not remove the effect from the game, only one way of getting it. See the list below.
- **What breaking the rule counts as.** Under Option B or C, a violation could be treated as cheating under §3.3 (zero tolerance) or as a game-file violation with the ordinary penalties in §1.2. The ruleset should say which, so the same conduct does not carry two different penalties.

## Other tools that do the same thing

None of these is covered by this vote. They fall into five kinds, and only the first leaves anything the anti-cheat can see.

1. **Inside the game, like ReShade.** A DLL placed next to the game. SweetFX, ENBSeries, GeDoSaTo and Special K work the same way, but most of them only support Direct3D, and Day of Defeat runs on OpenGL. In practice ReShade is the one that works here. The anti-cheat sees this kind by the DLL in the game folder.
2. **A separate program that redraws the game window.** Magpie and Lossless Scaling capture the game window, apply effects such as sharpening or colour, and show the result in their own window on top. Nothing is added to the game folder.
3. **Graphics-driver settings.** NVIDIA digital vibrance and gamma, NVIDIA App game filters (brightness, sharpening, colour), AMD Radeon Image Sharpening and colour settings, Intel's colour and gamma settings, and helpers like VibranceGUI that switch vibrance on when the game starts. The anti-cheat cannot see these.
4. **Windows itself.** Windows colour filters (including the colour-blind modes), colour profiles, and tools that change screen-wide brightness. The anti-cheat cannot see these.
5. **The monitor.** Gaming-monitor modes that brighten dark areas, such as Black eQualizer or Shadow Boost, and crosshairs drawn by the monitor's own menu, including over a sniper rifle. No software can see these.

**What this means for the vote:** brightening shadows, raising vibrance, sharpening, and even a sniper crosshair (which §3.5 already forbids as a game file) all stay possible through the driver or the monitor, whichever option passes. Option C removes the one tool in this list the anti-cheat can see. It closes one route to the effect, not the effect itself. That is not an argument for or against any option, but it is worth knowing what each one can and cannot achieve.
