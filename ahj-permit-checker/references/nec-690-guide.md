# NEC 690 Reference Guide — Solar PV Systems

This reference covers the most commonly cited NEC 690 sections in commercial
and C&I solar permit reviews. Cross-reference against the NEC edition adopted
by the target AHJ. The 2017, 2020, and 2023 editions have material differences
— do not assume the latest edition applies.

---

## Critical Edition Differences

| Topic | NEC 2017 | NEC 2020 | NEC 2023 |
|---|---|---|---|
| Rapid Shutdown | Module-level required for buildings | Module-level + array boundary | Module-level; SyRS updated |
| Ground fault | 690.5 | 690.5 (minor clarification) | 690.5 (clarification on monitoring) |
| Conductor sizing | 690.8 | 690.8 (125% retained) | 690.8 (same) |
| Backfeed/120% rule | 705.12(B) | 705.12(B) | 705.12(B)(2)(3)(b) — updated |
| Disconnecting means | 690.13 / 690.15 | 690.13 / 690.15 | 690.13 updated labeling |

When an AHJ has adopted a specific edition, flag any findings that differ
across editions — the inspector may interpret based on the adopted code
even if the design was drawn to a different edition.

---

## 690.7 — Maximum Voltage

**The rule:** The maximum PV system voltage must not exceed the ratings of
the equipment. For systems over 1,000V, additional requirements apply.

**Calculation:** Voc at standard test conditions × temperature correction factor
for the lowest expected ambient temperature at the site.

**Temperature correction:** Use NEC Table 690.7(A) or the module manufacturer's
temperature coefficient (Pmax, Voc) — whichever is more conservative.

**Common failure pattern:** Design uses STC Voc without temperature correction.
In cold climates (Colorado, New England, high-elevation California), corrected
Voc can exceed inverter maximum input voltage — silent design error, immediate
rejection when caught by plan check.

**What to check in the package:** SLD should show corrected Voc calculation
at the string level. If it shows only STC Voc, flag it.

---

## 690.8 — Circuit Sizing and Current

**The rule:** PV source circuit conductors must be sized at 125% of the
short-circuit current (Isc) of the PV modules.

**Formula:** Conductor ampacity ≥ 1.25 × Isc (per string)

**Additional derating:** If conductors are installed in conduit exposed to
sunlight on a rooftop, apply temperature and conduit fill derating per
NEC 310 tables. Rooftop conduit in direct sun can reach 60°C+.

**Common failure pattern:** Wire sized to STC Isc without the 125% factor,
or without rooftop temperature derating. Results in undersized conductors
that fail ampacity at plan check.

---

## 690.12 — Rapid Shutdown

**The rule (2017+):** PV systems installed on buildings must include a
rapid shutdown function that reduces conductors within the array boundary
to ≤30V within 30 seconds of initiating shutdown (for conductors more than
1 foot from the array) and ≤80V within 30 seconds at the array (2020+).

**What this means in practice:** Module-level power electronics (MLPEs —
microinverters or DC optimizers) with a system rapid shutdown initiator
(SRSS) are the standard compliance path for rooftop systems.

**Common failure pattern:**
- No RSSD (rapid shutdown system device) shown on SLD
- RSSD shown but not labeled correctly on the plans per 690.56
- System designed with string inverter only, no MLPE, on a building-mounted
  array — requires a separate RSSS solution
- Plans drawn to 2017 NEC but AHJ has adopted 2020 — the array-level
  requirement is different

**Label requirement (690.56):** A label must be placed at the rapid shutdown
initiation device (typically the AC disconnect or inverter disconnect) stating:
"PHOTOVOLTAIC SYSTEM EQUIPPED WITH RAPID SHUTDOWN"
along with instructions for initiating shutdown.

---

## 705.12 — Point of Connection / Backfeed Rule

**The rule:** For load-side connections, the sum of the overcurrent protective
device (OCPD) rating for the PV system backfeed breaker plus all other OCPD
ratings on the busbar must not exceed 120% of the busbar rating.

**Formula:** Backfeed breaker ≤ (busbar rating × 1.20) − main breaker rating

**Example:** 200A busbar, 200A main = maximum backfeed breaker of 40A
(200 × 1.2 = 240; 240 − 200 = 40A)

**Common failure pattern:** Package shows 200A main on a 200A busbar with
a 60A or larger backfeed breaker. Immediately flagged at plan check.

**Alternative compliance paths:**
- Supply-side connection (line-side tap before the main breaker) — no 120%
  limitation, but requires utility coordination and specific equipment ratings
- Panel replacement with higher busbar rating
- Center-fed busbar configuration (allows different calculation)

---

## 690.13 / 690.15 — Disconnecting Means

**690.13:** Each PV system must have a disconnecting means to disconnect
the PV system from all other conductors. Must be in a readily accessible
location. Must be labeled.

**690.15:** All conductors must be capable of being disconnected from all
sources of supply.

**Common failure pattern:**
- AC disconnect location not shown on site plan
- No DC disconnect shown between array and inverter (required if inverter
  does not have integral DC disconnect)
- Disconnect located in a locked room or non-accessible location
- Label missing or non-compliant text

---

## 690.47 — Grounding

**The rule:** Equipment grounding conductors (EGC) must be sized per NEC
Table 250.122. System grounding requirements depend on whether the system
is grounded or ungrounded (most modern string inverters are ungrounded
with transformer-less topology).

**Common failure pattern:**
- EGC sizing not shown on SLD
- Grounding electrode conductor (GEC) not shown connecting to building's
  grounding electrode system
- Package does not address equipment bonding for metal racking system

---

## Labeling Quick Reference

Required labels at minimum for commercial PV systems:

| Location | Required Label Text |
|---|---|
| Utility meter | SOLAR ELECTRIC SYSTEM CONNECTED |
| AC disconnect | PHOTOVOLTAIC SYSTEM DISCONNECT |
| Rapid shutdown device | PHOTOVOLTAIC SYSTEM EQUIPPED WITH RAPID SHUTDOWN + instructions |
| DC conduit | PHOTOVOLTAIC SYSTEM — may be energized from multiple sources |
| Combiner box | CAUTION — PHOTOVOLTAIC SOURCE CIRCUITS |
| Service panel backfeed breaker | SOLAR (or equivalent — must identify the breaker) |

AHJs often add local labeling requirements. Check ahj-profiles.md for
jurisdiction-specific additions.
