# Keynote: "Safe Inference" — working notes

**Status:** brainstorm in progress (started 2026-07-18)
**Framing chosen:** manifesto, for a *mixed* audience (methodologists + applied + general)
**Branch:** `claude/safe-inference-keynote-6kb9jc`

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
*procedure* substitute for *judgment about what is defensible*:

- **The regression tell:** your output looks identical whether your assumptions
  were mild or heroic. A tight CI comes out either way. *False precision is the
  house style.*
- **The RCT heuristic** (Chad's phrase): treating "did it come from an RCT?" as
  the whole test of credibility — so real, recoverable knowledge is discarded
  because it arrived by another route.

Two faces, one failure. Map onto **two errors** (deliberately evoke, but do NOT
label as, Type I / Type II — audience will think it's the ordinary one):

- **Error of commission** — asserting an effect that isn't defensible.
- **Error of omission** — failing to assert an effect that *is* defensible.

Punchline: *we have built a discipline obsessed with one error and structurally
blind to the other.* The RCT-only stance drives commission-error toward zero by
refusing to claim — and congratulates itself while the omission-error runs wild
and, in medicine, costs lives.

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

### (d) Other "missed-opportunity" topics (as topics, not yet worked)
- FDA rejection of a breakthrough **melanoma** drug (non-RCT evidence).
- **Pancreatic** cancer therapy (news-stage pointer).
Open question: do these share the GBM *structure* (Y(0) recoverable)? If yes,
present as a **class** — "wherever the counterfactual is nearly known/boundable,
the trial is optional" — far stronger than three anecdotes.

---

## 5. The arc (manifesto shape)

1. **Cold open** — lead with the *omission* error (the surprising one): a
   treatment we're nearly sure worked, withheld. Tease GBM; don't resolve.
2. **The villain** — two faces of one failure: procedure substituting for
   judgment (regression stars; the RCT certificate).
3. **The creed** — assert only the defensible; refuse to abandon the defensible.
4. **The engine** — the one question (know / bound / model / stress-test Y(0));
   δ-interval → ATT band; each with an instance.
5. **The symmetry** — TB (restrain) and GBM (rescue): same reasoning, opposite
   verdicts. Proof it's calibration, not skepticism and not boldness.
6. **The call to act** — the creed as adoptable norms; reframe what "rigor"
   means; the *ethics* of the omission error (real cost, real bodies).

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

## 7. Open decisions

- **Length?** 20 vs 45 min changes whether the ladder gets one example each or
  room to breathe.
- **Cold open:** need one concrete, human near-miss. GBM is the current best.
- **How hard to lean on the ethics/regulatory angle** for a mixed room.
- Do the melanoma/pancreatic cases share the GBM Y(0) structure? (→ class vs.
  anecdotes)

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
