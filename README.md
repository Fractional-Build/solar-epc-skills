# solar-epc-skills

Workflow automation for Solar EPC project managers, operations directors,
and field teams who are done losing margin to paperwork.

---

## The problem this solves

A mid-market Solar EPC running 40–60 projects a year loses roughly
800–1,200 hours annually to work that should not require a human.

Chasing lien waivers for a closeout binder.
Logging into utility portals every morning to check interconnection status.
Reformatting three vendor bids that all arrived in different templates.
Calling a subcontractor superintendent at 5pm to find out how many modules
went up that day.

These are not people problems. They are systems problems.
This library automates them - not with a new platform your team needs to
learn, but with workflows that run inside the AI tools your technical
team already uses.

---

## What's included

### [ahj-permit-checker](./ahj-permit-checker)

Reviews a completed permit package against the current requirements of the
target Authority Having Jurisdiction before you submit it.

Catches the outdated form. Flags the missing three-line diagram. Identifies
the setback that doesn't match the fire marshal's latest requirement.

A rejected permit resets a 4–6 week review clock. This check takes minutes.

**Includes:** Full NEC 690 reference, jurisdiction-specific AHJ profiles
(California, Texas, Arizona, Nevada, Colorado, New Jersey, Massachusetts),
fire setback rules by region.

---

### [spec-sheet-parser](./spec-sheet-parser)

Extracts structured technical data from any equipment datasheet - module,
inverter, racking, combiner - and validates compatibility between components.

Runs the Voc temperature correction, checks the 120% busbar rule, validates
string sizing, confirms clamp compatibility with module frame height.

Every calculation shown. No black box.

---

### [rfi-writer](./rfi-writer)

Turns a field observation - a text message from a superintendent, a voice
note from the roof, a paragraph of notes - into a properly formatted,
contractually sound Request for Information.

Correct structure. Specific location reference. Quantified impact statement.
A clear question that generates a binding written response.

An undocumented field condition is an unprotected cost exposure.

---

### [vendor-bid-normalizer](./vendor-bid-normalizer)

Normalises multiple vendor quotes to the same basis before comparison.

Aligns freight terms (FOB vs. DDP). Converts units. Flags scope inclusions
and exclusions. Surfaces lead time risk. Notes tariff exposure by country
of origin.

**Includes:** Tariff reference guide covering Section 201, AD/CVD, UFLPA
exposure for modules, inverters, and racking.

Comparing a DDP quote to an FOB quote at face value is a procurement error.
This skill prevents it.

---

### [daily-report-formatter](./daily-report-formatter)

Converts unstructured field notes into a properly structured daily
construction report.

Works from a text message. Works from a voice-to-text transcript.
Works from a bullet list written in a truck at the end of the day.

Captures crew deployment, work completed with quantities, weather conditions,
delays with cause and duration, safety status, site visitors, and open items.

The daily report is the document that protects the EPC when a schedule
dispute arises six months after project completion. This skill makes sure
it gets written every day.

---

### [change-order-draft](./change-order-draft)

Produces a formal Change Order Request from a description of additional scope.

Works for owner-directed changes, unforeseen conditions, design revisions,
and regulatory requirements. Includes cost breakdown by labour, materials,
and equipment. Calculates schedule impact. Flags verbal instructions that
need to be formalised in writing before work proceeds.

The window to capture a change order is while the work is happening.
This skill closes that window in minutes.

---

## Installation

### Claude Code

```bash
# Install individual skills
npx skills add fractional-build/solar-epc-skills --skill ahj-permit-checker
npx skills add fractional-build/solar-epc-skills --skill spec-sheet-parser
npx skills add fractional-build/solar-epc-skills --skill rfi-writer
npx skills add fractional-build/solar-epc-skills --skill vendor-bid-normalizer
npx skills add fractional-build/solar-epc-skills --skill daily-report-formatter
npx skills add fractional-build/solar-epc-skills --skill change-order-draft

# Or install the full library
npx skills add fractional-build/solar-epc-skills
```

### Manual Installation

Clone the repository and copy any skill folder to your Claude skills directory:

```bash
git clone https://github.com/fractional-build/solar-epc-skills
cp -r solar-epc-skills/ahj-permit-checker ~/.claude/skills/
```

The skills are compatible with Claude Code, Cursor, Codex CLI, and any
AI coding environment that supports the SKILL.md standard.

---

## How this gets used

These workflows are self-contained. A technical team member can install
them and begin using them immediately.

They are also a starting point. The skills as published cover the standard
workflow. A specific EPC operation has its own document templates, its own
subcontractor communication patterns, its own project management stack.

Configuring these workflows for a specific operation - connecting them to
Procore, to a specific PM system, to the way a particular team works -
is what we do at Fractional Build.

If you want this running in your business rather than sitting in a GitHub
repository, that conversation starts here:

**[fractional.build](https://fractional.build)** - 30-minute scope call,
no pitch, written build plan within 24 hours.

---

## Contributing

Industry expertise is the thing that makes these skills better.

If you are a Solar EPC professional and you see something wrong, outdated,
or missing - a jurisdiction profile that needs updating, a code section
that has changed, a field scenario that this library doesn't handle -
open an issue or submit a pull request.

The AHJ profiles and tariff reference in particular benefit from people
who work in specific markets every day.

---

## License

MIT License. Use freely, modify freely, deploy in your operation.
The skills are yours. The implementation expertise is ours.

---

*Built by [Fractional Build](https://fractional.build) - AI-powered
operations infrastructure for Solar EPC firms.*
