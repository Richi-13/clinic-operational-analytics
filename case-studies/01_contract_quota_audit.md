# Case Study: Reconstructing Missing Contract Data and Winning an Internal Argument for a Funding Appeal
### (Anonymized — methodology and sequence of events preserved, identifying details generalized)

## Context

A public healthcare institution operates under a fixed-term contract with a
national health insurer (a single-payer model). Funding for outpatient
service packages is set as a "global rate" — a planned monthly budget per
package — which the contract allows either party to request a revision of,
if the actual value of services delivered differs materially from the
planned rate for three consecutive months.

## Problem, part 1 — the data disappeared

Starting in 2026, the insurer stopped including payment amounts in the
monthly electronic medical record (EMR) exports altogether. Previously,
the institution could read its actual earned revenue per service package
directly from the file. From 2026 onward, that column was simply gone —
only the service code remained.

Without a way to calculate actual earned revenue, the institution had no
way to monitor its own performance against the contract's global rate, and
no way to know whether it was eligible to request a rate revision at all.

## Method, part 1 — reconstructing the missing calculation

Rather than treating this as a dead end, the calculation was rebuilt from
first principles, using the one thing the insurer's files still contained:
the service code. A national government decree publishes, for every
service code, the base rate and adjustment coefficient used to calculate
its price. By parsing that decree and joining it against the service codes
still present in the monthly files, actual earned revenue per package
could be reconstructed automatically and accurately — restoring full
visibility into contract performance. (This reconstructed pricing logic
became a core piece of the institution's later database redesign.)

## Problem, part 2 — a false "no basis to act"

With the reconstructed figures, Q1 2026 showed underperformance against
the global rate (as expected — this had already led to a rate cut). Q2,
however, showed the opposite: the institution significantly exceeded its
global rate. Based on a documented precedent from the previous year — where
raising a formal revision request had at least established the
institution's right to do so — a proposal was made to management to submit
a new funding-increase request for Q3–Q4.

Institutional leadership initially declined, stating there was "no basis"
to write such a letter — citing a belief that the insurer evaluates
performance by patient volume, not by earned revenue, and that the
institution was in fact underperforming, not overperforming.

## Method, part 2 — re-reading the contract to resolve the disagreement

To resolve the disagreement, the relevant contract clauses were re-read in
detail (with AI-assisted document analysis to speed up cross-referencing).
This surfaced two key facts that had been missed:

1. **The evaluation criterion is earned revenue, not patient/record
   count** — the contract explicitly bases rate revisions on the actual
   value of services delivered, contrary to leadership's assumption.
2. **The three-month evaluation is a cumulative sum, not a per-month or
   averaged comparison** — the insurer compares the sum of the planned
   rate across three months against the sum of actual earned revenue
   across the same three months, not month-by-month. This detail had
   caused earlier confusion about a rate cut that seemed to contradict the
   institution's own (correct) monthly figures.

A written justification memo was prepared, citing the specific contract
clauses, the applicable government decree, and the reconstructed revenue
figures, to formally support the funding-increase request.

## Outcome

The written justification was passed up to institutional leadership and
legal counsel, who — after reviewing the cited contract clauses — agreed
with the analysis and submitted a formal request to the insurer for a
global-rate revision for the upcoming quarters. A response from the
insurer is still pending at the time of writing; based on the prior year's
precedent, a favorable outcome is possible but not guaranteed. Regardless
of the insurer's decision, establishing the institution's clear
contractual right to request revision — backed by a repeatable, correct
calculation method — was itself considered a valuable outcome by
leadership.

## Skills demonstrated

- Rebuilding a broken/missing data pipeline from first principles when a
  primary data source is discontinued
- Contract and regulatory document analysis to resolve a factual dispute
- Persistence and independent verification when a stated "no basis to act"
  conflicted with the underlying data
- Translating a legal/contractual argument into a clear, evidence-backed
  written case for non-technical and executive stakeholders
- Cross-functional collaboration with legal counsel to formalize an
  external request

