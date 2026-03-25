---
name: change-order-draft
description: >
  Drafts a formal Change Order or Change Order Request (COR) for Solar EPC
  construction projects. Use this skill whenever a user describes additional
  scope, a scope reduction, an owner-directed change, an unforeseen condition
  that increases cost, or any deviation from the original contract scope that
  has a cost or schedule impact. Trigger for phrases like "write a change order",
  "draft a CO", "the owner asked us to add", "we found something that's extra
  work", "document this scope change", "help me price this change", or when
  a user describes work that falls outside the original contract. Also trigger
  when a user mentions a verbal instruction from an owner or GC that has not
  been formalised in writing — capturing verbal scope changes before the crew
  leaves the site is the single most important revenue protection action in
  EPC construction. Every undocumented change is absorbed cost.
---

# Change Order Draft

Unbilled scope creep destroys project margins more reliably than almost any
other single factor in construction. A crew executes a small owner request,
the project manager intends to formalise it later, and by the time the final
invoice is prepared, neither side remembers the conversation clearly.

The window to capture a change order is while the work is happening or
immediately after. This skill closes that window fast.

## What You're Working With

The user will provide one or more of the following:

- A description of the additional or changed scope
- The reason the change is required (owner request, unforeseen condition,
  design change, regulatory requirement)
- Cost information (labour hours, material costs, equipment)
- Schedule impact (days added to completion, milestone affected)
- The contract reference (if known)

If no cost information is provided, the skill will produce a Time and Material
(T&M) change order that captures the scope and authorises the work —
cost to follow. This is better than no change order at all.

## Step 1 — Classify the Change Order

**Type 1 — Owner-Directed Change (ODC)**
The owner or owner's representative has requested additional or different scope.
This is the clearest change order — owner directed, owner pays.
If this was a verbal instruction: flag urgency. Issue before any work begins.

**Type 2 — Unforeseen Condition (UFC)**
Site conditions differ materially from what the contract assumed.
Cost recovery depends on contract language around differing site conditions.
Flag the relevant contract clause if known.

**Type 3 — Design Change (DC)**
The engineer of record has revised the design after the contract was executed.
All costs associated with implementing the revised design are additional scope
unless the contract explicitly includes design revision allowances.

**Type 4 — Regulatory Change (RC)**
A code amendment, AHJ requirement, or utility requirement imposed after
contract execution requires additional work.
Most EPC contracts include language making regulatory changes the owner's
risk — confirm before drafting.

**Type 5 — Acceleration / Schedule Compression**
Owner has requested earlier completion than the contracted schedule.
Overtime, additional crew mobilisation, and expedited procurement are
additional costs. Time-sensitive — issue immediately upon verbal request.

## Step 2 — Capture the Scope and Cost

From the user's description, extract:

**Scope:**
What work is being added, removed, or changed? Be specific about location,
quantities, and the difference from the original contract scope.

**Labour:**
Hours by trade, rate per hour, total labour cost.
If not provided, produce a T&M structure and note "labour cost to be
confirmed based on actual hours."

**Materials:**
List of materials, quantities, unit costs, total material cost.
If not provided, note "material cost to be confirmed based on actual receipts."

**Equipment:**
Any additional equipment rental or owned equipment costs.

**Subcontractor costs:**
If any additional subcontractor scope is involved.

**Overhead and Profit:**
Apply the contract-specified markup if known.
If not specified, use industry standard: 10-15% overhead, 10% profit.
Flag if the contract specifies a different markup for changes.

**Schedule Impact:**
How many calendar days does this change add to the project completion date?
Which milestone is affected?

## Step 3 — Draft the Change Order

Produce the change order in the following format.

---

**CHANGE ORDER REQUEST**
*(or CHANGE ORDER if the owner has already approved and this is the formal document)*

