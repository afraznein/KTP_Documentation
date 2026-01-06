# KTP League Official Rules

**Day of Defeat 1.3 Competitive Ruleset**

[![Version](https://img.shields.io/badge/Version-Season_9_2026-blue)](#)
[![Game](https://img.shields.io/badge/Game-Day%20of%20Defeat%201.3-green)](#)

> **Note:** These rules govern the KTP competitive league for the Half-Life: Day of Defeat mod. They may be updated as needed (see Rule 1.1). All teams and players are expected to know and abide by these rules. Failure to do so can result in penalties, including suspensions and forfeits.

---

## Table of Contents

- [1. General Rules, Games, and Servers](#1-general-rules-games-and-servers)
- [2. Teams, Regions, Home/Away, and Ringer Rules](#2-teams-regions-homeaway-and-ringer-rules)
- [3. Cheating, Penalties, and Disputes](#3-cheating-penalties-and-disputes)
- [4. Player Rules](#4-player-rules)
- [5. Captain Rules](#5-captain-rules)

---

## 1. General Rules, Games, and Servers

> **Section Summary:** This section covers league administration, definitions of terms, server requirements, and general match procedures.

### 1.1 Rule Modifications

KTP reserves the right to modify or update any league rules at any time as needed. This includes changes necessitated by game updates, new releases, or other factors deemed necessary to the league. Any rule changes will be posted here AND announced publicly (via Discord, website, etc.). Teams are responsible for checking the rules regularly (especially before matches) to ensure they remain in compliance. Best faith efforts will be made to ensure no one misses a rule change.

### 1.2 Penalties for Rule Violations

Upon an infraction of the rules listed here or the rules listed in the KTP Community Rules, the league may apply penalties. Depending on severity, any combination of the following may occur:

- A player (or multiple players) can be suspended
- A single game can be forfeited
- An entire match can be declared a forfeit loss for the offending team

### 1.3 Definitions: Games vs Matches

| Term | Definition |
|------|------------|
| **Game** | A single contest between two teams on one map (i.e., one full round on the chosen map) |
| **Match** | May consist of multiple games between the same teams (e.g., a best-of-three can include up to three separate games on possibly different maps) |

> **Important:** Suspensions are typically given in terms of a number of **games** (or a length of time), rather than entire matches. This distinction is critical for understanding penalty durations.

### 1.4 Valid Game Requirements

For any official game to be valid, the following conditions must be met:

- [ ] The correct map must be played (as scheduled)
- [ ] The correct KTP league config for that map must be used
- [ ] The game must take place on a KTP-approved server

### 1.5 KTP-Approved Servers

All matches must be played on a server that has been approved by KTP admins. To qualify as approved, a server must meet the following requirements:

| Requirement | Description |
|-------------|-------------|
| **Dedicated server** | Must be a dedicated (non-listen) server |
| **Logging enabled** | Server logging must be set to record |
| **HLTV requirement** | An HLTV spectator proxy must be running with a minimum 120-second delay to prevent ghosting |
| **Configuration** | Server and HLTV must be configured with official KTP settings |
| **Final approval** | Admin approval required before server can be used for KTP matches |

### 1.6 Admin Access to Servers

Server owners who wish to host league matches must provide KTP admins with full access to the server:

- Any HLTV passwords
- Server rcon (remote console) password
- Access to the server's control dashboard
- FTP access to server files/logs

### 1.7 Server Crash Procedure

#### Crash within first 5 minutes of a half:
The half must be fully restarted from the beginning (score 0-0)

#### Crash after first 5 minutes of a half:
- The half will be restarted with the score and time remaining set to what they were at the moment of the crash
- Round the time up to the nearest full minute
- The score will need to be manually restored via server commands
- **No player substitutions are allowed** during this mid-game restart

> **Mandatory notification:** Teams must inform a league admin immediately when a crash/restart occurs.

### 1.8 Technical Pauses (Trial Period)

Each team receives 5 minutes of technical pause time per 'game' to address legitimate technical issues. This allowance resets for overtime periods. In best-of-three series, each team receives 5 minutes per individual 'game'.

#### 1.8.a Pause Mechanics

The match plugin automatically triggers a pause 10 seconds after any player disconnect unless the affected team cancels it. Teams may also initiate manual pauses using `.tech` commands. Through use of the plugin, all pauses require confirmation from the opposing team to unpause, followed by an automatic countdown before play resumes. Teams are not charged pause time while waiting for the opposing team to confirm an unpause.

#### 1.8.b Valid Technical Issues

Technical pauses are authorized for disconnects, game crashes, hardware failures, and similar genuine technical problems only. Pauses for tactical discussions, waiting for late players, or deliberate delays are prohibited.

#### 1.8.c Good Faith Requirement

Both teams must act in good faith when using the pause system. Teams must confirm unpauses promptly when their issue is resolved. Abuse of the pause system—including tactical pausing, deliberately delaying unpause confirmation, or false technical claims—will result in warnings, player suspension, or match forfeiture.

#### 1.8.d Trial Status

This pause system is under **TRIAL** evaluation and may be modified or even completely removed based on community usage, feedback, or at admin discretion. This could happen at any point this season.

> **See also:** Rule 1.7 for server crash procedures.

### 1.9 Map Exploits and Illegal Spots

Using restricted or unintended areas of a map is strictly prohibited:

- Standing on tiny invisible ledges or edges not meant to support players
- "Pixel-walking and hanging" (e.g., perching on the ladder in dod_harrington via an exploit)
- Entering any area that is only reachable by using a pixel walk

Violations may result in player suspension and/or forfeiture of the game or match.

### 1.10 Tie Games and Overtime

In the event of a tie game, overtime must be played immediately to determine a winner.

**Overtime format:**
- Two additional halves of **5 minutes each** (teams switch sides for the second OT half)
- If still tied, continue playing additional 5-minute overtime halves until a winner is decided
- Use the overtime config files: normal config name with `_ot` appended (e.g., `ktp_harrington_ot.cfg`)

> **Penalty:** Failure to complete required overtime rounds will result in a loss being recorded for **both teams**.

### 1.11 Spectators

No unauthorized spectators are allowed in the game server during official matches. The only spectators permitted are:

- KTP admins
- Official broadcasters (e.g., HLTV proxy with required delay, or league-sanctioned casters)

### 1.12 Team Admission and Participation Eligibility

KTP reserves the sole and absolute discretion to approve or deny entry to any team. Teams may be denied entry or removed for:

| Reason | Description |
|--------|-------------|
| **Disruptive Conduct** | Behavior intended to provoke conflict, interfere with gameplay, or violate league policies |
| **Operational Unreliability** | Patterns of forfeits, missed matches, excessive roster turnover, or behavior disrupting league scheduling |

### 1.13 BYEs and Forfeit Scoring

- **BYEs:** Awarded the average point value of all teams in the same division, calculated after all matches complete
- **Forfeits:** Only scored after the end of regulation
- **Special case:** If a BYE is awaiting a potential forfeit that is confirmed at regulation end, it will be treated as a BYE and scored using the average point value method

---

## 2. Teams, Regions, Home/Away, and Ringer Rules

> **Section Summary:** This section covers team composition, scheduling, server selection by region, roster management, and rules for using substitute players (ringers).

### 2.1 Team Composition (International vs NA)

| Team Type | Definition |
|-----------|------------|
| **International** | Majority of players (4+) based outside North America (EU, SA, etc.) |
| **North American** | Majority of North American players |

### 2.2 Scheduling Default Match Times

| Scenario | Default Time |
|----------|--------------|
| **Standard** | Sunday at 9:00 PM Eastern Time (EST) |
| **International (east of UTC -2)** | Sunday at 3:00 PM EST |

> Times may adjust for daylight savings time.

### 2.3 Home Team Advantage

#### 2.3.a Standard Matches
The **HOME** team chooses:
- Which KTP-approved server the match will be played on
- Which side (Allies or Axis) their team will start on

#### 2.3.b Best-of-Three (BO3) Matches
Each map is treated independently. The team that picked a map is considered the "home" team for that map.

### 2.4 Server Selection by Region

| Matchup | Server Location | Side Selection |
|---------|-----------------|----------------|
| **NA vs NA** | Central US (default) | Home team chooses |
| **International vs International** | New York | Home team chooses |
| **NA vs International** | New York (mandatory) | **NA team always chooses side** |

### 2.5 Use of Suspended Players

Teams may not roster or play any individuals who are suspended by KTP. Violations result in:
- Team removal from the league
- Possible suspension of all team members
- Suspension of anyone lending accounts to evade bans

### 2.6 Team Name Changes

A team is allowed to change its name **once** during the course of a season. After using this single name change, the team's name is locked for the rest of the season.

### 2.7 Rosters and Roster Locks

| Rule | Details |
|------|---------|
| **Maximum roster size** | 10 players |
| **Lock timing** | End of team registration period |
| **After lock** | No changes to roster, team name, player handles, or SteamIDs |
| **Exception** | Captain may request to remove a player via support ticket |

### 2.7.1 Mid-Season Roster Window

One roster addition window will occur mid-season, announced at least one week in advance.

| Division | Requirements |
|----------|--------------|
| **Highest division** | Additions approved if roster slot available (up to 10) |
| **Other divisions** | Admin approval required (preserves competitive integrity) |

### 2.8 No Bypassing Rules by Agreement

No agreement between team captains can override official rules or active suspensions. Such agreements are invalid and constitute a rule violation.

### 2.9 Ringers

A **ringer** is a player not on your official roster, temporarily used to fill in. Using ringers requires:
- Approval from the opposing team before the match
- Captain's consent

### 2.10 Roster Minimums in Matches

| Requirement | Details |
|-------------|---------|
| **Rostered players** | At least 4 of 6 players must be from official roster |
| **Maximum ringers** | Up to 2 approved ringers allowed |

### 2.11 Team Forfeits and Removal

Teams that repeatedly forfeit may be removed from the league. More than one forfeit in a season may result in removal at admin discretion.

---

## 3. Cheating, Penalties, and Disputes

> **Section Summary:** This section outlines what constitutes cheating, the dispute process, evidence requirements, and penalties for violations.

### 3.1 Admin Authority

League administrators reserve the right to issue suspensions, forfeits, or other penalties as needed. All decisions are aimed at preserving fair play and competitive integrity.

### 3.2 Investigations and Evidence

KTP admins may investigate any player or team for suspicious behavior, including:
- Requesting player POV demos or MOSS anti-cheat files at random
- Conducting spot-checks at any time

**Failure to provide requested materials can result in:**
- Forfeit of the game/match in question
- Suspension of the player

### 3.3 Zero Tolerance for Cheating

Any player found cheating will be suspended (or banned) from KTP, and any influenced match results are subject to being overturned or forfeited.

### 3.4 Definition of Cheating

Cheating includes (but is not limited to):
- Wallhacks (seeing enemies through walls)
- Aimbots (automatic target acquisition)
- Illegally modifying game files
- Any external program giving unfair advantage
- Snap tap, rapid trigger, or any mechanical or software-based input enhancements that allow firing beyond intended game limits

### 3.5 Allowed & Prohibited Game Files

Only default game files may be used, with these exceptions:

#### Permitted Modifications:
| Modification | Status |
|--------------|--------|
| Approved custom scoreboard HUD/UI | Allowed |
| Custom HLTV models | Allowed |
| ClientScheme.res modifications | Allowed |
| TrackerScheme.res modifications | Allowed |
| Custom crosshair (non-sniper weapons) | Allowed |
| Custom crosshair for sniper rifle | **NOT Allowed** |

### 3.6 In-Game Spectator Rule (No Spectating Once Live)

Once a match has gone "live", no player is allowed to use spectator mode. **Spec hopping** is considered cheating.

**Exceptions:**
- Player killed at exact moment of full map capture
- Player becomes stuck in map geometry

### 3.7 Filing Disputes

Disputes must be filed by the team captain **within 24 hours** of match completion.

| Season Phase | Dispute Limit |
|--------------|---------------|
| Regular season | 2 cheating disputes |
| Post-season (playoffs) | 1 cheating dispute |

> **Note:** Valid disputes (where accused is found guilty) do not count against your limit.

### 3.8 Dispute Process for Accused Players

#### 3.8.a Evidence Submission Deadline
Players have **24 hours from notification** to submit:
- POV demos
- MOSS files
- Any other requested materials

#### 3.8.b Consequences and Investigation
- Failure to provide files may result in suspension and/or forfeit
- Admins may review demos and MOSS files from prior/subsequent matches
- Player may be subject to additional scrutiny in future games

### 3.9 MOSS Anti-Cheat Submissions

MOSS files are **not collected weekly** on a routine basis. However, in the event of a dispute or random check, players must provide their MOSS file and demos from the match in question.

---

## 4. Player Rules

> **Section Summary:** This section outlines player registration, identity requirements, recording obligations, file retention, and prohibited behaviors.

### 4.1 Player Registration and Identity

#### 4.1.a Community Rules and Conduct
All players agree to abide by the **KTP Community Rules** at all times.

#### 4.1.b Alias and SteamID Registration
- One in-game alias and one Steam account per player
- Allowed to change alias and/or SteamID **once** per season
- Changes must be reported to league admins

#### 4.1.c In-Game Identity Requirements
- Must use exact registered SteamID
- Must use team tag and registered player handle
- Minor formatting variations allowed (color codes, abbreviations)

#### 4.1.d File Integrity and CVAR Checks
All players must comply with file-integrity and CVAR checks. Players must not interfere with or bypass these systems.

#### 4.1.e MOSS Anti-Cheat and Recording

Every player must use **MOSS (Mission Officer Security Software)** during each match.

**Requirements:**
- [ ] Do not alter or tamper with the MOSS ZIP file
- [ ] Rename the file after match (e.g., `PlayerName_vs_TeamX_Week3.zip`)
- [ ] Be prepared to provide it to admins if requested
- [ ] Never modify the contents of the MOSS zip

#### 4.1.f POV Demos and Screenshots

**POV Demos:**
- Record one POV demo for each half (two demos per full game)
- Start recording before first round, stop when half ends

**Pre-Game Screenshot:**
- Take screenshot showing at least one player model from each team
- Verifies player models/skins are correct

**End-of-Half Scoreboard Screenshots:**
- Screenshot the scoreboard at the end of each half
- Used to verify score and player participation

**Stay Until Game End:**
- Do not disconnect until match is completely over
- If you crash, rejoin immediately

#### 4.1.g Character Name Length and Format

All player aliases (handles), team tags, and full in-game names must comply with the following technical requirements to ensure compatibility with the game engine:

**Maximum Length:**
Player aliases and team tags must not exceed 30 visible characters. Full in-game names (team tag + player handle) must also not exceed 30 visible characters total.

**Character Set Restriction:**
Only standard ASCII characters are permitted. This includes:
- Letters: A-Z, a-z
- Numbers: 0-9
- Basic symbols: ! @ # $ % ^ & * ( ) - _ = + [ ] { } | \ ; : ' " , . < > ? / ~
- Spaces (though excessive spacing is discouraged)

**Prohibited:**
The following are not allowed in player names or team tags:
- UTF-8, Unicode, or multi-byte characters (e.g., emoji, non-Latin alphabets, special symbols like ™ © ®)
- Characters outside the standard ASCII range
- Any characters that may cause display issues or engine instability

**Enforcement:**
Player names or team tags that violate these requirements must be changed before match play.

### 4.2 VODs Are Not Acceptable Replacements

Video recordings or Twitch VODs are **NOT** substitutes for demos or MOSS. You must still record in-game demos and run MOSS even if streaming.

### 4.3 File Retention

Retain all match files **for the duration of the season**:
- POV demos for each half
- All required screenshots
- MOSS ZIP files from each match

### 4.4 Player Boosting

Boosting is **allowed only if** the destination area is reachable by a single player without a boost. Boosting to access glitched or unintended areas is illegal.

### 4.5 Voice Commands and Signals

Voice commands should be used for team communication only. Excessive use to taunt, annoy, or "neg" opponents is not allowed.

### 4.6 Forbidden Key Bindings (Attack/Duck)

Players are prohibited from:
- Binding `+attack` to any key in combination with another action
- Binding `+attack` or `+duck` to mousewheel to accelerate firing or bypass stamina restrictions

### 4.7 No Automated Scripts

Players may not use scripts to automate:
- Player attacking
- Player movement
- Rapid-fire
- Auto-recoil compensation
- Automated jumping or movement patterns

### 4.8 Exploiting Movement/Animation

Players may not use hand signals, voice commands, or cvar toggles with movement commands to make their player model harder to hit. Any tactic that warps, jitters, or misaligns your hitbox is illegal.

### 4.9 Glitches and Exploits

The following are considered cheating:

| Exploit | Description |
|---------|-------------|
| **Weapon Spawning** | Spawning extra weapons/ammo to bypass class limitations |
| **Grenade Glitch** | Duplicating grenades or bypassing normal mechanics |
| **Map Bugs** | Clipping through walls, getting under/above map |
| **Pixel Walking** | Using unintended collision spots for unfair positioning |
| **Wall Glitching** | Making player model poke through walls to see/shoot other side |

> **General principle:** Any exploit not part of fair, intended gameplay is illegal, even if not explicitly listed.

---

## 5. Captain Rules

> **Section Summary:** This section outlines the specific responsibilities and requirements for team captains.

### 5.1 Captain's In-Game Duties

#### 5.1.a Readable Scoreboards
Captains must configure their client settings so end-of-half scoreboards are easy to read in screenshots (high-contrast, clear font).

#### 5.1.b RCON Status Screenshot
Captains must take one `rcon status` screenshot per game to prove player SteamIDs.

### 5.2 Communication and Availability

- Captains must not be banned from KTP Discord
- Must be reachable and respond to scheduling messages promptly
- If absent, designate an acting captain and inform admins

### 5.3 Match Punctuality and Forfeit Wins

| Time | Action |
|------|--------|
| **+10 minutes** | Document and alert an admin if no word from opposing team |
| **+15 minutes** | Admin can officially call no-show and award forfeit win |

### 5.4 Fair Scheduling

Captains must schedule with integrity:
- Be proactive in communication
- Offer multiple reasonable times
- Reply promptly
- Keep records of scheduling communications

### 5.5 Roster and Ringer Checks

Captains must verify player eligibility before match starts:
- Check opposing players match roster names and SteamIDs
- Verify any ringers have been approved

> **Important:** Once a match is completed, you cannot dispute based on an ineligible player if you had the opportunity to catch it beforehand.

### 5.6 Reporting Scores

The **winning team captain** must report results within **1 hour of match completion**:

- [ ] Final score for each game/half
- [ ] Adjusted client scheme screenshots of both end-rounds
- [ ] Tallied final result

Post in the designated KTP Discord scores channel.

### 5.7 Playoff Map Vetoes (BO3 Matches)

Captains must submit vetoes and map picks **at least 72 hours before default match start time**.

> **Penalty:** Late submissions result in admins performing vetoes on the team's behalf.

### 5.8 Captain Accountability

Captains are responsible for ensuring team members understand and follow all rules. Repeated team violations may result in captain suspension for negligence.

---

**End of Rules Document**

*Last Updated: January 2026*

*Questions? Contact KTP Admins via Discord or the league website.*
