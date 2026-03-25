---
name: ahj-permit-checker
description: >
  Reviews a completed Solar EPC permit package against the current requirements
  of the target Authority Having Jurisdiction (AHJ) before submission. Use this
  skill whenever a user mentions permit review, AHJ submission, plan check,
  permit package, permit rejection, building department, fire marshal setbacks,
  structural calculations, electrical plan review, or anything related to
  preparing or checking a solar permit application. Also trigger when a user
  asks "will this pass plan check", "is my permit package ready", or "what's
  missing from my permit set". This skill prevents the single most avoidable
  delay in the Solar EPC pre-construction pipeline.
---

# AHJ Permit Checker

A permit rejection resets the municipal review clock — typically 2 to 6 weeks.
For a commercial solar project, that delay cascades through equipment staging,
subcontractor scheduling, and revenue recognition. The root cause of most
rejections is not a bad design. It is an outdated form, a missed setback rule,
or a code update the team didn't know about.

This skill reviews a permit package before it goes out the door.

## What You're Working With

The user will provide one or more of the following:

- A completed permit package (PDF or description of contents)
- The target AHJ (city, county, or utility district name)
- The system type (rooftop commercial, ground-mount C&I, carport, BESS, hybrid)
- The applicable codes (NEC edition adopted locally, IBC/CBC year, local amendments)

If the AHJ is not specified, ask for it. The check is meaningless without it.
If the system type is not specified, infer it from the package contents.

## Step 1 — Identify the AHJ Profile

Before reviewing the package, establish what this AHJ actually requires.
Read `references/ahj-profiles.md` for known jurisdiction quirks, common
rejection patterns, and local amendment flags by region.

If the AHJ is not in the reference file, work from first principles using
the standard checklist in Step 2, and flag that the AHJ is unverified — the
user should confirm requirements directly with the building department.

## Step 2 — Run the Full Checklist

Work through every section below systematically. Do not skip sections because
they seem unlikely to apply. The rejections that cost the most are always
the ones that seemed unlikely.

### A. Document Completeness

Verify the package contains all required documents:

- [ ] Cover sheet with project address, APN, scope of work, system size (kWdc / kWac)
- [ ] Site plan showing property boundaries, setbacks, and system location
- [ ] Roof plan (for rooftop) or site layout (for ground-mount) with dimensions
- [ ] Single-line electrical diagram (SLD)
- [ ] Three-line diagram (if required by this AHJ — see ahj-profiles.md)
- [ ] Structural calculations or stamped letter (PE stamp requirements vary by AHJ)
- [ ] Equipment cut sheets: modules, inverters, racking, disconnects, meters
- [ ] Load calculation worksheet (for interconnection to service panel)
- [ ] Interconnection application or proof of utility pre-approval (if required)
- [ ] Title 24 / energy compliance forms (California jurisdictions)
- [ ] Fire department access plan (setbacks, ridge vents, hip/valley clearances)
- [ ] Grounding and bonding diagram
- [ ] Hazardous materials / battery energy storage forms (if BESS included)

Flag every missing document. Do not proceed assuming it will be added later.

### B. Electrical Plan Review

Check the SLD against NEC requirements. Reference `references/nec-690-guide.md`
for the specific code sections relevant to each check below.

- [ ] String configuration: verify Voc (at lowest recorded temp) does not exceed
      inverter maximum input voltage. Apply temperature correction per NEC 690.7.
- [ ] Conductor sizing: verify ampacity meets NEC 690.8 (125% of Isc per string,
      continuous load factor applied)
- [ ] OCPD ratings match conductor ampacity and equipment ratings
- [ ] Rapid shutdown compliance labeled and shown (NEC 690.12 — check which
      edition the AHJ has adopted; requirements differ significantly)
- [ ] AC disconnect location and labeling meets NEC 690.13 / 705.22
- [ ] Backfeed breaker labeled and does not exceed 120% busbar rule (NEC 705.12)
      OR load-side connection shown correctly
- [ ] Ground fault protection indicated on SLD
- [ ] Anti-islanding / interconnection protection method shown
- [ ] Meter socket and PTO meter location consistent with utility requirements
- [ ] All equipment listed as UL or equivalent — flag any non-listed equipment

### C. Structural Review

- [ ] Racking system matches roof type (composition shingle, TPO, standing seam,
      ballasted, ground-mount — each has different attachment requirements)
