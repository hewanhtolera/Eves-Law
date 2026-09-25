# Eve's Law

**The Reach Failure Codebook and its coded case record.**

A coded dataset of AI deployment harms that existing law could not reach, and
of the regulatory instrument that would have reached each one.

**Status:** v1.0 codebook, 1 record. Active.

---

## The claim

AI harm is being regulated at the wrong layer.

The public debate is about model capability. The failures are occurring at
deployment — configuration, routing, corroboration, escalation, procurement.
This dataset records cases in which the model performed correctly and a person
was harmed anyway, and identifies, for each, the specific doctrinal element
that prevented a remedy.

Where harm concentrates at the deployment layer, the duty belongs to the
deployer, before the fact, in both directions: a failure analysis published
before deploying into concentrated power, and an auditing layer over
concentrated power where one is available and effective.

The second half of that is not a standard argument. It is recorded in the
codebook as the `absence` value in F4 — harm that occurred because no system
was watching a place where one was available and cheap. Without it, a harm
framework can only recommend restriction.

## What is here

| Path | Contents |
|---|---|
| `CODEBOOK.md` | The coding scheme. Canonical, versioned. |
| `METHOD.md` | Inclusion criteria, source tiers, coding procedure, limitations. |
| `records/` | One file per coded case. |
| `data/records.csv` | The coded rows, machine-readable. |
| `data/schema.json` | Field definitions and permitted values. |
| `requests/` | Public-records requests filed against provisional records. |
| `CHANGELOG.md` | Every change to the codebook or a published record. |

## The scheme

Six fields. Two are not present in existing AI-harm taxonomies.

- **F1 Position** — what the system's output did, structurally
- **F2 Discretion** *(novel)* — what the system did to the judgment of the person holding power
- **F3 Stakes** — reversibility, bearer, awareness
- **F4 Failure mode** — including `absence` *(novel value)*
- **F5 Reach failure** — the specific doctrinal element that fails
- **F6 Intervention layer** — where a fix would bind

Full definitions and coding rules in `CODEBOOK.md`.

## Records

| ID | Subject | System | Status |
|---|---|---|---|
| RF-001 | Isaacs | ALPR network | Provisional (tier 2) |

## How to use this

The scheme is free to use, including commercially, with attribution. If you
code cases with it, cite the codebook version you coded against so records
remain comparable. Corrections and disputed codings are welcome as issues.

## Limitations

Stated in full in `METHOD.md` §5. In short: single coder, no inter-coder
reliability established, purposive rather than random selection, U.S. law only,
and a visibility bias that cannot be corrected from public sources.

No record asserts liability or fault. Records locate where a duty is absent.

## Citation

See `CITATION.cff`. GitHub renders a citation block from it.

## License

Codebook, method, and records: CC BY 4.0. Attribution required.

## Naming

**Eve's Law** is the project. **The Reach Failure Codebook** is the instrument
inside it, and records carry `RF-` identifiers. The project name travels; the
instrument name is what a committee, a filing, or a procurement officer cites.
Keeping them separate means the analysis can be quoted by parties who would not
quote the project.
