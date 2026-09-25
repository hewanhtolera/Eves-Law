# RF-001 · Isaacs

**Coded** 2026-09-25 · **Codebook** v1.0 · **Source tier** 2 (sworn testimony)
· **Status** provisional — records request filed, see `requests/RF-001.md`

---

## Fact block

Facts only. No field is coded from this section's framing.

- Subject: Lindsey Brooke Isaacs, 23, of Palm Coast, Florida.
- System: Flock Safety automated license plate reader (ALPR) network.
- Developer: Flock Safety. Deployer: Florida investigating agency.
- Underlying incident: fatal collision on Interstate 4, Volusia County,
  4 October 2025. Three people killed.
- Investigators searching for a Dodge Durango queried the ALPR network.
- One camera recorded Isaacs' black 2025 Dodge Durango travelling eastbound
  near the Seminole–Volusia county line at 9:51 p.m., approximately three miles
  west of the crash site.
- Isaacs' vehicle had no collision damage. She held a receipt placing her
  elsewhere. A discrepancy in vehicle description was reported.
- Isaacs was arrested in April 2026 on eight felony counts, including three
  counts of vehicular homicide.
- She was held 13 days, part of it in solitary confinement.
- All charges were dropped. A different driver was charged.
- Isaacs testified before the U.S. Senate Judiciary Subcommittee on Crime and
  Counterterrorism on 23 September 2026.
- In correspondence to the subcommittee, Flock stated that it relies on its
  clients, rather than the company, to police system usage.
- Four ALPR manufacturers were invited to testify. All declined.

## Coding

### F1 · Position — `retrieve` + `flag`

The network matched a query against stored reads and surfaced a result. The
read itself appears to have been accurate. No decision was produced by the
system.

Coding this `retrieve` rather than `decide` is load-bearing. An analysis that
treats the camera as the decision-maker cannot explain this case, because the
camera was correct.

### F2 · Discretion — `expanded`

Applying the F2 test: the arrest would not have survived review on the non-AI
evidence alone. The available physical evidence was disconfirming — no
collision damage, a receipt placing the subject elsewhere, a reported vehicle
description discrepancy.

The hit did not substitute for human judgment. It supplied the authority to
proceed against what judgment could observe directly.

### F3 · Stakes — `irreversible` · `third party` · `unaware`

**Reversibility.** Thirteen days of incarceration, part in solitary, and three
counts of vehicular homicide entered on a public record. Dismissal restores
none of it.

**Bearer.** Isaacs was not the system's user, customer, or subscriber. She had
no relationship with the deploying agency.

**Awareness.** No notice that the network was operating on her; no mechanism by
which she could have contested a read before it became an arrest.

### F4 · Failure mode — `inference chain` + `absence`

**`inference chain`.** A true observation — a similar vehicle, three miles
away, near the time — was converted into the identification of a person. Each
step was individually defensible. The chain was not. No component
malfunctioned.

**`absence`.** Nothing in the deployment required independent corroboration
before an arrest predicated on a plate hit, and nothing recorded the reasoning
between the hit and the charging decision.

*Threshold check.* (a) Corroboration requirements and query audit logging are
standard, available features of records systems in law enforcement use.
(b) Their cost is negligible against thirteen days of wrongful incarceration
and eight felony charges. (c) Neither was in force. Basis for (a) and (b)
requires tier 1 confirmation; see request §4 and §6.

### F5 · Reach failure — `not a state actor` + `immunity` + `no defect`

Responsibility distributes across four parties. Liability attaches to none.

- **Vendor oversight.** Flock's correspondence to the subcommittee states the
  company relies on clients to police system usage. The company directs
  responsibility to the agency.
- **`immunity`.** Qualified immunity shields individual officers absent clearly
  established law. No clearly established law governs ALPR corroboration.
- **`not a state actor`.** Flock is a private company, placing it outside the
  ordinary public-law remedy against the state.
- **`no defect`.** The system performed to specification. A product liability
  claim fails at the defect element.

Dropped charges create no remedy of their own. Diffusion of responsibility is
not incidental to this deployment pattern; it is its structural outcome.

### F6 · Intervention layer — `deployment rule` + `logging duty` + `procurement standard`

Not `model`. The model was accurate, so every remedy aimed at detection quality
misses this case.

- **`deployment rule`.** Independent corroboration required before an arrest
  predicated on an ALPR hit. This is the remedy Isaacs named in testimony.
- **`logging duty`.** The hit-to-charge chain recorded and auditable, so that
  "independent judgment was exercised" becomes a testable claim rather than an
  assertion. Pairs with an enforcement authority.
- **`procurement standard`.** No agency acquires network access without both of
  the above as contract terms. Available today, to purchasing officers, with no
  legislation required.

### Derived

`model_performed_as_designed` = **true**

---

## Remedy map

| Finding | Binds at | Instrument | Who can act |
|---|---|---|---|
| No corroboration required before arrest | Deployment | Use policy, state statute | Agency head, legislature |
| Hit-to-charge reasoning unlogged | Audit | Regulation + AG enforcement | State AG, regulator |
| Vendor disclaims usage oversight | Contract | Procurement standard | State and county purchasing |
| No party bears liability | Doctrine | Liability allocation statute | Legislature |
| Subject unaware, cannot contest | Process | Notice and challenge right | Legislature |

---

## Open questions

Fields that would change on tier 1 documents:

- Match confidence returned by the query, and whether a confidence figure was
  presented to investigators. Bears on F2.
- Whether the agency's written ALPR use policy contained any corroboration
  requirement on the arrest date. Bears on F4 `absence` and on F5.
- Whether vendor guidance recommended corroboration and the agency overrode it.
  Would move responsibility between developer and deployer in F5.
- The vehicle description discrepancy: its nature and whether it was recorded
  before arrest. Bears on F2.

## Not claimed

- No allegation that the camera malfunctioned or misread.
- No fault assigned to any individual officer, prosecutor, or employee.
- No legal conclusion as to liability in any actual or potential proceeding.
- Coded from testimony and reporting, not from the case file. Every field above
  is superseded by documents obtained under `requests/RF-001.md`.

## Sources

Sworn testimony before the U.S. Senate Judiciary Subcommittee on Crime and
Counterterrorism, 23 September 2026, and contemporaneous reporting of that
hearing by multiple independent outlets. Full source list to be appended at
tier 1 upgrade.
