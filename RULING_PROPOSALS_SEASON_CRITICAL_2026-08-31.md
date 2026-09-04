# Season-critical rulings — the ones that bite during S10

Third batch from the **43** ambiguities `#9` surfaced. `#10` took the six contradictions; `#11` took four that needed no vote. These **fourteen** are the ones a live season will hit — most of them in the first few weeks.

The rest (~18) are conduct and housekeeping questions with no deadline. They will rule better after a season has actually run, and they are listed at the end so nothing is lost.

⚠️ **Where the software already decides, that is stated.** Several of these are less open than they look, and one is not open at all once you look at the schedule.

---

## A. Scoring and standings — these bite at week 1

### 1 · §1.14 step 1 — "most wins, then fewest losses" cannot separate anyone

Every team in a division plays the same number of matches, and §1.13.a is explicit that a BYE **is not a result** — it adds no win and no loss. So wins and losses always sum to the same total, and "fewest losses" can never break a tie that "most wins" did not already break.

**Proposed:** collapse step 1 to **most wins**, and say that losses are informational. Nothing changes in practice; the rule stops describing a second step that cannot fire.

⚠️ Exception worth naming: it *can* fire where a division has an odd number of teams and an uneven week count, because then teams genuinely play different numbers of matches. If that is intended to be possible, say so — otherwise the fix for it is the week count, not the tiebreaker.

### 2 · §1.14.a — what "identical record" means

Could mean identical **wins and losses**, or merely **tied after step 1**. And a forfeit is called "a head-to-head result like any other" while §1.13.c gives it no score until the end of the season.

**Proposed:** "identical record" = tied after step 1. And head-to-head reads **win/loss only, never the scoreline** — which is the only reading consistent with §1.13.c, since a forfeit has no scoreline to compare until the season ends.

### 3 · §1.14.b.i — "or any other consequence", and who decides one exists

Open-ended, and nothing says who determines that a consequence exists — i.e. when the admin ruling is triggered at all.

**Proposed:** an admin ruling is triggered when the tie decides **a playoff berth, a playoff seed, or a relegation/promotion position**. Anything else is left as a tie. If the list should be open-ended, then say explicitly that **an admin declares the trigger**, so the answer is never "nobody knew whose job it was".

### 4 · §2.11 — is "repeatedly forfeit" the same as "more than one forfeit"?

Two consecutive sentences use different phrasings and nothing says they are the same threshold. Separately, it is not stated whether a **forfeit win** (§5.3) counts toward a team's tally.

⚠️ **Nothing tallies forfeits in code today**, so whichever way this goes there is no migration.

