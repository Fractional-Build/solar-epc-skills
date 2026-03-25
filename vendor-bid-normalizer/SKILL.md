---
name: vendor-bid-normalizer
description: >
  Normalises and compares multiple vendor bids or procurement quotes for Solar
  EPC projects into a single structured comparison. Use this skill whenever a
  user has received two or more quotes for the same equipment or scope of work
  and needs to compare them on equal terms. Trigger for phrases like "compare
  these bids", "which vendor is cheaper", "help me evaluate these quotes",
  "normalize these proposals", "vendor comparison", "procurement analysis",
  or when a user pastes or uploads multiple quotes with different formats,
  units, or inclusions. Also trigger when a user asks about total landed cost,
  shipping inclusion, warranty comparison, or wants to understand the real
  difference between two vendor quotes. Apples-to-apples comparison is
  impossible without normalization — trigger this skill whenever bids arrive.
---

# Vendor Bid Normalizer

Three bids arrive in three different formats. One quotes FOB factory. One
includes freight. One bundles modules and racking together. Comparing them
directly produces the wrong answer. This skill normalises all bids to the
same basis before any comparison is made.

## What You're Working With

The user will provide two or more of the following:

- Vendor quotes (pasted, uploaded, or described)
- Equipment specifications per quote
- Project location (for freight normalisation)
- Timeline requirements (for lead time comparison)
- Any prior pricing context or budget expectations

If fewer than two quotes are provided, the output is a structured extraction,
not a comparison. State this clearly and offer to run the comparison once
the second quote is available.

## Step 1 — Extract Each Quote Into a Standard Structure

For each bid received, extract the following. If a field is not in the quote,
mark it as NOT STATED. Never assume inclusion — if it's not written, it's not included.

### Equipment Quote Structure

| Field | Vendor A | Vendor B | Vendor C |
|---|---|---|---|
| Vendor name | | | |
| Quote number / reference | | | |
| Quote date | | | |
| Quote validity (expiry) | | | |
| Equipment description | | | |
| Manufacturer | | | |
| Model number | | | |
| Quantity | | | |
| Unit | (each / Wp / kW / pallet) | | |
| Unit price | | | |
| Extended price | | | |
| Freight terms | (FOB / CIF / DDP) | | |
| Freight cost (if stated) | | | |
| Destination (if stated) | | | |
| Lead time from PO | | | |
| Warranty — product | | | |
| Warranty — performance (modules) | | | |
| Payment terms | | | |
| Minimum order quantity | | | |
| Certifications included | | | |
| Domestic / imported content | | | |
| Tariff applicability noted | | | |

## Step 2 — Identify Normalisation Gaps

Before computing a comparison, identify every dimension where the bids
are NOT comparing the same thing. These must be resolved before any
comparison is valid.

Common gaps:

**Freight terms mismatch**
FOB factory (buyer pays freight) vs. DDP (delivered duty paid, seller pays
freight and customs) can represent a 3-10% cost difference depending on
origin and destination. Do not compare unit prices until freight basis is aligned.

Freight estimation if not stated: if project location is provided and
equipment origin is known, provide an order-of-magnitude freight estimate.
Flag it clearly as an estimate.

**Unit mismatch**
One quote in $/W, one in $/module. One in $/linear foot, one in $/kit.
Convert all to the same unit before comparison.

**Scope mismatch**
One quote includes mounting hardware; one does not.
One quote includes disconnects; one does not.
One quote includes commissioning; one does not.
Itemise the inclusions/exclusions for each bid before comparing totals.

**Quantity mismatch**
One quote is for 500 modules; one is for 600 modules (different project
assumptions). Normalise to the same quantity.

**Model mismatch**
Different module models from different manufacturers are not interchangeable.
If comparing non-identical equipment, flag this prominently — a lower-cost
module with lower efficiency changes the system design and may require more
racking, more labour, or a larger footprint.

**Warranty mismatch**
A module with a 25-year linear performance warranty is not equivalent to
one with a 10-year step-down warranty, even at the same wattage.
Note the difference but do not assign a dollar value to it — that is a
business judgment for the user.

**Lead time mismatch**
If one vendor can deliver in 4 weeks and another in 16 weeks, and the
project mobilises in 6 weeks, the 16-week option may not be viable
regardless of price. Flag lead time risk independently of price comparison.

## Step 3 — Build the Normalised Comparison

Once gaps are identified and addressed (either resolved or explicitly flagged),
produce the comparison table.

### Normalised Comparison Table

| | Vendor A | Vendor B | Vendor C |
|---|---|---|---|
| **Equipment** | | | |
| Manufacturer / Model | | | |
| Quantity (normalised) | | | |
| Unit price (normalised basis) | | | |
| Extended equipment cost | | | |
| **Logistics** | | | |
| Freight cost (stated or estimated) | | | |
| Tariff exposure | | | |
| Estimated landed cost | | | |
| **Terms** | | | |
| Lead time | | | |
| Payment terms | | | |
| Quote validity | | | |
| **Warranty** | | | |
| Product warranty | | | |
| Performance warranty | | | |
| **Total landed cost** | **$X** | **$X** | **$X** |
| **Delta vs. lowest** | — | +$X (+X%) | +$X (+X%) |

### Key Differences Summary

Below the table, write a plain-language paragraph for each material difference
that is not captured in the numbers. This section is for the person who will
make the procurement decision — it should take 60 seconds to read.

Example:
> "Vendor B is $X lower in total landed cost but carries a 16-week lead time
> versus Vendor A's 6 weeks. Given the project's scheduled mobilisation date
> of [date], Vendor B's lead time creates a procurement risk that would need
> to be mitigated with a deposit and confirmed order within [X] days.
> Vendor C's quote uses a different module model with [X]W lower rated power —
> this would require [Y] additional modules to meet the design capacity,
> changing the effective cost per watt to $[Z], which makes it the highest-cost
> option despite the lower unit price."

## Step 4 — Flag Tariff and Country-of-Origin Risk

For all equipment quotes, flag the following. Read `references/tariff-guide.md`
for current tariff context.

- Modules: country of manufacture, applicable Section 201 or 301 tariffs,
  AD/CVD exposure, UFLPA compliance requirements
- Inverters: country of manufacture, tariff applicability
- Racking: country of manufacture, steel/aluminum tariff applicability

Do not quantify tariff impact unless specific rates are confirmed — tariff
environments change. Flag the risk and recommend the user confirm with their
trade compliance team or freight forwarder.

## Step 5 — Produce the Recommendation

After the comparison table and differences summary, produce a recommendation
section with three options:

**If one vendor is clearly superior on total landed cost AND terms AND lead time:**
State it directly. "On a total landed, apples-to-apples basis, Vendor A
represents the best value for this procurement."

**If there is a trade-off (e.g., lower cost vs. shorter lead time):**
Frame the decision as a binary. "This procurement decision turns on whether
[lead time / warranty / payment terms] is the higher priority for this project."

**If the bids cannot be fairly compared due to missing information:**
State what is needed. "A valid comparison requires [specific information]
from Vendor B. Until this is provided, Vendor A is the only fully specified
option."

## Important Constraints

This analysis is based on the information provided in the quotes. Vendor
representations about lead time, warranty coverage, and product specifications
should be confirmed in a purchase order with specific contractual terms.
A lower price on a quote that ships late, ships a different model, or has
a warranty that is difficult to enforce is not a saving — it is a risk.
