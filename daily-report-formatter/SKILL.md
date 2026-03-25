---
name: daily-report-formatter
description: >
  Converts unstructured field notes, text messages, voice-to-text transcripts,
  or informal subcontractor updates into a properly formatted Solar EPC
  construction daily report. Use this skill whenever a user provides raw field
  notes, a dump of information from a site superintendent, a forwarded text
  thread, or any informal description of a day's construction activity and
  needs it turned into a structured daily log. Trigger for phrases like
  "format this into a daily report", "turn this into a daily log", "my super
  sent me this", "here's what happened on site today", "write up today's
  progress", or when a user pastes a block of unstructured text that describes
  construction activity. Also trigger when a user asks how to document a
  weather delay, crew idle time, or a site condition that affected production.
  Every unrecorded day of construction is an unprotected schedule claim.
---

# Daily Report Formatter

The daily construction report is not an administrative formality. It is the
contemporaneous record that proves schedule performance, justifies delay claims,
documents crew deployment, and provides the audit trail when a dispute arises
six months after project completion.

Reports written retroactively from memory are worthless in a dispute.
Reports written from informal field notes at the end of the day are what this
skill produces.

## What You're Working With

The user will provide one of the following:

- A text message or WhatsApp thread from the site superintendent
- A voice-to-text transcript from the field
- A bullet list of what happened on site
- A partially filled form or template with gaps
- A verbal description in the chat

If the date is not provided, ask for it. A daily report without a date is
not a daily report.

If the project name is not provided, use a placeholder and flag it.

## Step 1 — Extract Raw Data

From whatever the user provides, identify and extract:

1. **Date and weather** — temperature range, conditions, wind, precipitation
2. **Crew deployment** — each trade, crew size, hours on site, superintendent name
3. **Equipment on site** — lifts, heavy machinery, vehicles
4. **Work completed** — what was actually installed or completed, with quantities
5. **Work planned for tomorrow** — what the crew intends to accomplish next day
6. **Delays or issues** — anything that reduced productivity or stopped work
7. **Safety incidents** — any near-miss, first aid, or recordable incident
8. **Visitors** — inspector, owner rep, engineer of record, utility representative
9. **Materials delivered or received** — what arrived, quantity, condition
10. **Open items or RFIs** — anything that needs resolution

If the input is thin on any of these, do not fabricate. Use the placeholder
notation: [NOT REPORTED — confirm with superintendent].

## Step 2 — Classify the Day

Before drafting, classify the day type. This affects how the report is written
and what language is used in the delay section.

**Full Production Day:** All planned work executed as planned. No significant
delays. Normal crew and equipment deployment.

**Partial Production Day:** Work completed but at reduced rate due to weather,
crew reduction, equipment issue, or material shortage.

**Weather Delay Day:** Work stopped or significantly impacted by weather.
Important: document the specific weather condition, the time at which work
stopped, and the crew time that was lost. This documentation supports a
force majeure or excusable delay claim.

**Administrative / Inspection Day:** No significant installation work but
on-site activity for inspection, punch list, commissioning, or meetings.

**Standby / Idle Day:** Crew on site but unable to work due to a condition
outside the EPC's control (material not delivered, access not provided,
owner-caused delay, utility delay). This is the highest-priority day to
document carefully — idle crew costs are the basis of a cost recovery claim.

## Step 3 — Draft the Daily Report

Produce the report in the following format.

---

**DAILY CONSTRUCTION REPORT**

**Project:** [Project name and address]
**Report No.:** [Sequential number if known — otherwise leave blank]
**Date:** [Date]
**Prepared By:** [Superintendent name if provided / left blank if not]
**Report Type:** [Full Production / Partial Production / Weather Delay /
Administrative / Standby-Idle]

---

**WEATHER CONDITIONS**

| | Morning | Afternoon |
|---|---|---|
| Temperature | | |
| Conditions | (Clear / Cloudy / Rain / High Wind / Other) | |
| Wind Speed (est.) | | |

Weather impact on work: [None / Reduced productivity / Work stopped — describe]

---

**CREW ON SITE**

| Company | Trade / Scope | Crew Size | Hours | Superintendent |
|---|---|---|---|---|
| [EPC name] | [General supervision / electrical / civil] | | | |
| [Sub name] | [Racking / civil / electrical / commissioning] | | | |

Total on-site person-hours: [sum]

---

