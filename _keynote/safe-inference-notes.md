# Keynote: "Safe Inference" — working notes

**Status:** brainstorm in progress (started 2026-07-18)
**Framing chosen:** manifesto, for a *mixed* audience (methodologists + applied + general)
**Length:** 45–60 min (decided 2026-07-18) — full ladder, Y(0) "class" argument earns its place
**Ethics angle:** *one sharp beat*, not a sermon (decided 2026-07-18) — vivid line on the
cost of omission, then back to the method
**Branch:** `claude/safe-inference-keynote-6kb9jc`

> **AUDIENCE = social scientists (decided 2026-07-18). Read this before drafting slides.**
> Not a clinical-trials room. The medical framing ("discipline over-worships the RCT")
> is *borrowed drama*, not the home critique. For this room the argument is **symmetric**:
> - **Commission is home turf.** Social scientists live in observational work; the
>   *regression tell* (a tight CI regardless of whether assumptions were mild or heroic)
>   is a sin they commit daily and recognize instantly. Lead the villain here.
> - **Omission is the provocative half.** The pressure to treat "was it randomized?" as
>   the whole test of credibility is real in social science too — but it does *not* define
>   the field's identity the way it defines clinical trials, so don't fight the RCT as if
>   it were the sole enemy. The enemy is *procedure substituting for judgment*, on **both**
>   sides of the RCT/observational line.
> - **Medical cases = imported illustrations.** GBM / melanoma / TB / COVID supply the
>   life-and-death stakes social science rarely gets to show. Every time one is used, tie
>   it *back* to the social scientist's daily bind (the observational study they under- or
>   over-claim from). **Open TODO:** find/develop a social-science-native example that has
>   the same two-condition structure (recoverable Y(0), effect clears the band).

> **Resume locally (from an open terminal):**
> ```bash
> cd <path to>/chadhazlett.github.io      # your local clone
> git fetch origin
> git checkout claude/safe-inference-keynote-6kb9jc && git pull
> claude                                    # launch Claude Code here
> ```
> First thing to tell the local session:
> *"Read `_keynote/safe-inference-notes.md` — that's the state of my safe-inference
> keynote; let's continue from the open decisions."* (A local session does not
> remember the web chat; this file is the handoff.)

> **Privacy note.** This repo is public. This file deliberately contains **only
> non-sensitive intellectual content** — the talk's argument, structure, and
> published facts. Private source material (email threads, unpublished data,
> funding/strategy discussion, collaborator contacts) is **not** reproduced
> here; it is only *pointed to* under "Where the source detail lives" so the
> notes stay safe to keep in a public repo.

---

## 1. The concept

**Safe inference** = say only what you can *defend*, and refuse to abandon what
you *can* defend. Calibrated to the defensible — no bolder, no more timid.

Already a named idea in the lab (students ask to discuss "safe inference"), not
a coinage invented for this talk. Good to state that early: it lends credibility
and signals this is a research program, not a slogan.

The creed has **two halves**, and the second is the novel one:

1. **Never assert the indefensible.** (commission)
2. **Never refuse to assert the defensible.** (omission)

A naive reading of #1 alone licenses the worst offender — the person who says
almost nothing and calls it rigor. #2 is what stops "safe" from collapsing into
"silent." That tension is the engine of the whole talk.

---

## 2. The villain

Not p-hacking, not bad actors. The enemy is a **cultural default** that lets a
*procedure* substitute for *judgment about what is defensible* — and for social
scientists it wears **two faces on opposite sides of the RCT line**:

- **The regression tell (commission; home turf).** Your output looks identical
  whether your assumptions were mild or heroic. A tight CI comes out either way.
  *False precision is the house style.* This is the sin social scientists commit
  daily in observational work — lead here; the room will recognize itself.
- **The RCT heuristic (omission; the provocative half).** Treating "did it come
  from an experiment?" as the whole test of credibility — so real, recoverable
  knowledge is discarded because it arrived by another route. Real in social
  science, but *not* the field's defining identity (unlike clinical trials), so
  don't stage it as war on the RCT. Both faces are the *same* failure: procedure
  in the seat where judgment belongs.

Two faces, one failure. Map onto **two errors** (deliberately evoke, but do NOT
label as, Type I / Type II — audience will think it's the ordinary one):

- **Error of commission** — asserting an effect that isn't defensible.
- **Error of omission** — failing to assert an effect that *is* defensible.

Punchline: *we have built a discipline that polices one error and is structurally
blind to the other.* We drill commission down with robustness tables and referee
demands, then either (a) over-claim anyway when the procedure says we may, or
(b) go silent the moment the evidence isn't an experiment — and call the silence
rigor. The medical cases (§4) show where that silence costs lives; the point for
*this* room is that the same reflex quietly discards defensible social-science
knowledge every day, without a body to mark the loss.

---

## 3. The engine (the "how")

One **generative question**, not a menu of estimators:

> *Where can we defensibly* know*,* bound*, or* model *the counterfactual —
> Y(0) — without an experiment?*

Chad's own crisp statement of the move (vs. the "externally controlled trials"
literature, which still tries to *use the data* to point-identify):

