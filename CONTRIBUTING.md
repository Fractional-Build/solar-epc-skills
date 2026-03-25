# Contributing to solar-epc-skills

This library gets better when people who work in Solar EPC every day
contribute what they know. A permitting coordinator in Sacramento who
catches an outdated form requirement. A project manager in New Jersey
who knows exactly which fire marshal will reject a package without a
separate review letter. A procurement manager who has been burned by
a specific vendor's freight terms.

That knowledge is not in any textbook. It is in this file, if you put it here.

---

## What we need most

### AHJ profiles for uncovered jurisdictions

The `ahj-permit-checker/references/ahj-profiles.md` file currently covers
California, Texas, Arizona, Nevada, Colorado, New Jersey, and Massachusetts.

Every state not on that list is a gap. Every county or municipality with
a quirk that differs from its state's standard is a gap.

If you work in a market and you know something specific — a form that
updated recently, an inspector who always flags a particular item, a
jurisdiction that requires something unusual — that belongs in this file.

**High-priority jurisdictions we know are missing:**
- Florida (utility-scale and C&I)
- North Carolina
- Georgia
- Illinois / Midwest markets
- New York (Con Ed territory vs. PSEG Long Island vs. upstate)
- Pacific Northwest (Oregon, Washington)
- Mountain West (Utah, New Mexico, Idaho)
- Hawaii (HECO interconnection is its own world)

### Code updates and corrections

NEC adoption timelines change. AHJs update their requirements without
announcement. Fire departments amend setback rules independently of
building departments.

If something in the reference files is wrong or out of date, open an issue
or submit a correction. A stale reference file is worse than no reference
file — it generates false confidence.

### Field scenarios not covered

The `rfi-writer`, `daily-report-formatter`, and `change-order-draft` skills
each include a section on common field scenarios. Those lists are not
exhaustive. If your operation regularly encounters a condition that is not
in the skill, it should be.

### Tariff and procurement intelligence

The tariff environment for solar equipment changes frequently. The
`vendor-bid-normalizer/references/tariff-guide.md` file reflects the
landscape as of early 2026. If something has changed, submit an update
with a source reference.

---

## How to contribute

### Option 1 — Open an issue (easiest)

You do not need to write code or format a pull request. If you know
something that belongs in this library, open an issue and describe it
in plain language. We will format it and integrate it.

Use the issue title format:
- `[AHJ] Sacramento County — updated fire setback rules 2024`
- `[CODE] NEC 2023 rapid shutdown changes`
- `[FIELD] Common RFI scenario missing — soil contamination discovery`
- `[TARIFF] AD/CVD rate update for [manufacturer]`
- `[BUG] Incorrect information in [file name]`

### Option 2 — Submit a pull request

Fork the repository, make your changes, and open a pull request against
the `main` branch.

**For AHJ profile additions**, follow the existing format in
`ahj-permit-checker/references/ahj-profiles.md`. Each entry should include:

- NEC edition adopted
- PE stamp requirements
- Fire setback requirements and any local amendments
- Whether a three-line diagram is required in addition to the SLD
- Any known rejection triggers — the specific things that cause packages
  to bounce in that jurisdiction
- Utility name and any interconnection pre-approval requirements

You do not need to fill every field. Partial, accurate information is
more valuable than a complete entry that is partly guessed.

**For code corrections**, include a reference — the NEC section, the
AHJ bulletin, the code update notice. An assertion without a source
cannot be verified and will not be merged.

**For field scenario additions**, write them in the same format as the
existing scenarios in the relevant skill: a one-line description of the
condition followed by what makes it worth documenting.

---

## What makes a good contribution

**Specific over general.**
"Los Angeles City requires 4-foot pathways, not 3-foot" is useful.
"Some California jurisdictions have stricter requirements" is not.

**Sourced where possible.**
If you can point to the AHJ bulletin, the NEC section, or the utility
interconnection guide that confirms what you are contributing, include it.
If you cannot — because you learned it from a plan checker conversation
or a rejected permit — that is still worth contributing. Mark it as
"field-verified" and note the approximate date.

**First-hand or well-verified.**
Do not contribute something you read in a forum post without independently
confirming it. A wrong entry in the AHJ profiles causes real damage to
real permit applications.

**Dated.**
AHJ requirements and tariff rules change. When you contribute something
time-sensitive, note when you verified it. An entry that says "verified
March 2026" is more useful than one that has no date, because a reader
knows to re-check it if significant time has passed.

---

## What we do not accept

- Contributions that could be used to circumvent permit requirements or
  misrepresent a system design to an AHJ. This library is for helping
  EPCs get permits approved correctly, not for finding shortcuts around
  legitimate safety requirements.

- Vendor-specific promotional content. The tariff guide and procurement
  references are factual. They are not a place to recommend specific
  vendors or products.

- Unverified AHJ requirements submitted as fact. If you are not certain,
  frame it as "unverified — confirm with building department" and we will
  accept it with that framing.

---

## Recognition

Contributors who submit verified AHJ profiles, code corrections, or
material field scenario additions will be acknowledged in the repository's
`CONTRIBUTORS.md` file by name or GitHub handle, whichever they prefer.

If your contribution comes from direct field experience at a named EPC firm
and you want to be identified that way, we will include it. Practitioners
who contribute their knowledge deserve credit for it.

---

## Questions

Open an issue with the label `question` or reach out directly:

**Vishal Soni — Fractional Build**
vishal@fractional.build
https://fractional.build

---

*The best version of this library is built by the people who live in
these workflows every day. We built the structure. You have the knowledge
that makes it accurate.*
