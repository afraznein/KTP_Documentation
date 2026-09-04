# Six ruleset contradictions — proposals for an admin vote

Surfaced by the es/pt translation pass (`#9`): translating a rule forces you to read it precisely, and 43 ambiguities fell out. These are the **six apparent contradictions** — the ones the translators said "may need an actual ruling".

**Four of the six are already decided in shipped code.** The software has been behaving one way for weeks; the ruleset simply never said so. Those are proposed as **ratifications** — the vote is whether the behaviour is right, not what to build. Two are genuinely open.

⚠️ **`KTP Ruleset.es.md` and `KTP Ruleset.pt.md` are NOT edited in this PR.** English is authoritative; the translations must follow whatever is ratified, or they drift from it. That is a deliberate second step, not an oversight.

---

## Ratifications — the code already does this (vote: confirm or override)

### 1 · §1.10 vs §1.13.c — an unfinished overtime

**The collision.** §1.10 said failing to complete overtime records "a loss for **both teams**". §1.13.c says where both teams forfeit the match is **voided** and neither collects. Same event, two outcomes.

**What the software does:** voids it. `voidMatch` exists and is documented as *"the match produced no winner and never will — double forfeit"*. There is **no implementation anywhere of a both-teams-loss**, so §1.10's penalty has never executed. Also worth knowing: *"Nothing voids automatically; a missed deadline stays an admin decision."*

**Proposed:** one team at fault → forfeit under §1.13.b. Both at fault → void under §1.13.c. §1.10 no longer invents a third outcome.

### 2 · §1.13.c was self-referential

**The collision.** A BYE is final "as soon as every other match that division played that week has been scored" — but a forfeit that week "is scored **only at the end of the regular season**". Read literally, **any week containing a forfeit can never satisfy the BYE's finality condition until the season ends.**

**What the software does:** settles a BYE on **match status**, not on credit finality — final once no match that week is still `scheduled` or `in_progress`. A forfeited match *has* an outcome, so it does not hold the week open; `cancelled` "neither blocks settlement nor feeds an average".

**Proposed:** say that explicitly — separate *"every match has an outcome"* from *"every credit is final"*. The self-reference dissolves.

### 3 · §1.13.a vs §1.13.b — is the forfeit credit one-sided?

**The collision.** §1.13.a credits a BYE as *both* points for and against, and rests its zero-differential rationale on that. §1.13.b says the average is credited "to the non-forfeiting team only" without saying **in which direction**. Read one way, a forfeit win moves differential and a BYE does not.

**What the software does:** treats a forfeit as "a bye for that team alone" (operator ruling, 2026-08-20, recorded in `bye-scoring.ts`). A BYE credits both directions — so a forfeit is **differential-neutral too**.

**Proposed:** state it. A team is not rewarded in the differential tiebreak for an opponent who did not turn up, any more than for sitting out.

### 6 · §4.6 vs §4.7 — Rapid Trigger is not Rapid Fire

**The collision.** §4.6 permits Rapid Trigger explicitly and distinguishes it from Rapid Fire. §4.7's bare "Rapid-fire" bullet carries no such distinction, so a reader applying §4.7 alone bans legal hardware.

**What the software does:** the anticheat treats Rapid Trigger as **legitimate hardware** — it has an entire attribution pipeline for Hall-effect boards.

**Proposed:** §4.7's bullet carries the distinction inline. Rapid Trigger shortens *when* a key registers; it never multiplies a press into more than one input.

---

## Genuinely open — nothing in code decides these

### 4 · §4.1.g — three length limits that cannot all bind

> Player aliases and team tags must not exceed 30 visible characters. Full in-game names (team tag + player handle) must also not exceed 30 visible characters.

If alias ≤ 30 **and** tag ≤ 30 **and** tag + handle ≤ 30, the first two are unreachable in combination with the third. A 30-character tag leaves zero characters for the handle.

⚠️ **Nothing enforces any of the three in code today** — it is pure text, so whichever way this goes there is no migration and no live breakage.

**Option A — the combined limit is what binds.** Tag + handle ≤ 30 total; individual caps become "no single part may fill the whole budget". Simplest, and matches what the in-game name actually has to fit.

**Option B — raise the combined limit.** Keep alias ≤ 30 and tag ≤ 30, and set the combined cap to something reachable. Requires picking a number nobody has measured against DoD's actual name field.

**Option C — the individual caps are advisory; only the combined one is enforced.**

*Recommendation: A.* It is the only reading under which all three sentences can be true at once, and it describes the constraint that physically exists.

### 5 · §3.4 vs §4.6 — the same conduct, two penalty regimes

Input multiplication — *"Snap Tap" / SOCD null-cancel, "Rapid Fire" / Turbo, or any bind, script, or device feature that turns one press into more than one action* — appears in **both**:

- **§3.4** lists it as **cheating**, which §3.3 makes **zero tolerance**.
- **§4.6** lists it as a **prohibited binding**, penalised under §1.2.

**Which applies is not stated**, and the two ends are very far apart: a ban versus a warning, for identical behaviour.

🔴 **This is the one with real stakes.** It is exactly the ambiguity an accused player will contest, and the anticheat *does* detect this class — so it will come up with a named person attached.

**Option A — §4.6 governs; §3.4 drops input multiplication.** Bindings and device features are a configuration failure, escalating under §1.2. Cheating stays for wallhacks, aimbots, file modification. ⚠️ Weakest response to a deliberate macro user.

**Option B — §3.4 governs; §4.6 cross-references it.** Input multiplication is cheating whatever produced it. ⚠️ Zero tolerance then applies to someone whose keyboard shipped with SOCD enabled by default and who never opened the software — which the AC's own attestation work exists precisely because it cannot rule out.

**Option C — split by intent and provenance.** §4.6 (config-level, §1.2) governs a first occurrence disclosed or detected without concealment; §3.4 (cheating) governs concealment, repetition after notice, or a device configured expressly for it.

*Recommendation: C*, with the boundary written into §3.4 rather than left to adjudication. It is the only option that survives the case the anticheat keeps producing — **a legitimate Hall-effect keyboard whose owner did not know**, of which there are currently 15 Wooting owners without Wootility and 4 NuPhy owners on the AC's own accepted-risk list. Under B every one of them is a zero-tolerance case.

---

## What is NOT in this PR

The other **37** ambiguities from `#9` — dangling cross-references (§4.1.e, §5.7), undefined terms (§1.7's elapsed-vs-remaining clock, §4.5's "neg"), and one structural nesting error at §1.14.b.i. They need rulings too, but none of them contradicts another rule.

🔴 **Separately and urgently: §2.2.b cites "per Rule 2.1" for a UTC−2 longitude test that Rule 2.1 does not contain**, and no code implements such a test either — `season_team.international` is a hand-set flag. **Eight teams declared §2.1 and zero are flagged §2.2.b.** Generation stamps kickoff once, so that ruling is needed before the S10 schedule is generated. It is not in this PR because it is a different kind of decision: per-team, not per-rule.