> *Declare a defensible interval for δ (the residual bias), then report the
> entire ATT band across that interval.*

That is safe inference in one line. Sensitivity analysis, partial
identification, and SCQE are all instances. Four ways to get at Y(0):

- **Know it** — prognosis near-deterministic (e.g., uniformly fatal disease),
  so Y(0) is essentially known; a single treated arm is then nearly as
  informative as an RCT.
- **Bound it** — partial identification: a range you believe.
- **Model its trend** — SCQE: replace the untestable "no confounding" with a
  *nameable, boundable* assumption about the baseline trend across cohorts.
- **Stress-test it** — sensitivity analysis: how wrong would you have to be?

**Graceful degradation** (demoted from creed to *mechanism*): these tools turn
the RCT-fundamentalist's light switch (RCT → believe; else → silence) into a
*dimmer*. As knowledge of Y(0) weakens, the claim weakens smoothly through a
zone of defensible ranges. That continuity is what dissolves the false binary
between the two errors.

**Deep point (intellectual heart):** an RCT's value is *proportional to our
ignorance of Y(0)*. Randomization buys protection against confounding in the
counterfactual we'd otherwise have to guess. Where Y(0) is knowable by other
means, that protection is redundant — demanding the trial anyway is not rigor,
it's ritual.

**The two conditions (added 2026-07-18, from the melanoma/pancreatic dig).**
Safe non-RCT inference needs *both*, and naming the second sharpens the whole
thesis — it's what keeps "the trial is optional" from becoming reckless:

1. **Recoverable Y(0)** — the counterfactual is known or defensibly boundable
   (a narrow δ-interval).
2. **Signal clears the band** — the effect must be *large relative to the
   δ-band width + selection*. In δ-band language: safe inference concludes only
   when the *whole* ATT band clears the decision threshold. A knowable-but-noisy
   Y(0) plus a small effect leaves a band that straddles zero — and *that* is
   precisely when you still want the RCT.

This reframes the RCT not as the enemy but as the right tool for one regime:
**small effect relative to a wide-or-uncertain Y(0) band.** The manifesto isn't
"trials are ritual" — it's "match the instrument to where Y(0) actually sits."
Pancreatic (below) is the honest case where condition 2 fails; that honesty is
what makes the class argument credible rather than triumphalist.

---

## 4. The examples — a ladder of difficulty

Same engine (defensible δ → ATT band), three verdicts. This ordering shows the
method doing *both* jobs, which defeats the "this is just skepticism" prior.

### (a) TB / isoniazid preventive therapy — the RESTRAINT case (commission)
Published SCQE application. IPT in HIV patients in Tanzania; treatment adopted
non-randomly. **The naive comparison is dramatic and misleading** — much of the
therapy went to *low-risk* patients, so a raw treated-vs-untreated gap
overstates the effect. SCQE reframes it honestly: state the defensible baseline
trend, report the ATT band. Guards against believing the indefensible.
*(Public figures: ~26,715 HIV patients; ~25% received IPT after it became
available; within a year <1% of treated vs 16% of untreated developed TB —
exactly the kind of raw gap that needs the SCQE treatment.)*

### (b) GBM — the RESCUE case (omission); the FLAGSHIP
A treatment we're nearly sure worked, not credited because the inference sits
outside an RCT and rests on reasoning about Y(0) where prognosis is clear.
**The wrinkle that makes it the best demo:** it's not naive Y(0) imputation.
There's a (compromised) trial design → study sample is *mostly but not entirely*
treated. You *could* use only the treated arm and impute Y(0); instead, use the
**whole study group + SCQE** to compute Y(0) for the treated and recover the
**ATT**. So it showcases safe inference under **non-random selection into
treatment**, not just the easy "Y(0) is known" case.

### (c) Three COVID treatments — the SCALE case (omission, under time pressure)
Informative claims about three treatments that would be impossible under the RCT
heuristic — where *waiting for the trial was itself the costly choice*. Traces
to worked dissertation analyses (real, not hypothetical).

### (d) The class — melanoma & pancreatic (worked 2026-07-18; the TWO-CONDITION lesson)
No longer loose anecdotes. Researched, and together they *define the class
boundary* — which is stronger than three confirming cases, because the boundary
is where the method earns its honesty.

