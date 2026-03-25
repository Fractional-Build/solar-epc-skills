# AHJ Profiles — Known Jurisdiction Requirements and Quirks

This file captures known requirements, local amendments, and common rejection
patterns for specific jurisdictions. It is not exhaustive. When a jurisdiction
is not listed, work from the standard checklist in SKILL.md and flag the
review as UNVERIFIED.

Entries are organized by state, then by jurisdiction.

---

## Table of Contents
- California — Southern
- California — Northern / Bay Area
- California — Central Valley
- Texas
- Arizona
- Nevada
- Colorado
- New Jersey / Mid-Atlantic
- Massachusetts / New England

---

## California — Southern

### Los Angeles City (LADBS)
- **NEC edition:** 2020 NEC with local amendments
- **PE stamp required:** Yes, for all commercial systems. Wet stamp required —
  digital stamps not accepted as of last verified update.
- **Fire setbacks:** 4-foot pathways (not 3-foot). Many packages fail here.
- **Three-line diagram:** Required for all commercial systems over 10 kW AC.
- **Interconnection:** SCE or LADWP pre-approval required before permit issuance.
  LADWP has its own separate permit process — do not conflate with LADBS permit.
- **Forms:** Use LADBS current forms from their portal. They update these without
  announcement. Always download fresh.
- **Known rejection triggers:**
  - Using CalFire setbacks instead of LAFD setbacks
  - Missing three-line diagram (not same as SLD)
  - PE stamp from engineer not licensed in California

### Los Angeles County (Unincorporated)
- **Different from LA City.** Many contractors confuse these.
- Unincorporated areas use County Building & Safety, not LADBS.
- NEC 2020. PE stamp required for commercial.
- Fire setbacks: standard IFC 3-foot pathways apply (unlike LA City)
- Interconnection: SCE territory — WDAT or NEM agreement required before
  permit in many unincorporated areas.

### Riverside County
- Strong history of rejecting packages for missing or outdated structural
  calculations. PE stamp required; stamp must reference specific wind/seismic
  zone for Riverside County.
- High wind load area — many racking manufacturers' standard calcs don't cover
  the required exposure category. Verify.

### San Diego City (DSD)
- Online submittal via Permits.sd.gov. Paper submittals not accepted for most
  commercial projects.
- Title 24 compliance mandatory. Often the most overlooked document in packages
  submitted from out-of-state firms.
- Fire marshal review happens in parallel with building — do not assume one
  approval covers both.

---

## California — Northern / Bay Area

### San Francisco (DBI)
- Among the most complex permitting environments in the US.
- Requires separate review by SF Fire Department and SF Department of Building
  Inspection — they do not coordinate automatically.
- Historical buildings: additional review layer. Flag any project in SF
  pre-1940 construction.
- NEC 2020. Rapid shutdown required and enforced strictly.

### San Jose (City of San Jose)
- Fire marshal reviews are independent from building department.
  Submit to both simultaneously or expect delays.
- 4-foot pathways required in many commercial zones.
- Structural: PE wet stamp required.

### Oakland / Alameda County
- Local amendments include 3-foot setbacks from all skylights and ventilation
  openings, not just smoke vents.
- Permit portal frequently backlogged — plan for 6-8 week review cycles on
  first submission.

---

## California — Central Valley

### Fresno City / County
- 36" eave setback — more restrictive than standard IFC 18".
- Some inspectors require 36" setback from ALL roof edges, not just eave.
  Confirm with the specific plan checker before resubmitting.
- NEC 2017 still applies in some unincorporated Fresno County areas.
  Verify before designing to 2020.

### Sacramento City / County
- Updated fire requirements in 2023. Common issue: packages prepared using
  2021 Sacramento County fire guidelines.
- Commercial: Title 24 required. Often missed.
- Known for slow turnaround on electrical plan review — build 8-week buffer.

### Bakersfield (City of Bakersfield)
- Relatively straightforward process compared to Bay Area.
- NEC 2017. PE stamp required for commercial.
- Interconnection: PG&E in most areas — confirm WDAT or NEM timeline aligns
  with permit timeline.

---

## Texas

### ERCOT Territory (general)
- Texas does not have statewide building codes — AHJ requirements vary
  dramatically by municipality.
- Many rural areas: no permit required. Confirm before assuming permit is needed.
- Urban areas (Houston, Dallas, Austin, San Antonio): each municipality has
  independent requirements. Do not transfer a package from one Texas city
  to another without full re-review.

### Houston (City of Houston)
- Houston has no zoning code but does require electrical permits.
- NEC 2020 for electrical.
- No fire setback ordinance equivalent to IFC for solar — but fire marshal
  can request review for commercial occupancies.
- Structural: engineer letter or PE stamp required for commercial.

### Austin (City of Austin)
- NEC 2020. Active enforcement of rapid shutdown requirements.
- Austin Energy is the utility — has its own interconnection process that
  runs independently of permit. Align timelines.
- Environmental review may be required for ground-mount systems in
  Austin's ETJ (extra-territorial jurisdiction).

---

## Arizona

### Phoenix (City of Phoenix)
- High heat environment — requires documentation of thermal expansion for
  conduit runs over 50 feet.
- Some inspectors ask for heat derate calculations on conductor sizing even
  when not explicitly required by code. Include proactively.
- NEC 2017 with local amendments. Some Phoenix suburban jurisdictions
  (Mesa, Tempe, Scottsdale) have adopted 2020 — verify.

### Tucson (City of Tucson / Pima County)
- Fire department pre-approval required before building permit is issued.
  This is a sequential process — add 2-3 weeks to schedule.
- Pima County (unincorporated) has different process from City of Tucson.

---

## Nevada

### Clark County / Las Vegas
- Updated commercial solar requirements in late 2023.
- 3D rendering or isometric view of setbacks now requested by fire for
  commercial systems over 100 kW. Not always formally required but
  frequently requested — include proactively.
- NEC 2020.

---

## Colorado

### Denver / Jefferson County
- Cold climate — temperature correction on Voc is critical and frequently
  flagged. Minimum design temperature: -20°F in most Front Range jurisdictions.
- Snow load calculations required for all rooftop systems. Many packages
  miss this.
- NEC 2020. Rapid shutdown enforced at array level.

---

## New Jersey / Mid-Atlantic

### New Jersey (general)
- NEC 2017 (some municipalities), NEC 2020 (others). Confirm before designing.
- Structural: PE stamp required for all commercial systems.
- Fire: some municipalities require fire department walkthrough before
  certificate of occupancy — not just plan approval.
- Interconnection: JCP&L, PSE&G, and ACE are the main utilities. Each has
  different interconnection timelines and form requirements.

---

## Massachusetts / New England

### Massachusetts (general)
- NEC 2020 state-wide since 2023.
- 3-foot hip and valley setbacks strictly enforced even on systems that might
  qualify for exception under standard IFC.
- All commercial systems: electrical permit plus sign-off from licensed
  electrician required.
- Interconnection: Eversource or National Grid. NEM 3.0 replaced net metering
  — confirm tariff structure affects project economics, which may affect
  permit scope.

---

## Notes on Using This File

If a jurisdiction is not listed here, do not assume its requirements match
a listed similar jurisdiction. The range of variation even within a single
county can be significant.

When in doubt: call the building department. Ask specifically:
1. Which edition of NEC have you adopted?
2. Do you require a three-line diagram in addition to the SLD?
3. What are your current fire setback requirements for commercial rooftop solar?
4. Do you require a PE wet stamp, or is a digital stamp acceptable?

A 10-minute call to the building department prevents a 4-week rejection cycle.
