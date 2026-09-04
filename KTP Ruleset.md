# KTP League Official Rules

**Day of Defeat 1.3 Competitive Ruleset**

[![Version](https://img.shields.io/badge/Version-Season_10_2026-blue)](#)
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
| **Game** | A single contest between two teams on one map consisting of two halves (teams switch sides at halftime) |
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

> **Note:** These same crash procedures apply during overtime periods. The 5-minute threshold applies to each overtime half independently.

### 1.8 Technical Pauses (Trial Period)

Each team receives 5 minutes of technical pause time per game (regulation) to address legitimate technical issues. Unused regulation pause time does NOT carry into overtime. Each overtime period provides a fresh 5 minutes of pause time per team. In best-of-three series, each team receives 5 minutes per individual game.

#### 1.8.a Pause Mechanics

The match plugin automatically triggers a pause 30 seconds after any player disconnect unless the affected team cancels it by typing `.nodc` (or `.stopdc`) in chat during the countdown. Teams may also initiate manual pauses using `.tech` commands. Through use of the plugin, all pauses require confirmation from the opposing team to unpause, followed by an automatic countdown before play resumes. Teams are not charged pause time while waiting for the opposing team to confirm an unpause.

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
- Two additional halves of **10 minutes each** (teams switch sides for the second OT half)
- If still tied, continue playing additional 10-minute overtime halves until a winner is decided

> **Penalty:** Failure to complete required overtime rounds is treated as a forfeit by whichever team caused it, scored under §1.13.b. Where **both** teams are responsible, the match is **voided** under §1.13.c and neither team collects — it is not recorded as a loss for both.

> **Note:** In best-of-three matches, overtime applies to each individual map if that map ends in a tie. Each map must produce a winner.

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

A **BYE** is a regular season week in which a team has no match because its division holds an odd
number of teams. A **forfeit** is a match awarded without play.

#### 1.13.a Scoring a BYE

A BYE is worth the **average of the scores the division's other teams posted that week**, on that
week's map. Each match played in the division that week contributes two scores — one per team — and
the BYE team is credited with their mean, both as points scored and as points conceded.

Only a **played** match contributes scores to that average. A forfeited or voided match has no
scoreline, so it feeds nothing — it *receives* the average rather than supplying it. A team is also
never part of its own average. Where a week contains a second BYE or a forfeit, the average is taken
from whatever matches that division actually played.

The average is taken **per week**, because each week is played on one map and maps do not score
alike. It is never taken across the season.

The average is a **fraction and is kept as one**. Standings carry it to four decimal places and
display it trimmed — a whole number shows no decimals. It is never rounded to an integer before the
tiebreakers are applied, because rounding eight scores to whole points can reorder a division.

*Worked example.* Silver has nine teams, so one sits out each week. In week 4, on dod_harrington,
the other eight play four matches finishing 429-243, 312-300, 500-180 and 260-411. The eight scores
average 329.375, so the team on BYE is credited 329.375 points for and 329.375 points against.

Crediting the average both as points scored and as points conceded is deliberate: it means a BYE
moves a team's point differential by exactly zero. A BYE is **not a result** — it adds no win and no loss, and it does not make records
comparable between teams that have played a different number of matches.

#### 1.13.b Scoring a forfeit

A forfeited match is scored the same way — the average of the scores the division's other teams
posted that week — and is credited to the **non-forfeiting team only**. The team that forfeited
receives no points for that match, neither scored nor conceded.

The non-forfeiting team is credited that average **both as points scored and as points conceded**,
exactly as a BYE is under §1.13.a. **A forfeit therefore moves point differential by zero**, the same
as a BYE: a team is not rewarded in the differential tiebreak for an opponent who did not turn up,
any more than it is for sitting out.

A team that turned up to a match its opponent did not play is in the same position as a team on a
BYE: it had no opponent, through no fault of its own. The team that caused that is not owed the
same treatment, and the loss on its record is not the whole of the consequence.

A forfeited match contributes nothing to the average it is scored from. It has no scoreline.

Where both teams forfeit, the match is **voided** instead (§1.13.c) — neither team collects.

#### 1.13.c When each becomes final

- A **BYE** is final as soon as no other match that division played that week is still awaiting a
  result — that is, once every one of them has been **recorded, forfeited, or voided**. It does not
  wait on the rest of the season. Until then it is provisional and moves with each result.
  **A forfeit in that week does not hold the BYE open.** A forfeited match has an outcome the moment
  it is declared; what waits until the end of the regular season is the *forfeit's own credit*
  (§1.13.b), not the week's completeness. A voided match neither holds the week open nor feeds the
  average.
- A **forfeit** is scored **only at the end of the regular season**, once it is settled that no
  makeup match will be played. Until then the non-forfeiting team is credited nothing, so a fixture
  that is eventually played instead never carried a credit.

A match **voided** by admin decision scores nothing for either team, does not contribute to any
average, and does not hold a BYE or the season open.

### 1.14 Standings and Tiebreakers

Standings count **regular season matches only**. Playoff matches never affect the league table. A
match voided by admin decision counts for neither team — not a win, not a loss, and in no total.

Teams are ordered by:

1. **Record** — most wins, then fewest losses.
2. **Head-to-head** — the results between the teams that are level on record (see below).
3. **Point differential** — round points scored minus round points conceded across the whole
   regular season.

#### 1.14.a How head-to-head is applied

- The **tied group** is every team in the division with an identical record. Head-to-head is applied
  to the whole group at once — it is **not** a series of pairwise comparisons. Comparing pairs is
  not transitive: with three or more teams it produces a different answer depending on which pair is
  compared first, and can produce no answer at all.
- The group is ranked on a **mini-table** of the matches those teams played against each other,
  counting the same matches the standings count (regular season, played or forfeited). A forfeit is
  a head-to-head result like any other.
- The mini-table is ranked on **record only** — most mini-table wins, then fewest mini-table losses.
  **Mini-table point differential is deliberately not used**, at any step. See §1.14.c.
- Head-to-head applies **only when every team in the group has played at least one of the others**.
  If any tied team has played none of them, head-to-head is skipped for the entire group and the tie
  is settled on point differential. An unplayed head-to-head is never treated as an 0-0 record.
- Teams still level after the mini-table fall through to point differential. The mini-table is
  applied once; the rule does not recurse into a smaller tie inside the group.

#### 1.14.b Worked example

Two teams finish 5-2. One is +500 on differential, the other +100. The +100 team won the match
between them, so it finishes ahead — head-to-head is applied before differential. The visible
columns cannot show this on their own, which is why the standings page marks such a row and names
the result that placed it.

#### 1.14.b.i Teams still level after all three steps

> **Placement note.** This rule is numbered under §1.14.b (the worked example) but applies to
> §1.14.a and to the tiebreakers generally, not only to the example above. The identifier and heading
> level are left unchanged deliberately: the site builds anchors from the rule number, and both
> translations mirror this structure line for line.

If two or more teams remain exactly level after record, head-to-head and point differential, and the
order decides a playoff seed or any other consequence, **a KTP admin rules on the order and the
ruling is recorded publicly.** No further automatic criterion is applied.

⛔ **The order shown on the standings page is not authoritative in this case.** The site breaks the
remaining tie on an internal identifier purely so the table does not reshuffle between page loads.
That has no sporting meaning. Until an admin has ruled, treat those rows as unordered.

#### 1.14.c Why the mini-table ignores point differential

In a circular three-way tie every team is 1-1 inside the group, so the mini-table separates nobody
and the tie falls through to **overall** point differential. This is settled league precedent: the
Season 4, 5 and 8 Silver three-way ties were all resolved that way. Adding a mini-table differential
step would reverse those results. The step is absent on purpose — it is not an oversight to be
tidied up later.

### 1.15 Language and Translations

The English text of this ruleset is the official and controlling version. Translations into other languages are provided for convenience only.

Where a translation and the English text differ — in wording, in meaning, or through an error or omission in translation — the English text governs. All rulings, penalties, and dispute decisions are made on the basis of the English rules, and no ruling may be appealed on the ground that a translation said something different.

> **Important:** If a translated rule is unclear or appears to conflict with the English, read the English version or ask a KTP admin before acting on it. A misreading of a translation is not a defense to a rule violation.

---

## 2. Teams, Regions, Home/Away, and Ringer Rules

> **Section Summary:** This section covers team composition, scheduling, server selection by region, roster management, and rules for using substitute players (ringers).

### 2.1 Team Composition (International vs NA)

| Team Type | Definition |
|-----------|------------|
| **International** | Majority of players (4+) based outside North America (EU, SA, etc.) |
| **North American** | Majority of North American players |

### 2.2 Scheduling Default Match Times

#### 2.2.a Standard Default Time
Sunday at 9:00 PM Eastern Time (ET — US Eastern, observing daylight saving).

#### 2.2.b International Default Time
When one or both teams have majority EU players east of UTC -2, the default match time is Sunday at 3:00 PM EST.

> Times may adjust for daylight savings time.

### 2.3 Home Team Advantage

#### 2.3.a Standard Matches
The team listed on the schedule as the **HOME** team has the choice of server usage for both halves as well as the choice of which side (Allies or Axis) to join first.

#### 2.3.b Best-of-Three (BO3) Matches
Each map is treated independently. The team that picked a map is considered the "home" team for that map.

### 2.4 Server Selection by Region

#### 2.4.a NA vs NA — Home Team Server Selection

For matches between North American teams (no International team involved), the **HOME** team selects the game server location from the following KTP-approved locations:

| Location | Status |
|----------|--------|
| **Chicago** | Available |
| **Dallas** | Available |
| **Denver** | Available |

The HOME team may propose an alternate KTP-approved server location not listed above, but this is subject to the opposing team captain's approval. If the opposing captain does not approve the alternate location, the HOME team must select from the three standard locations listed above.

> **Important:** Matches may never be played on non-KTP-approved servers regardless of mutual agreement.

> **Trial Policy:** This home team server selection policy is being introduced as a trial to evaluate its impact on competitive balance and match quality. The league will monitor usage and may adjust available locations, revert to neutral server assignment, or modify the selection process based on community feedback and competitive outcomes.

#### 2.4.b International vs International

For matches between International teams (majority EU/SA players per Rule 2.1), the **HOME** team selects the game server location from the following KTP-approved locations:

| Location | Status |
|----------|--------|
| **Atlanta** | Available |
| **New York** | Available |

The HOME team may propose an alternate KTP-approved server location not listed above. The alternate location requires the opposing team captain's approval. If the opposing captain does not approve, the HOME team must select from the standard locations listed above.

> **Important:** Matches may never be played on non-KTP-approved servers regardless of mutual agreement.

#### 2.4.c NA vs EU — Server Selection

For matches between a North American team and a European team (majority EU players east of UTC -2 per Rule 2.1), the **HOME** team selects the game server location from the following KTP-approved locations, with priority given to New York:

| Location | Status |
|----------|--------|
| **New York** | Primary |
| **Atlanta** | Backup only (if New York is unavailable) |

New York must be used whenever it is available. Atlanta may only be selected if no New York servers are available at the time of scheduling or match start. These East Coast locations provide reasonable compromise latency for trans-Atlantic connections.

The HOME team may propose an alternate KTP-approved server location not listed above. The alternate location requires the opposing team captain's approval. If the opposing captain does not approve, the HOME team must select from the standard locations listed above, following the priority order.

> **Important:** Matches may never be played on non-KTP-approved servers regardless of mutual agreement.

#### 2.4.d NA vs SA — Server Selection

For matches between a North American team and a South American team (majority SA players west of UTC -2), the **HOME** team selects the game server location from the following KTP-approved locations:

| Location | Status |
|----------|--------|
| **Atlanta** | Available |
| **New York** | Available |

These locations provide reasonable compromise latency for South American connections.

The HOME team may propose an alternate KTP-approved server location not listed above. The alternate location requires the opposing team captain's approval. If the opposing captain does not approve, the HOME team must select from the standard locations listed above.

> **Important:** Matches may never be played on non-KTP-approved servers regardless of mutual agreement.

#### 2.4.e Side Selection for NA vs EU

When a North American team plays against a European team (majority EU players east of UTC -2 per Rule 2.1), the **NA team always chooses** which side (Allies or Axis) to play on first, **overriding the home team advantage defined in Rule 2.3.a**. This offsets the scheduling advantage EU teams receive from the earlier default match time.

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
| **Exception** | Changes may still be made by admin decision — see Rule 2.7.a |

#### 2.7.a Requesting a Roster Change

Roster changes are requested on the league website (ktpleague.gg) under your account settings, not by support ticket.

| When | Captain | Player asking to leave |
|------|---------|------------------------|
| **Registration open** | Edits the roster directly; admins are notified of what changed | Files a request |
| **Registration closed, before the lock** | Files a request; staff review it | Files a request |
| **After the lock** | The captain's form closes — ask an admin | Files a request |

A player may ask to leave a roster **at any time, before or after the lock**, from their own account settings. It is a request in every case: the player stays on the roster until an admin acts on it, and a request that would leave a team with no captain is not applied until another captain is in place.

Every request and every decision stays on the record.

### 2.7.1 Mid-Season Roster Window

One roster addition window will occur mid-season, announced at least one week in advance.

| Division | Requirements |
|----------|--------------|
| **Highest division** | Additions approved if roster slot available (up to 10) |
| **Other divisions** | Admin approval required (preserves competitive integrity) |

### 2.8 No Bypassing Rules by Agreement

No agreement between team captains can override official rules or active suspensions. Such agreements are invalid and constitute a rule violation.

### 2.9 Ringers

A **ringer** is a player not on your official roster, temporarily used to fill in. Using ringers requires approval from the opposing team captain before the match begins.

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
- Requesting player POV demos at random, and reviewing KTPAntiCheat records
- Conducting spot-checks at any time

**Failure to provide requested materials can result in:**
- Forfeit of the game/match in question
- Suspension of the player

### 3.3 Zero Tolerance for Cheating

Any player found cheating will be suspended (or banned) from KTP, and any influenced match results are subject to being overturned or forfeited.

#### 3.3.a Scope of a Ban

A ban may be applied to a player, and where there is evidence of ban evasion, to the hardware used to evade it. A ban applies across all KTP-operated servers.

Where hardware is shared — a venue machine, a household, a shared computer — a hardware ban must not be applied without evidence connecting the specific player to the evasion. A person affected by a hardware ban who was not party to the evasion may contest it under Rule 3.9.a and, on a successful contest, must be restored.

### 3.4 Definition of Cheating

Cheating includes (but is not limited to):
- Wallhacks (seeing enemies through walls)
- Aimbots (automatic target acquisition)
- Illegally modifying game files
- Any external program giving unfair advantage
- Input multiplication — "Snap Tap" / SOCD null-cancel, "Rapid Fire" / Turbo (auto-repeat) modes, or any bind, script, or device feature that produces more than one input from a single physical actuation, accelerates firing, or bypasses stamina (see Rule 4.6)

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
- Any other requested materials

#### 3.8.b Consequences and Investigation
- Failure to provide files may result in suspension and/or forfeit
- Admins may review demos and KTPAntiCheat records from prior/subsequent matches
- Player may be subject to additional scrutiny in future games

### 3.9 KTPAntiCheat Records

KTPAntiCheat records are produced automatically by the client and held by the league; players are not required to submit them. In the event of a dispute or random check, players must provide their POV demos from the match in question.

Every session is scored on KTP's servers from the submitted evidence. Sessions may be re-scored when detection methods change, including sessions from earlier in the season; a re-score can change a previous outcome in either direction.

**Retention:** Session uploads are retained indefinitely for integrity review, so a finding can always be re-examined from the original evidence. Match telemetry is kept for **30 days**; session records and outcomes are kept for the season. A finding resting on telemetry can only be re-examined while that telemetry is still retained.

#### 3.9.a Contesting a KTPAntiCheat Finding

A player may contest a KTPAntiCheat finding, including a coverage finding, by notifying an admin within **14 days** of being informed of it. Findings are re-examined from the original evidence where it is still retained (see Rule 3.9).

A player may review their own uploaded sessions at any time through the KTP league website (ktpleague.gg), including screenshots, configuration files, and device inventory, and may download their own copy. Individual artifacts may be withheld from that copy where releasing them would disclose how KTPAntiCheat detects cheating. Where anything is withheld, the player is told that material was withheld, and an admin who did not make the original finding will explain the reason on request. Withheld material is still examined in full when a contest under this rule is reviewed.

An admin who did not make the original finding reviews the contest. The outcome is one of: finding upheld, finding withdrawn, or finding varied. The player is told which, and why.

Automated output is never by itself a final outcome — a person reviews any finding before a penalty is applied.

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
All players must comply with file-integrity, CVAR, and anti-cheat checks. Players must not interfere with or bypass these systems.

#### 4.1.e KTPAntiCheat

Every player must run the current version of **KTPAntiCheat** for the duration of each match they play. A match is covered when the player's KTPAntiCheat session is running before the match begins and remains running until it ends.

Players must not alter, tamper with, or interfere with the client, its session records, or its uploads, and must not submit or cause to be submitted any record that is not their own.

A player whose match is not covered is subject to the same handling as any other Section 4 violation. Repeated failure to cover matches may be treated as evasion.

Coverage is determined from KTPAntiCheat's own records. A player may contest a coverage finding under Rule 3.9.a.

Technical failure — a crash, a disconnect, or a KTPAntiCheat outage — is not a violation, provided the player reports it to an admin before the next match. Admins may accept an uncovered match at their discretion where the cause is evident.

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

**Overtime Demos:**
- Record separate POV demos for each overtime half following the same procedure as regulation halves

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

Video recordings or Twitch VODs are **NOT** substitutes for demos or KTPAntiCheat. You must still record in-game demos and run KTPAntiCheat even if streaming.

### 4.3 File Retention

Retain all match files **for the duration of the season**:
- POV demos for each half
- All required screenshots

> **Note:** There is no anti-cheat file for players to keep — KTPAntiCheat records are produced and retained by the league (see Rule 3.9).

### 4.4 Player Boosting

Boosting is **allowed only if** the destination area is reachable by a single player without a boost. Boosting to access glitched or unintended areas is illegal.

### 4.5 Voice Commands and Signals

Voice commands should be used for team communication only. Excessive use to taunt, annoy, or "neg" opponents is not allowed.

### 4.6 Input Bindings & Device Features

**Principle:** one physical actuation equals one in-game input. A device may change *when* a single key registers (its actuation/reset point); it may not multiply one physical action into several inputs, auto-repeat an input, or resolve an input for you.

**Permitted:** Rapid Trigger and adjustable actuation points — these change only *where* in a key's travel a single press registers. One press is still one input, so the player remains the rate limiter. ("Rapid Trigger" is the industry-standard term — used by Wooting, Razer, SteelSeries, Corsair, etc. — for a dynamic/continuous reset point on Hall-effect/analog keyboards and analog mouse switches. Rapid Trigger is permitted on both keyboards and mice. It is **not** the same as the prohibited "Rapid Fire" / "Turbo" auto-repeat below.)

**Prohibited:**
- **A key bound to `+attack` must issue `+attack` and nothing else.** Binding or aliasing `+attack` together with any additional command — directly, through an alias, or through an exec'd config — is prohibited.
- Binding `+attack` or `+duck` to the mousewheel (accelerates firing / bypasses stamina restrictions)
- "Rapid Fire," "Turbo," or multi-tap keyboard/mouse modes that emit repeated inputs from a single press
- "Snap Tap" / SOCD handling / null-cancel binds that auto-release one of two opposing movement keys (**SOCD** is the generic term; "Snap Tap" is Razer's brand name)

**Notes:**
- Rebinding is unaffected. `+attack` may be bound to any key, and other commands may have their own keys. Only combining them on the fire key is prohibited.
- Stock commands are not suspicious in themselves. `+lookup`, `+lookdown`, `+left`, `+right`, and `centerview` ship as Half-Life defaults and appear in most configs.
- Wheel `+jump` remains permitted (bunny-hopping).

### 4.7 No Automated Scripts

Players may not use scripts to automate:
- Player attacking
- Player movement
- Rapid-fire
  ⚠️ **“Rapid-fire” here means auto-repeat — one press producing repeated inputs.** It does
  **not** mean **Rapid Trigger**, the analogue actuation feature of Hall-effect keyboards, which
  §4.6 permits explicitly. Rapid Trigger shortens *when* a key registers; it never multiplies a
  press into more than one input. See §4.6.
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
Captains must configure their client settings via a customized client scheme so end-of-half scoreboards are easy to read in screenshots (high-contrast, clear font).

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

#### 5.4.a Regulation Scheduling Deadline

All regular-season matches must be completed by the **midnight that ends the
final regular-season Sunday** (00:00 Eastern on the following day). A match
still unplayed or without a confirmed time at that deadline is referred to the
admin team together with its full scheduling record — every proposed time,
every response, and every reminder the league attempted to deliver.

- **No automatic forfeits.** The deadline flags a match for admin review; it
  never decides a result. Admins rule under §1.13 and §3.1, weighing who
  proposed times, who went silent, and — as a distinct fact — whether a team's
  captains could be reached at all.
- A team whose captains were unreachable by every channel the league has is a
  different case from a team that was reached and did not respond. The
  scheduling record shows which is which.

### 5.5 Roster and Ringer Checks

Captains must verify player eligibility before match starts:
- Check opposing players match roster names and SteamIDs
- Verify any ringers have been approved

> **Important:** Once a match is completed, you cannot dispute based on an ineligible player if you had the opportunity to catch it beforehand.

### 5.6 Reporting Scores

Results are reported on the match page at the league website (ktpleague.gg) within **1 hour of match completion**. The obligation to report within the hour rests on the **winning team captain**; either captain may enter the result, and a losing captain who enters it first discharges it.

Reporting is two-sided. One captain enters the result, the **opposing** captain confirms it, and the result is recorded — and the standings move — only on that confirmation. A captain cannot confirm their own team's report.

**Reporting captain:**

- [ ] Enter each team's final point total for the match
- [ ] Check the winner the site names back to you before sending — a reversed score is the common mistake, and the other captain is the only person who can catch it

**Opposing captain:**

- [ ] Confirm the result, or dispute it with a reason, **within 24 hours** of being asked to

A captain who disagrees with an entered result disputes it instead of confirming it. A disputed result is never recorded; it goes to the admin team with both captains' accounts of it.

Screenshots are **not** uploaded with the report. Captains still take them (Rule 5.1.a, Rule 5.1.b), retain them for the season (Rule 4.3), and must produce them on request — a disputed result is settled from them.

> **Note:** Playoff series results and forfeits are recorded by admins, not through captain reporting. Send playoff scores to an admin when the series is done.

> **If the site cannot take the report:** post it in the designated KTP Discord scores channel within the same hour and tell an admin. That is a fallback for an outage, not a second reporting route.

### 5.7 Playoff Map Vetoes

Vetoes are run for playoff matches only. They take place in the veto room on the match page at the league website (ktpleague.gg): both captains act in turn — bans, picks, and starting sides — against the published playoff map pool. The site decides whose turn it is and refuses an illegal move, so there is nothing to submit anywhere else.

Captains must complete the veto **at least 72 hours before the round's default match start time** (Rule 2.2). The deadline is measured from the default time, not from any later time the two captains agree between themselves.

> **Penalty:** If the veto is not complete at that deadline, admins perform the outstanding steps on the late team's behalf. A step taken that way is marked as a staff action in the match's veto log, which is public.

Series length is set by admins on the match. Most playoff matches are best-of-three; the veto runs the same way for a best-of-one or a best-of-five.

#### 5.7.a When a Round Resolves Late

A playoff match has no teams until the round before it is decided. Where both teams become known **less than 72 hours before** the round's default start, the 72-hour deadline cannot have been met and is not counted against either team. The veto is instead due **as soon as both captains have had a reasonable chance to run it**, and admins may perform outstanding steps once the match is otherwise due to be played.

### 5.8 Captain Accountability

Captains are responsible for ensuring team members understand and follow all rules. Repeated team violations may result in captain suspension for negligence.

---

**End of Rules Document**

*Last Updated: August 2026*

*Questions? Contact KTP Admins via Discord or the league website.*