- **Melanoma — vemurafenib (BRAF-V600E; Zelboraf). SHARES the structure, strongly.**
  Single-arm signal was a "Lazarus effect" (~50% RECIST response, tumor shrinkage
  in ~80%). Y(0) is near-deterministic: pre-2011 metastatic melanoma median OS
  ~6–9 mo (M1c ~5 mo), dacarbazine "control" ~5% response ≈ natural history,
  spontaneous metastatic regression ~0.23%. So a ~50% response against a ~0%
  counterfactual = a single arm nearly as informative as an RCT. **The gift:** the
  pivotal RCT (BRIM-3, vs dacarbazine) drew public argument that *randomizing was
  unethical because Y(0) was already known* (Amy Harmon, NYT, Sep 2010 — two cousins,
  one lottery'd to the ineffective arm). That IS the safe-inference argument in the
  wild. *(Cleaner regulatory instance if wanted: pembrolizumab / KEYNOTE-001, 24%
  ORR, accelerated approval 2014 with RCTs only as confirmation.)*
- **Pancreatic — daraxonrasib (RMC-6236, RAS(ON) inhibitor). PARTIALLY — condition 2 fails.**
  Untreated metastatic PDAC median OS ~3.5 mo, so Y(0) is *equally* recoverable
  (condition 1 met). BUT the effect is incremental — single-arm ORR ~30%, OS gains
  in *months* — which sits inside the selection/δ-noise band (phase-1 patients are
  fitter than historical controls; a few months' OS is exactly what selection can
  manufacture). So **condition 2 (signal clears the band) fails**, and the field
  correctly ran the confirmatory RCT (RASOLUTE-302: OS 13.2 vs 6.7 mo, HR 0.40) —
  which a single arm could not have credibly established.

**The class claim, stated honestly:** *"Wherever Y(0) is recoverable* and *the
effect is large relative to the band, the trial is optional; where the effect is
small relative to the band, the trial is doing real work."* Melanoma + GBM sit on
the "optional" side; pancreatic marks the far edge where the RCT is warranted.
This two-sided class is the §5 climax — it proves calibration, not skepticism.

> **Framing guard (audience = social scientists):** these are *borrowed*
> illustrations. Each time, land the transfer explicitly — e.g. "you don't
> estimate cancer survival, but you *do* face the exact same call every time a
> reviewer says 'but it's not an experiment' about an effect you can defend."
> Sources for all figures live in the research memo (scratchpad) / §9.

---

## 5. The arc (manifesto shape) — TIMED for 45–60 min (~52 target)

Times are a spine, not a stopwatch. GBM is **double-teased**: 30-sec human hook
up front (unresolved), full structural payoff in the flagship slot — a move only
the long slot affords.

1. **Cold open — the near-miss (3 min).** Lead with the *omission* error (the
   surprising one): a treatment we're nearly sure worked, not credited, because
   it didn't come from an experiment. Tell it as a person, not a method. Tease
   GBM; do NOT resolve. Plant the question: *how many defensible truths are we
   throwing away — and would we even notice?*
2. **The two errors (4 min).** Name commission vs omission (evoke, don't label,
   Type I/II). The turn: *we police one and are blind to the other.* For THIS
   room, immediately locate both in social-science practice, not just medicine.
3. **The villain (7 min).** Two faces of one failure — procedure substituting for
   judgment. **Regression tell** (commission, home turf: false precision) →
   **RCT heuristic** (omission: credibility outsourced to a certificate). Keep it
   two-sided; the enemy straddles the RCT/observational line.
4. **The creed (3 min).** Assert only the defensible; refuse to abandon the
   defensible. Two halves; the second is the novel one. It's an existing lab idea,
   not a slogan coined for the talk (say so — lends credibility).
5. **The engine (13 min).** The one generative question (know / bound / model /
   stress-test Y(0)); δ-interval → ATT band. Then the **two conditions** (§3):
   recoverable Y(0) *and* signal-clears-the-band. Graceful degradation as a
   *dimmer* not a switch. The deep point: an RCT's value ∝ our ignorance of Y(0)
   — and the second condition says exactly when the trial is still doing real work.
6. **The ladder (14 min).** Same engine, escalating difficulty & opposite verdicts:
   **TB / RESTRAINT** (commission — naive gap overstates; SCQE reins it in) →
   **GBM / RESCUE** (omission; *resolve the cold open*; the hard case — non-random
   selection, whole study group + SCQE, recover the ATT) → **COVID×3 / SCALE**
   (omission under time pressure; waiting *was* the costly choice) → **the class**
   (melanoma shares it; pancreatic marks the boundary where the RCT earns its keep).
7. **The symmetry (4 min).** Put TB (restrain) and GBM (rescue) side by side: one
   engine, opposite verdicts. Proof it's *calibration*, not skepticism and not
   boldness. This is the slide that disarms "you're just an RCT skeptic."
8. **One sharp beat — the cost of omission (2 min).** A single vivid line: the
   omission error has a body count too; in social science it just doesn't leave
   one. Then step off the pedal — back to method. (Per decision: no sermon.)
9. **The call to act (5 min).** The creed as adoptable norms (§6). Reframe what
   "rigor" means: not the tightest interval but the truest one. Close on the
   flipped-SICSS line.

---

## 6. Draft creed slide (norms to pin above a desk)

1. State the assumption you cannot test *before* the estimate, not in the appendix.
2. Report how wrong you'd have to be, to be wrong.
3. Never let a tight interval stand in for a strong assumption.
4. A range you believe beats a point you don't.
5. Do not discard defensible evidence for want of a trial.
6. Reward the honest "we can't tell yet" over the confident wrong answer.

Closing line candidate (flips the SICSS title "Causality you can believe in?"):
*Causality you can believe in isn't the causality that sounds most certain —
it's the causality still standing after you've told the whole truth about what
you assumed.*

---

## 7. Decisions & open items

**Resolved 2026-07-18:**
- ~~Length~~ → **45–60 min** (~52 target; see timed arc §5).
- ~~Ethics lean~~ → **one sharp beat**, no sermon (arc step 8).
- ~~Cold open~~ → **GBM, double-teased** (30-sec hook up front; payoff in flagship slot).
- ~~Melanoma/pancreatic structure~~ → **worked (§4d).** They define the *class
  boundary*: melanoma shares it strongly; pancreatic fails condition 2. This
  produced the two-condition refinement to the engine (§3) — the biggest single
  upgrade so far.
- ~~Audience~~ → **social scientists** (see top-of-file framing box). Villain now
  two-sided; commission is home turf, omission is the provocative half.

**Still open:**
- **Social-science-native example.** All flagship cases are medical (borrowed
  drama). Need ≥1 example from the room's own world with the two-condition
  structure — recoverable Y(0) + effect clears the band. (Candidates to scout:
  a policy change where the pre-trend / baseline is genuinely nameable-and-boundable
  — SCQE-style — vs. one where it isn't, mirroring the pancreatic boundary.)
- **The COVID×3 case** still needs a crisp one-slide statement of each (from the
  dissertation chapters) so "SCALE" isn't a gesture.
- **Slide build.** Notes are now rich enough to start an actual deck. Decide
  medium (Beamer / Keynote / reveal.js) before drafting.

---

## 8. Where the source detail lives (NOT reproduced here — public repo)

- **SCQE / δ-band framing + "RCT heuristic" + 3-examples project idea:** Gmail
  thread "Another non-RCT rejection" (May 2026) and "Bluesky needs SCQE?" (Apr
  2026), which also has a plain-language SCQE explanation usable for lay slides.
- **GBM analysis details:** emails re: the GBM R01 with the neurosurgery/computational-
  medicine collaborator; and the SCQE browser/demo app on Chad's GitHub.
- **COVID ×3:** worked dissertation chapters (committee materials).
- **TB numbers/method:** the Statistics in Medicine paper PDF (see references).

---

## 9. References

- Hazlett, C. (2020). *Inference without randomization or ignorability: A
  stability-controlled quasi-experiment on the prevention of tuberculosis.*
  Statistics in Medicine, 39(28), 4169–4186. DOI: 10.1002/sim.8717.
  Open version: https://escholarship.org/uc/item/5f84x9bm
- Related earlier framing: Chad's 2018/2019 JCI piece (cited in lab discussion
  as the non-technical seed of these ideas).
- Site talk pages already live in this repo: `SICSS2026/` ("Causality you can
  believe in?") and `ISSM2026/` (identification foundations).

**Medical illustration sources (borrowed drama — verify before quoting on a slide):**
- Melanoma / vemurafenib: Chapman et al., *NEJM* 2011 (BRIM-3),
  https://www.nejm.org/doi/full/10.1056/NEJMoa1103782 ; FDA approval summary,
  *Clin Cancer Res* 2014, https://aacrjournals.org/clincancerres/article/20/19/4994/208680 ;
  the "is randomizing ethical?" story — Amy Harmon, NYT, Sep 2010 (two cousins).
  Prognosis: metastatic melanoma median OS ~6–9 mo; spontaneous metastatic
  regression ~0.23%.
- Pancreatic / daraxonrasib (RMC-6236): Revolution Medicines release, RASOLUTE-302
  (OS 13.2 vs 6.7 mo, HR 0.40), https://ir.revmed.com/news-releases/ ; single-arm
  ORR ~30% via OncLive. Untreated metastatic PDAC median OS ~3.5 mo (PMC6759720).
  *Use as the boundary case (condition 2 fails), not a confirming case.*
