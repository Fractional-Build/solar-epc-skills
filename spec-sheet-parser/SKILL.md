---
name: spec-sheet-parser
description: >
  Extracts structured technical data from Solar PV equipment datasheets and
  specification documents, then performs compatibility and design validation
  checks. Use this skill whenever a user provides or references a module
  datasheet, inverter spec sheet, racking spec, combiner box datasheet,
  transformer datasheet, or any equipment cut sheet. Also trigger when a user
  asks to compare equipment options, check string sizing, verify inverter
  compatibility, validate DC/AC ratio, check clamp compatibility with a
  module frame, or confirm that equipment specifications meet design
  requirements. Trigger for phrases like "check these specs", "does this
  inverter work with these panels", "help me compare these two modules",
  or "pull the key numbers from this datasheet".
---

# Spec Sheet Parser

Every solar design depends on accurate equipment data. The manual process —
open PDF, find the right table, copy the number, paste it into a spreadsheet,
repeat 40 times across 6 documents — takes hours and produces transcription
errors. This skill does the extraction and the validation in one pass.

## What You're Working With

The user will provide one or more of the following:

- Equipment datasheets (PDF, image, or pasted text)
- A list of equipment for a specific project (module model, inverter model,
  racking model)
- A design scenario they want validated (string configuration, DC/AC ratio,
  clamp size, conductor sizing)

If the user provides a model number without a datasheet, attempt to work from
known specifications, but flag clearly that the data is from training knowledge
and should be verified against the current manufacturer datasheet before use
in a permit package or procurement order.

## Step 1 — Identify Equipment Type and Extraction Target

Determine what type of equipment is being parsed and what the user needs:

**If extraction only:** User wants structured data pulled from the datasheet.
Go to Step 2.

**If compatibility check:** User wants to know if two or more pieces of
equipment work together. Complete Step 2 for all equipment, then proceed
to Step 3.

**If design validation:** User wants to confirm a specific design decision
(string length, DC/AC ratio, conductor sizing). Complete Step 2, then
proceed to Step 4.

## Step 2 — Extract Structured Data

Extract the following parameters based on equipment type. If a parameter
is not present in the datasheet, mark it as NOT FOUND rather than leaving
it blank or guessing.

### PV Module

| Parameter | Symbol | Unit | Value |
|---|---|---|---|
| Maximum Power | Pmax | W | |
| Open Circuit Voltage | Voc | V | |
| Short Circuit Current | Isc | A | |
| Maximum Power Voltage | Vmp | V | |
| Maximum Power Current | Imp | A | |
| Module Efficiency | η | % | |
| Temperature Coefficient (Pmax) | γPmax | %/°C | |
| Temperature Coefficient (Voc) | βVoc | %/°C or mV/°C | |
| Temperature Coefficient (Isc) | αIsc | %/°C | |
| NOCT | NOCT | °C | |
| Maximum System Voltage | Vsys max | V | |
| Maximum Series Fuse Rating | OCPD max | A | |
| Operating Temperature Range | T_op | °C | |
| Dimensions (L × W × H) | — | mm | |
| Weight | — | kg | |
| Frame type | — | — | |
| Frame height (for clamp selection) | — | mm | |
| Connector type | — | — | |
| Certifications / Listings | — | — | |
| Bifacial / Monofacial | — | — | |
| Half-cut / Full-cell | — | — | |

### String Inverter

| Parameter | Symbol | Unit | Value |
|---|---|---|---|
| Rated AC Output Power | Pac | W or kW | |
| Maximum AC Output Current | Iac max | A | |
| AC Output Voltage | Vac | V | |
| AC Output Frequency | f | Hz | |
| Maximum DC Input Power | Pdc max | W or kW | |
| Maximum DC Input Voltage | Vdc max | V | |
| MPPT Voltage Range (low) | Vmppt min | V | |
| MPPT Voltage Range (high) | Vmppt max | V | |
| Maximum DC Input Current (per MPPT) | Idc max | A | |
| Maximum Short Circuit Current (per MPPT) | Isc max | A | |
| Number of MPP Trackers | — | — | |
| Number of DC Inputs per MPPT | — | — | |
| Maximum Efficiency | η max | % | |
| CEC Weighted Efficiency | η CEC | % | |
| Night-time Power Consumption | — | W | |
| Operating Temperature Range | T_op | °C | |
| Protection Rating | IP | — | |
| Dimensions (H × W × D) | — | mm | |
| Weight | — | kg | |
| Certifications / Listings | — | — | |
| Rapid Shutdown Compliant | — | Yes/No | |
| Transformer-less topology | — | Yes/No | |
| Communication protocols | — | — | |

