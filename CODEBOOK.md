# The Reach Failure Codebook

*An instrument of the Eve's Law project · Hewan Tolera*

**Version 1.0 · 25 September 2026**

A coding scheme for recording where an AI deployment caused harm that existing
law could not reach, and which regulatory instrument would have reached it.

This document is canonical. It is versioned and never silently edited; all
changes are recorded in `CHANGELOG.md` with a date and a reason. Cite the
version you coded against.

---

## Scope

The scheme codes **deployments**, not models. The unit of analysis is a single
incident in which an AI system was in the causal chain of a harm to an
identifiable person or class.

It is deliberately agnostic to sector. A case qualifies whether the system was
a language model, a classifier, a matching system, or a retrieval network.

## Structure

Two layers.

**The portable layer** is the six fields below. It is fixed. It applies to any
deployment in any sector and does not change when the subject matter changes.

**The domain layer** is case selection — which harms are coded first. It is
swappable. Narrowing it proves the instrument; broadening it dilutes the
instrument. See `METHOD.md` for the current inclusion criteria.

---

## F1 · POSITION

**Question:** What did the system's output do, structurally, in the chain of
action?

**Values (select one):**

| Code | Meaning |
|---|---|
| `retrieve` | Returned matching records from a store in response to a query |
| `flag` | Surfaced an item for human attention |
| `filter` | Removed or suppressed items before a human saw them |
| `generate` | Produced new content |
| `distribute` | Selected who received something |
| `decide` | Produced an outcome applied without human review |

**Coding note.** This field records function, not capability. Risk follows from
what an output is used to do, not from how advanced the underlying model is. A
sophisticated system in a low-stakes position is not the problem this scheme is
built to find; a crude one in a decisive position is.

**Common miscoding.** Coding `decide` because the output determined what
happened. If a human acted on the output, the position is `flag` or `retrieve`
and the human's role is recorded in F2. Collapsing the two makes F2 unreadable.

---

## F2 · DISCRETION — *novel field*

**Question:** What did the system do to the judgment of the person holding
power over the subject?

**Values (select one):**

| Code | Meaning |
|---|---|
| `expanded` | The output gave a human confidence or cover to act in a way they could not otherwise have justified |
| `checked` | The output constrained or audited a human decision |
| `replaced` | The output substituted for a human decision that was previously made by a person |
| `none` | No human discretion was implicated |

**Coding note.** This is the field that separates a tool failure from a power
failure. `expanded` is the finding that most often goes unrecorded, because it
is routinely miscoded as automation bias — a psychological description of the
human — when the structural fact is that the deployment converted a weak
inference into an actionable one.

**Test for `expanded`:** would the human's action have survived review on the
non-AI evidence alone? If no, and the action was taken anyway, code `expanded`.

**Test for `checked`:** did the output create friction against a human decision
rather than support for it? Systems coded `checked` are the ones the absence
value in F4 asks about.

---

## F3 · STAKES

**Question:** How bad, for whom, and did they know?

Three sub-fields, each coded separately.

**F3a — Reversibility:** `reversible` · `costly` · `irreversible`

Code `irreversible` where no later correction restores the subject's position:
incarceration served, a record created, a relationship ended, a death.

**F3b — Bearer:** `user` · `subject` · `third party`

The `subject` is the person the system operated on. Distinguish from `user`,
the person operating it. Where the subject had no relationship of any kind with
the deploying organisation, code `third party`.

**F3c — Awareness:** `informed` · `unaware`

Whether the bearer knew the system was operating on them and had any mechanism
to contest its output before it took effect.

**Coding note.** The subject of a system is frequently not its user. Systems
are evaluated almost entirely for the user's experience of them, which is why
the bearer must be recorded separately from the severity.

---

## F4 · FAILURE MODE

**Question:** What went wrong, mechanically?

**Values (select all that apply):**

| Code | Meaning |
|---|---|
| `false positive` | The system asserted something that was not true |
| `false negative` | The system failed to assert something that was true |
| `inference chain` | Each output was accurate; the chain of inference built on them was not |
| `routing` | The output reached the wrong party, or failed to reach the right one |
| `threshold` | The sensitivity setting excluded the harm |
| `taxonomy gap` | The harm was outside the categories the system was built to recognise |
| `absence` | *(novel value)* Harm occurred because no system was watching a place where one was available, affordable, and effective |

**Coding note on `absence`.** This value records the failure to deploy, not a
failure of deployment. Without it, the scheme can only ever recommend
restriction, which is why existing harm taxonomies read as uniformly
subtractive and are received as hostile by the people who would have to
implement them.

**Threshold for coding `absence`:** the auditing or checking capability must
have been (a) technically available at the time, (b) low-cost relative to the
harm, and (c) not deployed. Speculative capability does not qualify. State the
basis for (a) and (b) in the record.

**Note.** `inference chain` and `absence` frequently co-occur, because a chain
failure is usually also an unaudited chain.

---

## F5 · REACH FAILURE

**Question:** Which specific doctrinal element prevented existing law from
reaching this harm?

**Values (select all that apply):**

| Code | Meaning |
|---|---|
| `no cause of action` | No recognised legal claim covers this harm |
| `element missing` | A claim exists but fails at a named element |
| `immunity` | A defendant is shielded (qualified, sovereign, statutory) |
| `not a state actor` | A private defendant is outside a public-law remedy |
| `no defect` | The product performed as designed, defeating product liability |
| `safe harbor` | A statutory immunity applies (e.g. CDA §230) |
| `no private right` | A statute governs the conduct but creates no private enforcement |
| `no detection` | The harm is structurally undiscoverable by the person harmed |
| `preemption` | A higher jurisdiction has displaced the applicable rule |

**Coding note.** Name the element, not the mood. "The law is inadequate" is a
complaint. "Fails at the commercial-use element" tells a drafter which sentence
to change. Where `element missing` is coded, the specific element **must** be
named in the record.

**Interpretive rule.** A harm category with near-zero filings is evidence of
reach failure, not evidence of low harm. Litigation volume measures legal
availability, not incidence.

---

## F6 · INTERVENTION LAYER

**Question:** Where would a fix actually bind?

**Values (select all that apply):**

| Code | Binds via |
|---|---|
| `model` | Training, evaluation, or accuracy requirements |
| `configuration` | Settings within an existing deployment |
| `deployment rule` | A use policy or statute governing how output may be acted on |
| `procurement standard` | Contract terms required at acquisition |
| `logging duty` | A recorded, auditable trail, usually paired with an enforcement authority |
| `liability allocation` | A statute assigning responsibility between developer and deployer |
| `disclosure` | Notice to subjects, or publication of a failure analysis |
| `enforcement authority` | Granting a regulator or AG power to act |

**Coding note.** The layer selects the instrument. Most findings do not resolve
to legislation, and recording that is what makes the analysis usable by
procurement officers and agency counsel rather than only by advocates.

A record in which F6 resolves only to `model` should be re-examined: it usually
means F1 or F2 was coded too shallowly.

---

## Derived flag

**`model_performed_as_designed`** — boolean. True where no component
malfunctioned and the harm occurred anyway.

This is not a coded judgment; it follows from F4. It is recorded separately
because the distribution of this flag across the dataset is the scheme's
central empirical claim.

---

## Citation

Cite as: Tolera, H. (2026). *The Reach Failure Codebook*, v1.0. Eve's Law. Licensed CC BY 4.0. Attribution
required. See `CITATION.cff`.
