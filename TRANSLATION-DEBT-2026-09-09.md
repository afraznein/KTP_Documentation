# Translation debt — English ruleset, 2026-08-31 → 2026-09-09

**For:** chi (KTP Admin), reviewer and translator of `KTP Ruleset.es.md` and `KTP Ruleset.pt.md`.

This is the whole of the outstanding translation work in one place. It replaces six separate
tracking issues (#13, #15, #18, #19, #22, #24), which were one-per-English-commit and therefore a
count of commits rather than a worklist. Nothing here needs the issue tracker to read.

**Nothing in this document is a translation.** The Spanish and Portuguese files are deliberately
left as they are, apart from chi's own corrections from PR #14, which are carried forward here so
they are not lost and not re-done. The translating is his.

---

## What changed, and where it came from

The English ruleset moved **18 commits, +108/−26** between `3f5d4080` (the commit that added the
two translations, 2026-08-31) and `origin/main` at `072ac73` (2026-09-09). The es/pt files have not
been touched in that window.

The delta is three things:

1. **The thirteen season-critical rulings** the admins voted through on 2026-09-08, written into
   the rule text (`d34d2c8`, `a1a72d5`). These are the load-bearing content — they resolve
   ambiguities that bite in week 1.
2. **The §2.4 server-choice batch** (`a665c26`, `636b184`, `98b23e9`, `a30370a`) — who picks the
   server in an NA vs EU match, and whether the choice moves per map in a BO3.
3. **Clerical and single-rule changes** — the §2.2 timezone correction, §2.7/§2.7.a roster drops,
   §2.11's forfeit threshold, §1.14's standings step 1.

Reproduce the delta with:

```
git diff 3f5d4080..origin/main -- "KTP Ruleset.md"
```

---

## The last step: `source-sha256`

Each translation carries a `ktp-translation` header recording which revision of the English file it
was made from. ktpleague.gg re-checks it on every render and warns readers when it no longer
matches.

**Both files still carry the old hash, deliberately.** This PR does not refresh it, because the
translations are not yet updated — turning the reader-facing staleness warning off before the text
is current would be worse than leaving it on.

**When the translation is finished, set both headers to:**

```
source-sha256: fa86a3233860876e9b3aedba881c5e5623f782659f1bc32effe54790063cfa2d
```

That value is derived, not guessed. The recipe is sha256 of `KTP Ruleset.md` **with trailing
newlines stripped** — not a plain `sha256sum` of the file, which gives a different answer. It was
recovered by reproducing the currently-recorded value:

```
# reproduces the hash presently in both headers (5f160e48…), confirming the recipe
printf '%s' "$(git show 3f5d4080:'KTP Ruleset.md')" | sha256sum

# the value to write once the translation is current
printf '%s' "$(git show origin/main:'KTP Ruleset.md')" | sha256sum
```

If the English file moves again before the translation lands, recompute rather than copying the
value above.

---

## Status legend

| Mark | Meaning |
|---|---|
| **MISSING** | The English paragraph is new. There is no corresponding text in es/pt at all. |
| **STALE** | A corresponding paragraph exists in es/pt but now says something the English no longer says. It must be replaced, not appended to. |
| **DONE (chi)** | Already translated in PR #14 and carried forward in this branch. No action. |
| **SUPERSEDED (chi)** | chi translated this in #14, and an English change since then has moved the rule out from under it. Needs a small edit, not a re-translation. |

Section numbering is identical in all three files — the same section numbers, in the same order — so
every item below can be found in es/pt by its § number. Keep it that way: the site builds anchors
from the rule number, and a renumbered translation breaks every cross-reference into it.

---

# The worklist

Ordered by section number. 26 items.

---

## §1.10 — Tie Games and Overtime · penalty for not completing OT

**Status:** STALE in **es** (line ~141) and **pt** (line ~141).
**Was:** failure to complete overtime records a loss for both teams.
**Now:** it is a forfeit charged to whoever caused it; if both are responsible the match is voided
and neither collects.

> **Penalty:** Failure to complete required overtime rounds is treated as a forfeit by whichever team caused it, scored under §1.13.b. Where **both** teams are responsible, the match is **voided** under §1.13.c and neither team collects — it is not recorded as a loss for both.

⚠️ The existing es/pt sentence must be **replaced**. Appending the new rule after it leaves two
contradictory sentences.

---

## §1.13.a — Scoring a BYE · what feeds the average

**Status:** **DONE (chi)** — es and pt. No action.

chi added both new paragraphs in #14, before the English commit that introduced them landed. They
are already in the files on this branch. Recorded here only so it is clear they are not owed.

> Only a **played** match contributes scores to that average. A forfeited or voided match has no scoreline, so it feeds nothing — it *receives* the average rather than supplying it. A team is also never part of its own average. Where a week contains a second BYE or a forfeit, the average is taken from whatever matches that division actually played.

> The average is a **fraction and is kept as one**. Standings carry it to four decimal places and display it trimmed — a whole number shows no decimals. It is never rounded to an integer before the tiebreakers are applied, because rounding eight scores to whole points can reorder a division.

---

## §1.13.b — Scoring a forfeit · differential moves by zero

**Status:** MISSING in es and pt. New paragraph, inserted after "*…receives no points for that
match, neither scored nor conceded.*"

> The non-forfeiting team is credited that average **both as points scored and as points conceded**, exactly as a BYE is under §1.13.a. **A forfeit therefore moves point differential by zero**, the same as a BYE: a team is not rewarded in the differential tiebreak for an opponent who did not turn up, any more than it is for sitting out.

---

## §1.13.c — When each becomes final · the BYE bullet

**Status:** STALE in es and pt. The first bullet of §1.13.c is replaced and expanded.

**Was:** a BYE is final once every other match that division played that week has been *scored*.
**Now:** final once none of them is still *awaiting a result* — recorded, forfeited or voided — and
a forfeit in that week explicitly does not hold the BYE open.

> - A **BYE** is final as soon as no other match that division played that week is still awaiting a result — that is, once every one of them has been **recorded, forfeited, or voided**. It does not wait on the rest of the season. Until then it is provisional and moves with each result.
>   **A forfeit in that week does not hold the BYE open.** A forfeited match has an outcome the moment it is declared; what waits until the end of the regular season is the *forfeit's own credit* (§1.13.b), not the week's completeness. A voided match neither holds the week open nor feeds the average.

⚠️ Terminology: "**awaiting a result**" vs "**scored**" is the whole point of the change. Do not
collapse them into one word in translation.

---

## §1.14 — Standings and Tiebreakers · step 1

**Status:** STALE in es and pt. List item 1 is replaced.

**Was:** "Record — most wins, then fewest losses."
**Now:** wins only; losses are informational.

> 1. **Record** — most wins. Losses are shown for information only and never order the table: a BYE is not a result (§1.13.a), so within a division every team's wins and losses add up to the same total, and a further step on losses could never separate teams that wins had not.

*(This is season-critical ruling #1. See the ambiguity flagged at the end — the stated justification
does not hold for a voided match, and you may want that wording revisited in English before it is
translated.)*

---

## §1.14.a — How head-to-head is applied · bullets 1 and 2

**Status:** STALE in es and pt. Two bullets replaced.

**Bullet 1 was:** the tied group is every team with an *identical record*.
**Bullet 1 now:** every team level after step 1 — *the same number of wins*.

> - The **tied group** is every team in the division that is level after step 1 of §1.14 — the same number of wins. Head-to-head is applied to the whole group at once — it is **not** a series of pairwise comparisons. Comparing pairs is not transitive: with three or more teams it produces a different answer depending on which pair is compared first, and can produce no answer at all.

**Bullet 2 was:** "…A forfeit is a head-to-head result like any other."
**Bullet 2 now** adds *why* — head-to-head reads win/loss only, never the scoreline:

> - The group is ranked on a **mini-table** of the matches those teams played against each other, counting the same matches the standings count (regular season, played or forfeited). Head-to-head reads **the win and the loss only, never the scoreline**. That is why a forfeit is a head-to-head result like any other: it has a winner from the moment it is declared, even though it carries no score until the end of the regular season (§1.13.c).

*(Season-critical ruling #2.)*

---

## §1.14.b.i — Teams still level · placement note

**Status:** **DONE (chi)** — es and pt. No action.

chi added this note in #14. It is already on this branch in both files.

> **Placement note.** This rule is numbered under §1.14.b (the worked example) but applies to §1.14.a and to the tiebreakers generally, not only to the example above. The identifier and heading level are left unchanged deliberately: the site builds anchors from the rule number, and both translations mirror this structure line for line.

---

## §1.14.b.i — Teams still level · which consequences trigger a ruling

**Status:** STALE in es and pt. The main paragraph and the ⛔ paragraph are both replaced.

**Was:** "…decides a playoff seed or any other consequence".
**Now:** an exhaustive list of three, and an explicit "otherwise, no ruling is made".

> If two or more teams remain exactly level after record, head-to-head and point differential, and the order decides **a playoff berth, a playoff seed, or a relegation or promotion position**, **a KTP admin rules on the order and the ruling is recorded publicly.** No further automatic criterion is applied. Where the order decides none of those three things, the teams stay tied and no ruling is made.

> ⛔ **The order shown on the standings page is not authoritative in this case.** The site breaks the remaining tie on an internal identifier purely so the table does not reshuffle between page loads. That has no sporting meaning. Treat those rows as unordered until an admin has ruled — and for good, where no ruling is triggered.

⚠️ "**and for good**" is idiomatic English for *permanently*. It is not a typo for "and for the
good of". Translate the sense: the rows stay unordered permanently where no ruling is triggered.

*(Season-critical ruling #3.)*

---

## §2.1 — Team Composition · the definition table

**Status:** STALE in es and pt. Both table rows are replaced.

**Was:**

| Team Type | Definition |
|-----------|------------|
| **International** | Majority of players (4+) based outside North America (EU, SA, etc.) |
| **North American** | Majority of North American players |

**Now:**

| Team Type | Definition |
|-----------|------------|
| **International** | **4 or more** rostered players based outside North America (EU, SA, etc.) |
| **North American** | Any team that is not International |

⚠️ The word **majority** is deliberately gone from the definition. It is now a **count** (four or
more), and the residual category is defined by exclusion. Both translations currently render it as
a majority — es line ~294, pt line ~293. Carrying "majority" through would restate the rule the
change was made to remove.

---

## §2.1 — Team Composition · two new paragraphs

**Status:** MISSING in es and pt. Both are new, immediately after the table.

> Four is a majority of the **six** a team fields (§2.10), which is where the threshold comes from — not a majority of the ten-player maximum roster (§2.7).

> **Measured against the roster at lock, not the lineup on the night.** A team's type has to be known before the schedule is generated, because the default match time is stamped once (§2.2). A team with four or more international players is therefore International even if it fields fewer on a given Sunday — the classification errs toward granting the accommodation, not withholding it.

*(This is item 14 of the ruling proposals, the one entangled with the S10 kickoff ruling. It rode in
with the thirteen.)*

---

## §2.2.a — Standard Default Time · EST → ET

**Status:** STALE in es and pt (es line ~299 area, pt line ~299 area).

**Was:** Sunday at 9:00 PM Eastern Time (EST).
**Now:**

> Sunday at 9:00 PM Eastern Time (ET — US Eastern, observing daylight saving).

---

## §2.2.b — International Default Time · EST → ET

**Status:** STALE in es (line 302) and pt (line 302).

> When one or both teams have majority EU players east of UTC -2, the default match time is Sunday at 3:00 PM Eastern Time (ET — US Eastern, observing daylight saving).

🔴 **This one needs chi's decision, not just his translation.** In PR #14 he wrote, explicitly:

> *"I didn't change the timezones (EST to EDT or ET) because all SA players think EST is the sole
> one so it's simpler to keep it that way."*

That was a reasonable editorial call at the time. It is now in direct conflict with an approved
English rule change (`e1b58cf`, *"§2.2.b says EST for a start time that is mostly EDT"*), whose
whole purpose was to stop the ruleset naming a timezone the match is usually not played in.

We have not resolved this. §1.15 makes the English controlling, so the English now says ET — but
whether the Spanish and Portuguese should follow it literally, or keep "EST" with a parenthetical
gloss for a readership that reads EST as "US east coast time" generically, is a call for chi and
the admins. It affects §2.2.a and §2.2.b in both files.

---

## §2.3.b — Best-of-Three · home status and the server per map

**Status:** MISSING in es and pt. New paragraph after "*…is considered the 'home' team for that
map.*"

> Home status for a map carries the full §2.3.a advantage **for that map**: the server it is played on and which side to join first. **The server moves with the map** — the team that picked a map selects the server for it, so the server may differ from one map to the next within a series. §2.4 still governs which locations are eligible for each of those choices. ⚠️ **Exception:** in an NA vs EU match the server does not follow the map at all — §2.4.c gives every map's server to the NA team, and §2.4.e gives it every side choice.

*(Season-critical ruling #9. See the ambiguity flagged at the end — this paragraph and §2.4.c's new
per-map paragraph pull in opposite directions.)*

---

## §2.4.c — NA vs EU · who selects (intro paragraph)

**Status:** STALE in es (line ~349) and pt (line ~349).

**Was:** the **HOME** team selects.
**Now:** the **NA team** selects, overriding both §2.3.a and §2.3.b.

> For matches between a North American team and a European team (majority EU players east of UTC -2 per Rule 2.1), the **NA team** selects the game server location from the following KTP-approved locations, with priority given to New York. **This overrides the home team's server choice under §2.3.a, and the per-map server choice under §2.3.b** — the NA team selects for every map of the series, whichever team picked it. Together with §2.4.e's side choice it offsets the earlier default kickoff §2.2.b gives the European team:

*(Season-critical ruling #11.)*

---

## §2.4.c — NA vs EU · "at the time of scheduling **or** match start"

**Status:** MISSING in es and pt. New paragraph after the New-York-priority paragraph.

> "At the time of scheduling or match start" is **inclusive**: New York being unavailable at either moment is enough for Atlanta to be selected. Where the two moments disagree, **match start governs**, because that is when the match needs a server — a New York server that is available at match start is used even if none was when the match was scheduled, and one that has become unavailable by match start does not hold the match to New York. In a best-of-three the server is chosen per map (§2.3.b), so this test is applied at **each map's start**, not once for the series — a series may therefore run in different locations from map to map.

*(Season-critical ruling #10.)*

---

## §2.4.c — NA vs EU · the alternate-location paragraph

**Status:** **SUPERSEDED (chi)** in **pt**. STALE in **es**.

**Was:** "The HOME team may propose… the HOME team must select…"
**Now:**

> The NA team may propose an alternate KTP-approved server location not listed above. The alternate location requires the opposing team captain's approval. If the opposing captain does not approve, the NA team must select from the standard locations listed above, following the priority order.

🔴 **This is the one place where chi's #14 work collides with the English delta.** In #14 he
rewrote exactly this paragraph in the Portuguese file to make the priority order strict:

> *"…o time HOME deverá selecionar uma das localizações padrão listadas acima, respeitando
> estritamente a ordem de prioridade (New York como primária obrigatória)."*

That clarification is good and should survive. What has moved underneath it is only the **actor**:
`98b23e9` changed HOME → NA throughout §2.4.c. So the pt sentence needs `o time HOME` → `o time NA`
in both halves, keeping his added "(New York como primária obrigatória)". The es sentence needs the
same actor change and would benefit from the same clarification, which it does not yet have.

**This is an edit, not a re-translation. Do not revert his paragraph and start over.**

---

## §2.4.d — NA vs SA · why HOME still selects here

**Status:** MISSING in es and pt. New paragraph after "*These locations provide reasonable
compromise latency for South American connections.*"

> The **HOME** team selects here, unlike §2.4.c. That is deliberate: the NA team's server and side choice in §2.4.c/§2.4.e exists to offset the **earlier kickoff time**, and a South American team does not receive one — §2.2.b's 3:00 PM default is for majority-EU teams east of UTC -2 only. A South American team is International under §2.1 and still plays at the standard time, so there is nothing to offset.

---

## §2.4.e — Side Selection for NA vs EU · both side and server sit with NA

**Status:** MISSING in es and pt. New paragraph at the end of the section.

> The NA team also selects the server under §2.4.c, so in an NA vs EU match **both the side and the server sit with the NA team**, on every map, regardless of which team is HOME or picked the map. A European team gains neither by being HOME nor by picking a map; what it holds instead is the earlier default kickoff time under §2.2.b.

---

## §2.7 — Rosters and Roster Locks · the "After lock" table row

**Status:** STALE in es and pt.

**Was:** | **After lock** | No changes to roster, team name, player handles, or SteamIDs |
**Now:**

| Rule | Details |
|------|---------|
| **After lock** | No changes to team name, player handles, or SteamIDs. No roster **additions** except through the window in Rule 2.7.1. A **drop** is always allowed — see Rule 2.7.a |

---

## §2.7.a — Requesting a Roster Change · the "After the lock" table row

**Status:** STALE in es and pt.

**Was:** | **After the lock** | The captain's form closes — ask an admin | Files a request |
**Now:**

| When | Captain | Player (leaving a team) |
|------|---------|------------------------|
| **After the lock** | The captain's form closes for **additions** — ask an admin. A **drop** applies at once | Leaves at once |

---

## §2.7.a — Requesting a Roster Change · drops, transfers, swaps and holds

**Status:** STALE **and** MISSING in es and pt. One existing paragraph is replaced by eight.

**The paragraph to delete** (present in both files) is the one that says a player may *ask* to leave
at any time and stays on the roster until an admin acts. That is no longer the rule — a drop now
applies immediately and is not a request.

**The replacement, in full:**

> A player may leave a roster **at any time, before or after the lock**, from their own account settings, and a captain may drop a player at any time. **A drop applies immediately.** It is not a request and needs no approval: removing a player adds nobody and can create no competitive advantage, so the roster lock has nothing to protect against it.

> A **transfer out** lowers the origin team's roster exactly as a drop does, and is treated as one here. Two departures are **held** rather than applied, for the same reason — each would leave the team unable to play:
>
> - one that would leave a team with **no captain** is not applied until another captain is in place;
> - one that would leave a team with **fewer than four rostered players** is not applied until the team has four again, because Rule 2.10 requires four rostered players in every match.
>
> The floor reads the roster a player **leaves**, never the one they join, and it counts the **roster** — not the six fielded in a match.

> **A swap is judged on its end state.** Two teams exchanging players each finish with the roster size they started with, so a swap does not breach the floor even though either move, taken alone, would appear to.

> **A swap moves players, not captaincy.** Its end state is who is on each roster; it never decides who leads one. A player arriving in a swap joins as a player or co-captain, and a team whose only captain is one of the two halves does not swap until another captain is in place — the same hold that governs any other departure. Captaincy changes on its own, afterwards, through the roster form.

> ⛔ **These holds bind captains and players. They do not bind admins.** An admin may move a player at any time, including during a lock — that is what makes a hold safe rather than a trap, and a team stuck behind one should ask an admin.

> ⚠️ **While rosters are locked, a player who leaves cannot join another team for the rest of the season.** Additions are governed by Rule 2.7.1's window, and outside that window there is none — an admin may still place them, but nobody should count on it. A player leaving a team mid-season should be told this before they act.

> An **addition** remains a request in every case.

⚠️ Vocabulary to settle once and use consistently across both files: **drop**, **transfer out**,
**swap**, **hold**, **the floor**. "Hold" here means the departure is *suspended, not refused* — it
applies later, automatically, once the blocking condition clears. A word that reads as "denied"
would change the rule.

---

## §2.7.1 — Mid-Season Roster Window · additions only

**Status:** STALE in es and pt. One sentence extended.

> One roster addition window will occur mid-season, announced at least one week in advance. It governs **additions only** — drops are always allowed and are never gated by it (Rule 2.7.a).

---

## §2.11 — Team Forfeits and Removal · the whole section

**Status:** STALE in es and pt. The single existing sentence is replaced by four paragraphs and a
note.

**Was:** teams that repeatedly forfeit may be removed; more than one forfeit may result in removal
at admin discretion.

**Now:**

> A team that forfeits **twice in a season** may be removed from the league at admin discretion. That is the only threshold.

> Only a forfeit **charged to** a team counts toward it. A forfeit win (§5.3) never counts against the team that turned up — that team is in the same position as a team on a BYE (§1.13.b), and is not charged for an opponent who did not appear.

> A forfeit is **charged when it is scored** under §1.13.c — at the end of the regular season, once it is settled that no make-up match will be played. **A fixture recovered by a make-up is never charged**, so a team that was declared a no-show under §5.3 and then played the match does not count it toward this threshold.

> Where a match is **voided** because both teams forfeited (§1.13.c), the forfeit is charged to **each** team.

⚠️ "**charged to**" is the key phrase and it is doing real work: a forfeit *win* and a forfeit
*charge* are opposite sides of the same match. Whatever verb you pick, the translation must let a
reader tell which team the forfeit is counted against.

*(Season-critical ruling #4.)*

---

## §4.7 — No Automated Scripts · rapid-fire vs Rapid Trigger

**Status:** MISSING in es and pt. New warning nested under the existing "Rapid-fire" bullet in the
prohibited-scripts list.

> - Rapid-fire
>   ⚠️ **"Rapid-fire" here means auto-repeat — one press producing repeated inputs.** It does **not** mean **Rapid Trigger**, the analogue actuation feature of Hall-effect keyboards, which §4.6 permits explicitly. Rapid Trigger shortens *when* a key registers; it never multiplies a press into more than one input. See §4.6.

⚠️ **"Rapid Trigger" is a hardware product term and should not be translated.** The whole point of
the paragraph is that two similar-sounding names mean different things; translating one of them
destroys the distinction. Check how §4.6 already renders it in each file and match that exactly.

---

## §5.3 — Match Punctuality and Forfeit Wins · three new paragraphs

**Status:** MISSING in es and pt. All three are new, after the +5/+10/+15 table.

> The clock runs from the match's **actual scheduled start time** — the time on the match page, which is the time the captains agreed to where the match was rescheduled. It does not run from the §2.2 default. A rescheduled match that both captains agreed to is the real appointment.

> **A no-show at +15 does not normally end the fixture.** KTP prefers a **make-up match**, and admins arrange one wherever both teams can still play. The +15 mark is what entitles an admin to call the no-show and start that conversation — it is not a result. A forfeit win is generally awarded only at the **end of the regular season**, for a fixture no make-up ever recovered.

> §1.13.c already sets this out from the scoring side: a forfeit is scored *"only at the end of the regular season, once it is settled that no makeup match will be played."* A forfeit **declared** and a forfeit **credited** are different moments, and neither is automatic — both are admin decisions.

⚠️ The middle paragraph quotes §1.13.c. Quote your own §1.13.c translation there, not a fresh
rendering of the English, or the two passages will differ inside the same document.

*(Season-critical ruling #5.)*

---

## §5.6 — Reporting Scores · the 1-hour duty is conduct, not a condition

**Status:** MISSING in es and pt. New paragraph after "*A captain who disagrees with an entered
result disputes it instead of confirming it…*"

> The 1-hour duty is a **conduct** matter for the winning captain, not a condition of the result. A result the opposing captain confirms inside their 24 hours **stands whenever it was entered**; a late report is a matter for the captain, and never voids the result. If **neither** captain has entered a result 24 hours after the match's scheduled start (§5.3), the fixture goes to the admin team for adjudication. Nothing is awarded automatically.

*(Season-critical ruling #6.)*

---

## §5.6 — Reporting Scores · the playoff note

**Status:** STALE in es and pt. The existing note is extended.

> **Note:** Playoff series results and forfeits are recorded by admins, not through captain reporting. Send playoff scores to an admin when the series is done. In playoffs the duty to record the result is the **admin's**, and no 1-hour clock runs on a captain while an admin is present. Captains report **only if no admin is present** when the series ends — and then the 1-hour clock applies.

*(Season-critical ruling #8.)*

---

## §5.6 — Reporting Scores · the site-outage note

**Status:** STALE in es and pt. The existing note is extended.

> **If the site cannot take the report:** post it in the designated KTP Discord scores channel within the same hour and tell an admin. That is a fallback for an outage, not a second reporting route. A result posted there **still needs the opposing captain's confirmation**, within the same 24 hours, before it is recorded — Discord is a channel for reporting, not a second authority. The one exception is an admin entering the result directly, which supersedes captain reporting.

*(Season-critical ruling #7.)*

---

## §5.7 — Playoff Map Vetoes · the 72-hour anchor

**Status:** MISSING in es and pt. New paragraph after the 72-hour deadline paragraph.

> A playoff round is a scheduled week with a date, exactly as a regular-season week is. A round's default date is **its week's Sunday**, and the 72 hours run back from the §2.2 default time on that date. ⚠️ **Playoff rounds are not always consecutive Sundays** — a bracket can hold a bye week. Season 10's rounds fall on 15 November, 22 November and 6 December, with 29 November off — so the anchor is the round's own published date, never "the following Sunday".

⚠️ The three dates are Season 10 specifics inside a rule text. Keep them as dates; render them in
each language's normal date format rather than transliterating the English one.

*(Season-critical ruling #12.)*

---

## §5.7.a — When a Round Resolves Late · what "a reasonable chance" means

**Status:** MISSING in es and pt. New paragraph at the end of the section.

> Both captains have had **a reasonable chance** once the full 72-hour window of §5.7 has elapsed with the fixture reachable by both of them — both teams known, and the veto room open to both captains — measured forward from the moment it became reachable. A match is **otherwise due to be played** when it is scheduled within its own playoff week.

⚠️ Both **"a reasonable chance to run it"** and **"otherwise due to be played"** are quoted terms
lifted from the paragraph above them in §5.7.a. Use whatever wording your existing §5.7.a
translation already uses for those two phrases, so the definition visibly defines the term it is
defining.

*(Season-critical ruling #13.)*

---

# The thirteen season-critical rulings — where each one landed

The admins voted these through on 2026-09-08. They are the load-bearing content of this delta: each
one closes an ambiguity that surfaces in the first weeks of a season, so a translation that carries
the old text keeps a Spanish- or Portuguese-reading captain on a rule the league has stopped
applying.

| # | Ruling | Section(s) | Item above |
|---|---|---|---|
| 1 | "most wins, then fewest losses" cannot separate anyone | §1.14 | §1.14 step 1 |
| 2 | what "identical record" means for the tied group | §1.14.a | §1.14.a bullets |
| 3 | "or any other consequence", and who decides one exists | §1.14.b.i | §1.14.b.i consequences |
| 4 | is "repeatedly forfeit" the same as "more than one forfeit"? | §2.11 | §2.11 |
| 5 | the +10 / +15 clock has no stated start | §5.3 | §5.3 |
| 6 | the 1-hour report vs the 24-hour confirmation | §5.6 | §5.6 conduct |
| 7 | does a Discord-reported result still need confirmation? | §5.6 | §5.6 outage note |
| 8 | playoff reporting duty | §5.6 / §5.7 | §5.6 playoff note |
| 9 | does per-map "home" move the server choice? | §2.3.b | §2.3.b |
| 10 | "available at the time of scheduling **or** match start" | §2.4.c | §2.4.c inclusive test |
| 11 | does the EU team keep its server choice? | §2.4.e vs §2.3.a | §2.4.c intro, §2.4.e |
| 12 | the 72-hour deadline anchor | §5.7 | §5.7 |
| 13 | "a reasonable chance" and "otherwise due to be played" | §5.7.a | §5.7.a |

A fourteenth proposal — §2.1, "Majority of players (4+)" measured against what? — was held in a
separate section as entangled with the S10 kickoff ruling, and landed in the same commit. It is the
two §2.1 items above.

---

# The §2.4 server-choice batch

Four English commits reworked who picks the server, and they only make sense read together. If you
translate one and not the others the files will contradict themselves.

| Commit | What it did | Item above |
|---|---|---|
| `a665c26` | §2.3.b — the server moves with the map, not the series | §2.3.b |
| `636b184` | propagated the per-map server ruling into §2.4.c and §2.4.e | §2.4.c inclusive test, §2.4.e |
| `98b23e9` | in NA vs EU the **NA** team picks the server, not the home team | §2.4.c intro, §2.4.c alternate |
| `a30370a` | said why §2.4.d keeps the home-team server choice | §2.4.d |

**Suggested order:** §2.3.b → §2.4.c intro → §2.4.c inclusive test → §2.4.c alternate (the one that
touches chi's #14 text) → §2.4.d → §2.4.e.

---

# What PR #14 already covers

chi's two commits from PR #14 are carried forward on this branch, unchanged and under his
authorship. #14 can be closed in favour of this PR — no work is lost.

| File | § | What he did | Still needed? |
|---|---|---|---|
| es | 1.13.a | Added the "only a played match feeds the average" paragraph | No — matches the English delta |
| es | 1.13.a | Added the "the average is a fraction" paragraph | No — matches the English delta |
| es | 1.13.a / 1.14.b | "Ejemplo resuelto" → "Ejemplo práctico"; "descansa" → "no juega" | No — his own terminology fix |
| es | 1.14.b.i | Added the placement note | No — matches the English delta |
| es | 3.9 | "durante la temporada" → "durante toda la temporada" | No — his own fix, §3.9 is not in the delta |
| pt | 1.13.a | Added the "only a played match" paragraph | No — matches the English delta |
| pt | 1.13.a | Added the "the average is a fraction" paragraph | No — matches the English delta |
| pt | 1.14.b.i | Added the placement note | No — matches the English delta |
| pt | 2.4.c | Made the priority order strict in the alternate-location paragraph | ⚠️ **Yes, one edit** — see §2.4.c alternate above; the actor changed HOME → NA |

⚠️ **One discrepancy worth knowing about:** #14's description says it fixes "*character set
formatting and bunny-hopping clarifications (§4.1.g and §4.6)*". The diff of the two commits does
not touch §4.1.g or §4.6 in either file. Either that work was intended and not committed, or the
description over-lists. Worth a look before §4.1.g/§4.6 are assumed done.

---

# Flagged for chi — English wording we did not resolve

These are places where the English is ambiguous or appears to contradict itself. **We have not
resolved any of them, and a translation should not resolve them either** — §1.15 makes the English
controlling, so a translation that tidies up an ambiguity creates a divergence rather than fixing
one. Carry the ambiguity across, and raise these separately if they are worth an English fix.

**1 · §2.3.b and §2.4.c disagree about whether the NA vs EU server is per-map.**
§2.3.b says: *"in an NA vs EU match the server does not follow the map at all"*.
§2.4.c says: *"In a best-of-three the server is chosen per map (§2.3.b), so this test is applied at
each map's start, not once for the series — a series may therefore run in different locations from
map to map."*
The reconcilable reading is that §2.3.b is about **who chooses** (always the NA team, never the map
picker) while §2.4.c is about **when the availability test is applied** (per map). But §2.3.b's
"does not follow the map **at all**" reads naturally as "one server for the whole series", which is
the opposite of what §2.4.c says. This is the sharpest conflict in the delta and it is in the
§2.4 batch, which a captain will hit in the first BO3.

**2 · §1.14 step 1's justification does not hold for a voided match.**
The new text says losses can never separate teams because *"within a division every team's wins and
losses add up to the same total"*. A **voided** match (§1.13.c) is neither a win nor a loss for
either team, so the two teams involved end the season with one result fewer than everyone else and
their wins and losses do **not** add up to the same total. The ruling itself (wins only) is fine;
the reason given for it has a hole. Translate the reason as written.

**3 · §1.13.c may declare a BYE final before a make-up match has been played.**
§1.13.c says a BYE is final once every other match that week is "recorded, forfeited, or voided",
and that a forfeit does not hold the week open. §5.3 says KTP prefers a **make-up match** and a
forfeit win is generally awarded only at the end of the regular season, for a fixture no make-up
recovered. So a match forfeited in week 4 can be made up in week 9 — producing two real scores on
week 4's map, which §1.13.a says feed that week's average — after week 4's BYE was already final.
Nothing in the text says whether the BYE reopens.

**4 · §2.11's threshold can only be reached after the season it is meant to police.**
A team may be removed after **two** forfeits, but a forfeit is *"charged when it is scored under
§1.13.c — at the end of the regular season"*. Read literally, no team can be removed mid-season for
forfeiting, which is when removal would matter. It may be that "charged" is intended only for the
counting and an admin may act earlier on declared forfeits, but the section says "that is the only
threshold".

**5 · §2.7.a's "cannot join another team for the rest of the season" overstates its own next
sentence.**
The warning says a player who leaves during a lock cannot join another team for the rest of the
season; the following sentence says additions are governed by §2.7.1's window, which exists
mid-season. So during that window they can. The warning is deliberately strong, but as written it
contradicts the sentence after it.

**6 · §2.1's "four is a majority of the six" justifies a count applied to a roster of up to ten.**
The threshold is explained as a majority of the six fielded (§2.10), but it is measured against the
roster at lock, which can be ten. A team with 4 international and 6 North American players on a
ten-player roster is International. That is stated and intended — the note says so — but the
"majority" framing invites a translator to write "majority", which is exactly what the table change
removed. Flagged so it is not reintroduced by the explanation after having been removed from the
definition.

**7 · "Forfeit" carries two meanings in the delta.**
It is a **scoring event** (§1.13.b/§1.13.c: what a match is worth) and a **disciplinary charge**
(§2.11: what counts toward removal). §1.13.c says a voided match "counts for neither team"; §2.11
says a match voided because both teams forfeited charges a forfeit to **each**. Both can be true
because they are different registers, but a single translated word for "forfeit" across both
sections will read as a contradiction. Consider whether es/pt need two terms — Portuguese already
splits this somewhat with "W.O." for the match outcome.

**8 · Terms we would flag for a translator regardless.**
- **"capout"** — does not appear in this delta, but appears elsewhere in the ruleset; confirm the
  existing es/pt rendering is what you want before this pass adds more cross-references.
- **"half"** — a DoD half, not a half of anything else. Existing files handle it; keep consistent.
- **"seed" / "berth"** — §1.14.b.i now distinguishes a playoff **berth** (getting in) from a
  playoff **seed** (where you are placed). They are different things in the new text and need
  different words.
- **"shelf"** — not present in this delta.
- **"Rapid Trigger"** — a hardware product name (§4.7). Do not translate.
- **"hold"** (§2.7.a) — suspended, not refused.
- **"charged to"** (§2.11) — counted against.
- **"awaiting a result"** vs **"scored"** (§1.13.c) — deliberately different.

---

# Issue index

The six tracking issues, folded into the worklist above. Each was opened automatically by
`.github/workflows/translation-debt.yml` on a push to `main` that touched `KTP Ruleset.md`; they are
a count of English commits, not six separate pieces of work.

| Issue | English commit | Sections it covered | Items above |
|---|---|---|---|
| #13 | `fab22d3` | §1.13.a, §1.14.b.i | §1.13.a (both, DONE by chi), §1.14.b.i placement note (DONE by chi) |
| #15 | `f6c8c2b` | §1.13.b, §1.13.c | §1.13.b, §1.13.c |
| #18 | `d756044` | §2.2.b | §2.2.b |
| #19 | `d717055` | §2.1 | §2.1 table, §2.1 new paragraphs |
| #22 | `2455ceb` | §1.10, §2.7, §2.7.a, §2.7.1 | §1.10, §2.7, §2.7.a (×3), §2.7.1 |
| #24 | `a1a72d5` | the thirteen rulings + §2.3.b/§2.4 batch | everything else above |

---

# How this branch was built, for the record

- `docs/translations-current` branches from `origin/main` at `072ac73`.
- chi's two commits from PR #14 (`b13de29`, `5073418`) are cherry-picked onto it with his
  authorship preserved. The resulting diff against `origin/main` is byte-identical to the diff of
  his two commits against their own base — +30/−4 across the two files, nothing added and nothing
  dropped.
- **`j0zj0z:main` was not written to.** His fork's default branch is untouched.
- The es/pt files carry no changes in this PR other than his.