**EQUIPMENT ON SITE**

| Equipment | Quantity | Used / Standby |
|---|---|---|
| [Scissor lift / boom lift / forklift / etc.] | | |

---

**WORK COMPLETED TODAY**

[Write in plain, specific language. Include quantities. Bad: "Installed modules."
Good: "Installed 240 modules on Roof Section B, Rows 1-12, Grid Lines A-D.
Module installation on this section is now 100% complete."]

Scope: [Description of work completed]
Quantities: [Modules installed: X | Conduit run: X LF | Trenching: X LF | etc.]
Percent complete (overall project): [X% if known]

---

**WORK PLANNED FOR TOMORROW**

[What the crew intends to do next. Specific. Referenced to drawing areas
where possible.]

---

**DELAYS AND ISSUES**

[If no delays: "No delays or issues to report."]

[If delays exist — use the following structure for each:]

**Issue [#]:**
- Description: [What happened]
- Cause: [Weather / Material not delivered / Design issue / Owner-caused /
  Equipment failure / Other]
- Duration: [Hours of lost productivity, or full-day stoppage]
- Responsible party: [If known — state factually, not accusatorially]
- Action taken: [What was done to mitigate]
- Open: [Yes — resolution pending / No — resolved on site]

**Note on standby time:** If crew was idle due to a condition outside the
EPC's control, state specifically: "Crew of [X] was on site and available
for work from [time] to [time]. Work could not proceed due to [reason].
Idle time of [X] person-hours is a direct cost to [EPC name] for which
cost recovery will be requested under [contract clause reference if known]."

---

**SAFETY**

Safety orientation conducted: [Yes / No]
Safety incidents today: [None / describe if applicable]
Near-misses or observations: [None / describe if applicable]
PPE compliance: [Full compliance observed / Issues noted — describe]

---

**SITE VISITORS**

| Name | Company / Role | Purpose of Visit | Time on Site |
|---|---|---|---|
| | | | |

[If no visitors: "No site visitors."]

---

**MATERIALS RECEIVED**

| Material | Quantity | Supplier | Condition | PO / Delivery Reference |
|---|---|---|---|---|
| | | | | |

[If nothing received: "No material deliveries today."]

---

**OPEN ITEMS**

| Item | Description | Assigned To | Due Date | Status |
|---|---|---|---|---|
| RFI-[###] | [Brief description] | [EOR / Owner / Utility] | | Open |

[If no open items: "No new open items. Refer to open issues log."]

---

**PHOTOS**

[List photo references or note: "Photos available in project photo log for [date]."]

---

**PREPARED BY:**
Name: ___________________
Title: ___________________
Signature: ___________________
Date: ___________________

---

## Step 4 — Flag High-Priority Items

After producing the report, review it and flag anything that requires
immediate PM or project director attention:

- Any safety incident (even minor)
- Any standby / idle time due to owner or utility-caused delay
- Any material delivery that arrived damaged or with quantity shortfall
- Any inspector visit that resulted in a comment, correction notice,
  or failed inspection
- Any verbal instruction from owner's rep that is not in writing

For each flagged item, add a note:
> **ACTION REQUIRED:** [Specific action needed and who should take it]

## Step 5 — Offer Follow-Through Documents

After delivering the report, offer to:

1. Draft an RFI if any field condition was noted that requires engineering
   clarification
2. Draft a change order if any owner-directed scope change was documented
3. Draft a delay notice letter to the owner if a standby day was documented
   (a formal delay notice protects the right to claim schedule extension)
4. Create a weather delay log if multiple weather delays have been reported

## Examples

Worked examples showing input field notes and the resulting formatted report:

- [Fresno Commerce Center — Full Production Day](examples/fresno-commerce-center.md)
  — Racking milestone completed, two subs on site, owner's rep verbal scope comment,
  material delivery. Illustrates day classification, missing-data placeholders, scope
  milestone language, person-hours math, and verbal-instruction flagging.

## Domain Notes — What Field Notes Usually Miss

When the user's input is sparse, these are the items most commonly omitted:

- Exact crew count by trade (not just "the racking crew")
- Quantity of work completed (not just "installed racking")
- Whether an inspection was passed, failed, or deferred
- Name of utility or owner rep who visited
- Specific weather times (work stopped at 2pm vs. weather all day)
- Whether open items from yesterday were resolved

Ask for these specifically if the input does not include them.