- [ ] Attachment spacing consistent with structural calculations
- [ ] PE stamp present if required (check ahj-profiles.md — many AHJs require
      wet stamp for systems over a threshold kW or for commercial occupancies)
- [ ] Roof age and condition noted if required (some AHJs reject permits on roofs
      over 10–15 years without documentation)
- [ ] Snow load, wind load, and seismic zone called out correctly for jurisdiction
- [ ] Ballast calculations provided for flat-roof ballasted systems
- [ ] Ground-mount: footing design, pile specifications, embedment depth shown

### D. Fire / Life Safety

This is the most frequently updated section. AHJs adopt fire code amendments
on different schedules. Read `references/fire-setback-rules.md` before
completing this section.

- [ ] Ridge setback shown (typically 18" from ridge, but varies)
- [ ] Hip and valley setbacks shown
- [ ] Eave setback shown
- [ ] 3-foot pathways provided per fire department requirements
- [ ] Smoke ventilation zones clear (check local fire code — some AHJs require
      specific clear areas over structural ridge lines)
- [ ] BESS fire separation distances met (if applicable)
- [ ] Address and emergency shutoff location visible on site plan

### E. Labeling Requirements

Labeling failures are the most common cause of rejected resubmittals.
The design can be perfect and the package still bounces if labels are wrong.

- [ ] "PHOTOVOLTAIC SYSTEM CONNECTED" label shown at utility meter
- [ ] "SOLAR ELECTRIC SYSTEM" label shown at AC disconnect
- [ ] Rapid shutdown initiation device labeled per NEC 690.56
- [ ] Conduit and conductor labels shown on SLD (voltage, current, wire size,
      conduit type)
- [ ] BESS labels if applicable (chemistry type, capacity, emergency contacts)
- [ ] Inverter nameplate data matches cut sheet shown in package

### F. Forms and Signatures

- [ ] All forms use the current version — check date on form against
      ahj-profiles.md. Outdated forms are rejected immediately at counter.
- [ ] Contractor license number present and matches license type required
      (C-10 electrical, C-46 solar — requirements vary by state and AHJ)
- [ ] Owner signature on owner-builder forms if applicable
- [ ] PE / structural engineer stamp and signature dated within 12 months
      (some AHJs reject stale calculations)
- [ ] Wet stamp vs. digital stamp — check ahj-profiles.md for this AHJ's policy

## Step 3 — Produce the Review Report

Structure your output exactly as follows:

---

### PERMIT REVIEW REPORT
**Project:** [address or project name]
**AHJ:** [jurisdiction name]
**System Type:** [rooftop / ground-mount / carport / BESS / hybrid]
**Review Date:** [today's date]
**AHJ Profile Confidence:** [VERIFIED / UNVERIFIED — confirm with building dept]

---

#### STOP — Cannot Submit
*Items that will result in rejection. Fix before submission.*

List each issue as:
> **[Section] — [Issue]**
> Why it matters: [one sentence]
> What to fix: [specific action]

If there are no STOP items, write: *None identified.*

---

#### REVIEW — Likely to Cause Issues
*Items that may cause rejection depending on this AHJ's specific inspector.*

Same format as above.

---

#### CONFIRM — Verify Before Submission
*Items that could not be verified from the package alone.*

Same format as above.

---

#### PASSED
*Sections that reviewed clean.*

List each section name on a single line.

---

#### SUMMARY
Total STOP items: [n]
Total REVIEW items: [n]
Total CONFIRM items: [n]

**Recommendation:** [HOLD — do not submit / SUBMIT WITH CAUTION / CLEAR TO SUBMIT]

---

## Step 4 — Offer Next Steps

After delivering the report, offer:

1. To walk through any STOP item in detail and explain the fix
2. To check whether the specific NEC edition adopted by this AHJ affects
   any of the electrical findings
3. To flag if there are known pending code updates for this jurisdiction
   that could affect a future resubmittal

## Important Constraints

This review is based on the information provided and the reference data in
this skill. It does not replace a licensed engineer's review for structural
calculations, or a licensed electrician's sign-off on the electrical design.
Flag this clearly at the bottom of every report:

> *This review is an operational pre-check, not a licensed engineering review.
> All structural calculations require PE sign-off. All electrical work requires
> sign-off by a licensed electrical contractor in the applicable jurisdiction.*