**Proposed:** one threshold — **two forfeits in a season** — and a forfeit **win never counts against the team that turned up**. The team that showed up is in the same position as a team on a BYE (§1.13.b's own reasoning); charging it is perverse.

---

## B. Match-day timing — these bite the first time someone is late

### 5 · §5.3 — the +10 / +15 clock has no stated start

Default time under §2.2, or the time actually scheduled? They differ whenever a match is rescheduled, which is common.

**Proposed:** the clock runs from **the match's actual scheduled kickoff**, not the §2.2 default. A rescheduled match that both captains agreed to is the real appointment. ⚠️ This is the reading the site supports, since `match.scheduled_at` is the stamped time and the default is only its initial value.

### 6 · §5.6 — the 1-hour report vs the 24-hour confirmation

Which clock is a late-but-confirmed result judged against, and what happens if **neither** captain enters a result?

**Proposed:** the 1-hour duty is on the **winning** captain and is a conduct matter, not a validity one — a result confirmed inside 24 hours **stands regardless of when it was filed**. If neither captain files within 24 hours of kickoff, the fixture goes to **admin adjudication**, not to an automatic outcome. ⚠️ Nothing automates this today, and §1.13.c's *"nothing voids automatically"* is the established posture.

### 7 · §5.6 — does a Discord-reported result still need confirmation?

**Proposed:** yes. Discord is a reporting **channel**, not a second authority — the opposing captain confirms in the same window either way. An admin entering a result directly is the exception, and it supersedes.

### 8 · §5.6 vs §5.7 — playoff reporting duty

"Playoff series results and forfeits are recorded by admins" leaves it unclear whether a winning captain retains any 1-hour duty.

**Proposed:** no. In playoffs the recording duty is the admin's; captains report **only** if no admin is present, and then the 1-hour clock applies.

---

## C. Server and side choice — BO3 exposes these immediately

### 9 · §2.3.b vs §2.4 — does per-map "home" move the server choice?

In a BO3 the team that picked a map is "home" for it, but picks are run by the site's veto room and §2.4 gives HOME the server choice.

⚠️ **The software models `home_season_team_id` per fixture but has no server-choice field at all** — server choice is a human convention today.

**Proposed:** per-map home status carries **side choice only**. The **server** is fixed for the whole series by the §2.4 home team, because changing server mid-series is an operational burden with no competitive rationale.

### 10 · §2.4.c — "no New York servers available at the time of scheduling **or** match start"

Inclusive or exclusive, and which moment governs when they differ?

**Proposed:** **inclusive** — either moment qualifying is enough. If they differ, **match start governs**, because that is when the match actually needs a server.

### 11 · §2.4.e vs §2.3.a — does the EU team keep its server choice?

The override covers the *side* choice for NA vs EU and is silent on the server choice the EU team holds as HOME under §2.4.c.

**Proposed:** the override covers **side only**. The EU team keeps the server choice it holds as HOME. ⚠️ If the intent was to move both, that must be said — it is a materially different rule and the two have been read both ways.

---

## D. Playoffs — less open than it looks

### 12 · §5.7 — the 72-hour deadline anchor

`#9` flagged that no rule defines which Sunday a playoff round defaults to, so the 72-hour deadline has no computable anchor.

✅ **It does have one.** Playoff rounds are **weeks with dates**, exactly like regular-season weeks. S10 as scheduled: **round 1 = 2026-11-15, round 2 = 2026-11-22, round 3 = 2026-12-06**, with a **bye week on 11-29** between rounds 2 and 3.

**Proposed:** state that a playoff round's default date is **its week's Sunday**, and that the 72-hour deadline runs from that date's default kickoff. ⚠️ And name the gap: **rounds are not always consecutive Sundays** — S10 has a bye week inside the bracket, so "the following Sunday" would be wrong.

### 13 · §5.7.a — "a reasonable chance to run it" and "otherwise due to be played"

Both undefined, and both decide whether a playoff match is forfeited or rescheduled.

**Proposed:** "a reasonable chance" = **the full 72-hour window under §5.7 elapsed with the fixture reachable by both captains**. "Otherwise due to be played" = **scheduled within its own playoff week**. Anything looser leaves an admin defending a judgement with no rule behind it, on the one match where the stakes are highest.

---

## E. Entangled with the S10 kickoff ruling

### 14 · §2.1 — "Majority of players (4+)" measured against what?

Roster maximum is 10 (§2.7); a match lineup is 6 (§2.10). **4 is not a majority of 10.** Which population the 4+ measures is unstated.

🔴 **This one is urgent and cannot wait for the vote**, because §2.2.b's international kickoff is decided from §2.1 declarations and **schedule generation stamps kickoff once**. Eight teams have declared §2.1; zero are flagged §2.2.b.

**Proposed:** the 4+ measures the **rostered squad at the roster lock**, not the match lineup — a team's region is a property of the team, not of who happens to start. And "majority" is dropped from the wording: **the threshold is 4 or more**, which is what the number actually says. Calling 4-of-10 a majority is the source of the confusion.

---

## Deliberately held — no deadline, and they rule better after a season

**Conduct:** §3.5 vs §5.1.a (custom HUD approval with no procedure) · §3.7 (whether non-cheating disputes exist) · §3.9 vs §3.9.a (a 14-day contest window against 30-day telemetry retention — **formally contestable and materially un-re-examinable at once**) · §4.4 (boosting, which read literally permits it only where it grants nothing) · §4.5 ("neg" is undefined slang) · §4.6 ×2 · §4.8.

**Housekeeping:** §1.7 (elapsed or remaining clock) · §1.8 (is the automatic 30-second pause charged to the budget) · §2.6/§2.7/§2.7.1 (does the lock extinguish an unused change; the mid-season window is not cross-referenced) · §4.1.b/c (which SteamID is "registered" after a permitted change) · §4.1.e ×2 · §4.1.f · §4.1.g's ASCII list · §5.4.a.

⚠️ §3.9 is the one to promote if any of these turn out to matter sooner — it is the only held item where **waiting destroys the evidence**.
