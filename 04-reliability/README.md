# 04-reliability-final — Facet-2 two-author inter-coder reliability assessment

This folder contains the **two-author independent re-coding and reconciliation artifacts** used to assess the reliability of the Facet-2 lifecycle classification during the **major-revision stage** of the manuscript.

## Provenance and purpose

During the major revision, **two authors independently re-coded the complete set of 22 empirical/technical studies** against the **10 Facet-2 lifecycle capabilities** using the same predefined `Absent` / `Partial` / `Explicit` operational criteria.

The two coding matrices represent the authors' **independent pre-reconciliation judgments**. They were kept separate and used to compute agreement statistics **before any disagreement was reconciled**. The reconciliation step was performed only after the pre-reconciliation statistics had been frozen.

This reliability exercise was conducted specifically during the major-revision stage. It should therefore be described as a **revision-stage two-author inter-coder reliability assessment**, not as an analysis that had already been performed in the original submission.

## Files

- **`facet2_coder_A.csv`**  
  Independent pre-reconciliation coding produced by Author/Coder A for all 22 empirical/technical studies and all 10 Facet-2 capabilities.

- **`facet2_coder_B.csv`**  
  Independent pre-reconciliation coding produced by Author/Coder B for the same studies and capabilities, using the same predefined coding scheme.

- **`facet2_agreement_summary.csv`**  
  Agreement statistics computed from the two independent coding matrices before reconciliation. The pairing key is `study_id + capability_code`.

- **`facet2_reconciliation.csv`**  
  Side-by-side record of the two independent decisions and the final consensus classification obtained after discussion of the initially discrepant cases against the operational definitions and the supporting evidence.

## Scope and unit of analysis

- Empirical/technical studies coded: **22**
- Framing/survey studies excluded from Facet-2 coding: **4** (`P012`, `P031`, `P078`, `P111`)
- Facet-2 lifecycle capabilities: **10**
- Judgments per coder: **220**
- Paired judgments used for agreement analysis: **220**
- Pairing unit: one `study_id + capability_code` cell

The 10 capabilities are:

- `DG` — Dataset generation
- `FE` — Feature engineering
- `DGV` — Data governance
- `TS` — Training/selection
- `VT` — Validation/testing
- `RS` — Registry/serving
- `MD` — Monitoring/drift
- `RE` — Retraining/evolution
- `TV` — Traceability/versioning
- `CF` — Cross-stage feedback

## Coding scale

The two authors independently applied the same three-level ordinal coding scale:

- **`Absent`** — no supporting evidence for the capability in the study.
- **`Partial`** — the capability is present only locally, incompletely, indirectly, or with limited operational detail.
- **`Explicit`** — a concrete mechanism is clearly described and substantiated in the reported workflow.

The operational question and coding rule associated with each capability are stored directly in the two coder files.

## Pre-reconciliation agreement results

The agreement statistics were computed from the two independent coding matrices **before reconciliation**.

- Paired judgments: **220**
- Agreements: **201**
- Disagreements: **19**
- Raw agreement: **91.36%** (`201 / 220`; stored as `0.913636`)
- Cohen's kappa, unweighted: **0.853** (`0.852708`)
- Quadratic-weighted Cohen's kappa: **0.951** (`0.951184`)

The unweighted Cohen's kappa is reported as the primary nominal agreement statistic. Because the coding categories are ordered (`Absent < Partial < Explicit`), the quadratic-weighted Cohen's kappa is also reported as a complementary ordinal agreement measure.

The 19 initial disagreements occurred only between **adjacent categories**:

- `Absent` vs. `Partial`: **15** cases
- `Partial` vs. `Explicit`: **4** cases
- `Absent` vs. `Explicit`: **0** cases

This pattern is consistent with the main interpretive boundary of the coding scheme: distinguishing absent evidence from limited/partial evidence, and partial evidence from fully explicit operationalization.

## Per-capability agreement

`facet2_agreement_summary.csv` also reports the number of agreements/disagreements, raw agreement, and unweighted Cohen's kappa for each capability.

These capability-level kappa values should be interpreted cautiously because each capability contains only 22 paired judgments and some categories have highly imbalanced or zero marginal frequencies.

Two cases deserve explicit interpretation:

- **`DGV` (Data governance):** raw agreement is high (`20/22 = 90.91%`), while unweighted kappa is `0.000`. This is a prevalence/marginal-distribution effect: Coder A assigned `Absent` to all 22 studies, while Coder B assigned `Absent` to 20 and `Partial` to 2.
- **`TV` (Traceability/versioning):** raw agreement is `100%`, but capability-level Cohen's kappa is mathematically undefined because both coders assigned the same single category (`Absent`) to all 22 studies, so there is no marginal variation. The blank kappa cell in the summary file therefore does not indicate missing coding data.

## Reconciliation procedure

After the pre-reconciliation statistics had been computed and frozen, the two authors reviewed the **19 initial disagreements** against:

1. the predefined Facet-2 operational question;
2. the `Absent` / `Partial` / `Explicit` coding rule;
3. the evidence extracted from the corresponding primary study.

The disagreements were then resolved through author discussion and a final consensus classification was recorded in `facet2_reconciliation.csv`.

The final consensus matrix is used for the manuscript's Facet-2 aggregate results. The independent Coder A and Coder B matrices, rather than the final consensus matrix, are the source for the reported inter-coder agreement statistics.

## Reproducibility rules

When reproducing the reliability analysis:

1. Load `facet2_coder_A.csv` and `facet2_coder_B.csv`.
2. Match rows by `study_id + capability_code`.
3. Verify that each coder file contains exactly `22 × 10 = 220` unique judgments.
4. Verify that `coder_decision` contains only `Absent`, `Partial`, or `Explicit`.
5. Compute raw agreement and Cohen's kappa **before** using any reconciliation data.
6. Compute quadratic-weighted Cohen's kappa using the ordinal order `Absent < Partial < Explicit`.
7. Use `facet2_reconciliation.csv` only after the pre-reconciliation statistics have been computed.
8. Do not overwrite the two independent pre-reconciliation decisions when updating the final consensus matrix.

## Manuscript reporting

A concise description consistent with these artifacts is:

> As an additional reliability assessment conducted during the major-revision stage, two authors independently re-coded the complete set of 22 empirical and technical studies across the ten Facet-2 lifecycle capabilities using the predefined Absent/Partial/Explicit criteria. This resulted in 220 paired capability-level judgments. Before reconciliation, the two coders agreed on 201 of 220 classifications (91.4%), corresponding to an unweighted Cohen's kappa of 0.853. Because the coding scale is ordinal (Absent < Partial < Explicit), a quadratic-weighted Cohen's kappa was also computed as a complementary measure and yielded 0.951. The 19 initial disagreements were subsequently reviewed against the operational definitions and supporting evidence and resolved through discussion. The independent coding matrices, agreement summary, and reconciliation record are provided in the replication package.

