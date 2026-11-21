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

KTPAntiCheat can see that ReShade is loaded. It cannot see which preset is running or judge what that preset does to the picture. That matters most for option B.

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
- **For enforcement:** the anti-cheat can confirm ReShade is loaded, but not that the preset follows the rule. Admins would have to ask for the preset file and check it by hand. A preset can be changed at any moment, so a check shows what a player sent, not necessarily what was running during the match. B1 also means someone has to maintain the list.
- **Draft text:** a row in the §3.5 table: *ReShade: Allowed only with [an approved preset / a preset that uses no depth-buffer shaders and does not increase the visibility of players]*, plus a short sub-rule saying players must provide their preset file when an admin asks (Rule 3.8.a's 24 hours).

### Option C: ReShade is prohibited

ReShade and similar post-processing injectors may not be running during a match.

- **For players:** anyone who uses it, for any reason, has to remove it or turn it off before matches. That includes players who use it for comfort or colour blindness.
- **For enforcement:** the simplest of the three. ReShade being loaded during a match is the violation, and the anti-cheat can see that.
- **Draft text:** a row in the §3.5 table: *ReShade and other post-processing injectors: **NOT Allowed**.*

---

## Things to weigh whichever way you vote

- **Other tools do the same thing.** Graphics-driver filters, driver colour settings and monitor modes like "black equalizer" can also brighten shadows and sharpen the image. None of them is covered by this vote, and the anti-cheat cannot see them. A ban on ReShade does not remove the effect from the game, only one way of getting it.
- **What breaking the rule counts as.** Under Option B or C, a violation could be treated as cheating under §3.3 (zero tolerance) or as a game-file violation with the ordinary penalties in §1.2. The ruleset should say which, so the same conduct does not carry two different penalties.