### Central / Utility-Scale Inverter

Same as string inverter plus:

| Parameter | Symbol | Unit | Value |
|---|---|---|---|
| Nominal DC Input Voltage | Vdc nom | V | |
| Number of String Inputs | — | — | |
| Internal combiner | — | Yes/No | |
| Cooling type | — | — | |
| Footprint | — | m² | |
| Pad mount / skid requirements | — | — | |

### Racking System

| Parameter | Unit | Value |
|---|---|---|
| Compatible roof types | — | |
| Maximum module frame height range | mm | |
| Maximum module frame width (for end clamps) | mm | |
| Span between rails | mm | |
| Maximum snow load | psf | |
| Maximum wind speed (design) | mph | |
| Rail material | — | |
| Rail finish | — | |
| Grounding method | — | |
| Certifications / Listings | — | |
| Compatible module connector types (for flush/grip mounts) | — | |

## Step 3 — Compatibility Check

If two or more pieces of equipment have been parsed, run the following checks:

### Module + Inverter Compatibility

**Voltage check (critical):**
```
Voc_corrected = Voc_stc × (1 + βVoc × (T_min - 25))

Where T_min is the lowest expected ambient temperature at the site.
If T_min is not provided, use -10°C as a conservative default and flag it.

Check: Voc_corrected × (modules per string) ≤ Vdc_max of inverter
```

Show the calculation explicitly. Do not just state pass/fail.

**MPPT range check:**
```
Vmp at operating temp = Vmp_stc × (1 + γPmax × (T_operating - 25))
(approximate — uses Pmax coefficient as proxy for Vmp coefficient)

Check: Vmppt_min ≤ Vmp_per_string ≤ Vmppt_max
```

**Current check:**
```
Isc per string = Isc_stc × 1.25 (NEC 690.8 factor)
Check: Isc per string ≤ Isc_max per MPPT input of inverter
```

**DC/AC ratio:**
```
DC/AC ratio = (Pmax per module × modules total) / Pac_inverter

Acceptable range for C&I systems: 1.1 to 1.4
Flag if outside this range — does not mean it's wrong, but warrants review.
```

### Module + Racking Compatibility

**Frame height check:**
```
Check: Module frame height falls within racking clamp range
If NOT FOUND on either datasheet, flag explicitly — this must be confirmed
before procurement. Wrong clamp selection is a common rework item.
```

**Weight check:**
```
If roof structural calculations are in scope, flag the module weight for
use in dead load calculations.
```

## Step 4 — Design Validation

If the user provides a specific design scenario, validate it:

### String Sizing Validation

Inputs needed: module model, inverter model, number of modules per string,
number of strings, site location (for temperature correction).

Run all checks from Step 3 for the specific string configuration.
Show every calculation step. Flag any value that is within 5% of a limit —
not just values that exceed it. Being close to a limit is itself a risk.

### Conductor Sizing Validation

```
Minimum conductor ampacity = Isc × 1.25 (NEC 690.8)

Apply derating for:
- Ambient temperature (NEC Table 310.15(B)(2) or 310.15(B)(3))
- Conduit fill (NEC Table C.1 or C.8 depending on conduit type)
- Rooftop adder: if conduit mounted on rooftop in direct sun, add 30°C
  to ambient temperature before applying temperature derating factor

Show the final derated ampacity and confirm it meets or exceeds the
minimum required ampacity.
```

## Step 5 — Produce the Output

Structure output based on what was requested:

### For extraction only:
Present the extracted data in a clean table.
Flag any NOT FOUND parameters.
Note: "Verify all values against current manufacturer datasheet before
use in permit documents or procurement orders."

### For compatibility check:
Present extracted data tables for all equipment.
Then present each compatibility check with full calculation shown.
Verdict per check: PASS / FAIL / REVIEW (within 5% of limit) / CANNOT VERIFY.

### For design validation:
Present the validation calculations in full.
Final verdict: DESIGN VALIDATED / ISSUES FOUND / ADDITIONAL DATA NEEDED.

## Important Constraints

Manufacturer datasheets are version-controlled documents. Module and inverter
specifications change between production lots, firmware versions, and
datasheet revisions. Always flag that values extracted from a datasheet
should be matched to the specific product revision in use on the project.

Do not make procurement recommendations. Flag compatibility issues and
present the data — the engineering decision belongs to the licensed engineer
of record.