**Project:** [Project name and address]
**COR No.:** [Sequential number — if PM has not assigned, use "COR-[TBD]"]
**Contract No.:** [If known]
**Date Issued:** [Today's date]
**Issued By:** [EPC / Contractor name]
**Directed To:** [Owner / Owner's Representative / GC name]
**Original Contract Value:** $[Amount if known — leave blank if not]
**This Change Order Amount:** $[Amount]
**Revised Contract Value:** $[Original + this CO — leave blank if original unknown]

---

**DESCRIPTION OF CHANGE**

[Plain language. What is being added, removed, or changed. No jargon.
Written so that someone who has never been on the project can understand
exactly what work is being done and why it is outside the original contract.]

**Change Type:** [Owner-Directed / Unforeseen Condition / Design Change /
Regulatory Change / Acceleration]

**Reference:** [RFI number if applicable / Drawing revision / Owner instruction
date / Field directive reference]

---

**BASIS FOR CHANGE**

[Why this is additional scope. One paragraph.

For Owner-Directed: "Per verbal instruction from [Owner Rep Name] on [date],
the Contractor was directed to [description]. This scope was not included in
the original Contract."

For Unforeseen Condition: "During [phase of work], the Contractor encountered
[condition] at [location]. This condition was not anticipated by the Contract
Documents and could not have been reasonably foreseen. The original Contract
assumed [what the contract assumed]. The actual condition requires [additional work]."

For Design Change: "Drawing revision [rev number] dated [date] issued by
[engineer of record] requires modifications to [scope] that were not included
in the original Contract scope."]

---

**SCOPE OF WORK**

[Detailed description of the specific work to be performed under this change.
Use bullet points for clarity. Include:
- Specific locations on the project
- Specific tasks
- Materials to be installed
- Any work to be removed or modified]

---

**COST BREAKDOWN**

| Category | Description | Quantity | Unit | Unit Cost | Total |
|---|---|---|---|---|---|
| **Labour** | | | | | |
| [Trade] | [Task description] | [hrs] | hr | $[rate] | $[total] |
| [Trade] | [Task description] | [hrs] | hr | $[rate] | $[total] |
| **Labour Subtotal** | | | | | **$[total]** |
| **Materials** | | | | | |
| [Material] | [Description] | [qty] | [unit] | $[unit cost] | $[total] |
| **Materials Subtotal** | | | | | **$[total]** |
| **Equipment** | | | | | |
| [Equipment] | [Description] | [qty] | [unit] | $[rate] | $[total] |
| **Equipment Subtotal** | | | | | **$[total]** |
| **Subcontractor** | | | | | **$[total]** |
| **Direct Cost Subtotal** | | | | | **$[total]** |
| **Overhead ([X]%)** | | | | | **$[total]** |
| **Profit ([X]%)** | | | | | **$[total]** |
| **TOTAL CHANGE ORDER VALUE** | | | | | **$[TOTAL]** |

*Note: If T&M change order, replace table with:*
*"Work to be performed on a Time and Material basis per contract rates.*
*Cost to be documented and submitted upon completion. Estimated cost: $[range].*
*A not-to-exceed authorization of $[amount] is requested."*

---

**SCHEDULE IMPACT**

Contract completion date (current): [Date]
Days added by this change: [X calendar days]
Revised contract completion date: [Date]

[If no schedule impact: "This change has no impact on the project completion date."]

[If schedule impact: "The work required by this change order will add [X]
calendar days to the project schedule. The revised substantial completion
date is [date]. Time extension to be formalised in a contract amendment."]

---

**APPROVAL**

By executing this Change Order, the Owner authorises the Contractor to proceed
with the described scope of work and agrees to the adjusted Contract Sum and
Schedule set forth herein.

| | Contractor | Owner |
|---|---|---|
| Name | | |
| Title | | |
| Signature | | |
| Date | | |

---

## Step 4 — Flag Urgency and Next Steps

After producing the change order draft, review for time-sensitive items:

**If work has already started or been completed:**
> **IMPORTANT:** This change order documents work that has already been
> performed. Obtain signed approval immediately. Unsigned change orders for
> completed work are the hardest to recover on final billing.

**If this was a verbal instruction:**
> **ACTION REQUIRED:** Send this to the owner's representative today.
> Do not wait. A verbal instruction executed without written confirmation
> is a gift to the owner — they can dispute it at closeout.

**If there is a schedule impact:**
> **NOTE:** This change order includes a schedule extension request.
> The owner must approve the schedule impact in writing as well as the
> cost. A signed CO that does not address schedule leaves the EPC exposed
> to liquidated damages on the extended completion date.

## Step 5 — Offer Related Documents

After delivering the change order draft, offer to:

1. Draft a transmittal email to the owner's representative attaching the CO
2. Draft a T&M ticket for immediate on-site use if the work is starting now
3. Update the project change order log (if the user maintains one)
4. Draft a back-charge notice if the cost is being passed through to
   a subcontractor who caused the condition

## Domain Notes — Most Common Change Order Scenarios in Solar EPC

**Field conditions that always generate COs:**
- Roof condition worse than survey — reroofing or structural reinforcement
- Underground utilities in conflict with trenching plan
- Main panel insufficient capacity — panel upgrade required
- Conduit routing changes due to existing building obstructions
- HVAC or mechanical conflicts on flat rooftop

**Owner-directed changes that are frequently not captured:**
- "While you're up there, can you also add an outlet?" — electrical
- "Move the inverter to the other side" — involves reracking, rerunning conduit
- "Add two more modules to this string" — requires design change, permit revision
- "Put the disconnect here instead" — location change has conduit implications

**Regulatory changes that generate COs:**
- AHJ inspector requires additional labeling not on approved plans
- Fire marshal requires pathway modification from approved design
- Utility requires additional metering equipment not in original scope
- Updated AHJ checklist requires additional calculations or documentation
