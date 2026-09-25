# Method

**Version 1.0 · 25 September 2026**

This document states how cases enter the dataset and how they are coded. It is
published before the dataset is complete so that inclusion cannot be adjusted
after the fact to suit a finding.

---

## 1. Inclusion criteria

A case is eligible when **all** of the following hold.

1. An AI or algorithmic system was in the causal chain of a harm.
2. The harm fell on an identifiable person or a defined class.
3. Facts sufficient to code all six fields are available from a source at
   tier 1 or tier 2 (see §3).
4. The harm has occurred. Predicted, simulated, and hypothetical harms are out
   of scope.

A case is **excluded** where the only available account is the claim of one
party with no corroborating record, or where coding any field would require
inferring facts not stated in the sources.

## 2. Selection

Cases are selected purposively, not randomly. The dataset is not a sample of
AI harms and no claim about population frequency is made from it.

Selection is governed by two standing rules, adopted in advance:

**Spread rule.** No more than one third of records may share an F1 position
value or a sector. The scheme's claim is that it travels; a dataset
concentrated in one deployment type cannot support that claim.

**Disconfirmation rule.** The dataset must include cases whose coding
exonerates a developer, cases where `absence` is the primary F4 value, and
cases where the appropriate F6 layer is `model`. A scheme that returns the same
finding regardless of input is not an instrument.

Where an eligible case would violate the spread rule, it is logged in
`records/DEFERRED.md` rather than dropped, so the exclusion is visible.

## 3. Source tiers

Every record states the tier of its strongest source.

| Tier | Source |
|---|---|
| 1 | Primary documents — court filings, contracts, configuration records, logs, records-request returns |
| 2 | Sworn testimony, regulatory findings, official investigative reports |
| 3 | Contemporaneous reporting by multiple independent outlets |

Records at tier 3 are coded and published, and are marked provisional. A
records request is filed for every tier 3 record; the request is published
alongside it in `requests/`. A record is upgraded when documents return, and
the change is logged.

**No record is published on a single source.**

## 4. Coding procedure

1. Facts are extracted into the record's fact block before any field is coded.
   Field values are never assigned from a narrative summary.
2. Fields are coded in order F1 → F6. Order matters: F2 is not codable until
   F1 distinguishes the system's position from the human's action.
3. Every field value carries a sentence of evidence naming what supports it.
4. Where the sources do not settle a field, it is coded `unresolved` and the
   open question is stated. `unresolved` is a permitted value in every field.

## 5. Known limitations

Stated here rather than defended later.

- **Single coder.** All records are currently coded by one person. Inter-coder
  reliability has not been established. A second coder on a subset is required
  before any distributional claim is made from this dataset.
- **Visibility bias.** Cases that reach public reporting are not representative
  of cases that occur. The dataset over-represents harms that were eventually
  discovered, which is precisely the opposite of the `no detection` value in
  F5. This bias cannot be corrected from public sources and is not corrected
  here.
- **Jurisdictional.** F5 is coded against U.S. law. Values are not portable to
  other jurisdictions without revision.
- **No legal conclusions.** Records state where a duty appears absent. They do
  not assert liability, fault, or a conclusion in any actual or potential
  proceeding.

## 6. Corrections

Errors are corrected in place, with the change, the date, and the reason
recorded in `CHANGELOG.md`. Records are not silently revised and are not
withdrawn once published.

A finding in this dataset can be wrong. Correcting it publicly is the
difference between analysis and commentary.
