# Replication Package: Lifecycle Support for ML-Enabled EDA and HW/SW Co-Design

This repository contains the replication material for a systematic literature review on lifecycle support for ML-Enabled EDA and HW/SW Co-Design for embedded systems.

The package preserves the complete evidence trail used in the review: database exports, merged and de-duplicated records, inclusion/exclusion decisions, backward and forward snowballing, full-text coding forms, the final set of primary studies, and the revision-stage inter-coder reliability assessment for the Facet-2 lifecycle classification.

## Research questions

The review addresses the following research questions:

- **RQ1:** What existing approaches combine machine learning with electronic design automation and HW/SW co-design for embedded systems?
- **RQ2:** How do these approaches support MLOps-related lifecycle activities, tools, and integration workflows?
- **RQ3:** What limitations and research gaps characterize the current state of the art?

## Review flow represented in this repository

The repository mirrors the review process described in the manuscript:

1. **Database search:** 1,864 records were exported from ACM Digital Library, IEEE Xplore, Scopus, and SpringerLink.
2. **Merge and de-duplication:** 131 duplicate records were removed, leaving 1,733 unique records.
3. **Initial screening:** metadata and title/abstract screening produced 152 studies for full-text assessment.
4. **Primary-search full-text assessment:** 22 studies were retained.
5. **Snowballing:** 33 additional candidates were identified (28 backward and 5 forward); 17 passed the initial snowballing screening and 4 were retained after full-text assessment.
6. **Final evidence base:** 26 primary studies were included in the data extraction and synthesis. Of these, 22 empirical/technical studies were coded for Facet 2, while 4 framing/survey studies were retained for contextual synthesis.
7. **Inter-coder reliability assessment:** 2 authors independently re-coded the 22 empirical/technical studies across the 10 Facet-2 lifecycle capabilities, producing 220 paired study-capability judgments. Before reconciliation, the coders agreed on 201 judgments and disagreed on 19, corresponding to 91.36% raw agreement, an unweighted Cohen's kappa of 0.853, and a quadratic-weighted Cohen's kappa of 0.951. Reconciliation was performed only after the pre-reconciliation agreement statistics had been computed and frozen.

The canonical final dataset is [`03-data-extraction/final_selected_papers.csv`](03-data-extraction/final_selected_papers.csv), with an editable spreadsheet counterpart in [`03-data-extraction/final_selected_papers.xlsx`](03-data-extraction/final_selected_papers.xlsx).

The independent coding matrices, agreement statistics, and reconciliation record used for the Facet-2 reliability assessment are available in [`04-reliability/`](04-reliability/).

## Repository structure

| Path | Purpose |
|---|---|
| [`Query.docx`](Query.docx) | Search string, database-specific search links, review goal, research questions, and a working summary of the selection process. |
| [`00-data/`](00-data/) | Raw bibliographic exports from the four digital libraries. These files represent the starting point of the review. |
| [`01-ic-ec/`](01-ic-ec/) | Merged records, de-duplication output, venue/document-type exclusions, inclusion/exclusion criteria, and the initial screening decisions. |
| [`02-snowballing/`](02-snowballing/) | Backward and forward snowballing candidates, their screening decisions, and the studies retained for snowballing full-text assessment. |
| [`03-data-extraction/`](03-data-extraction/) | Full-text data extraction forms, coding legend, final selected studies, and the final synthesis dataset. |
| [`04-reliability/`](04-reliability/) | Revision-stage two-author inter-coder reliability artifacts for the Facet-2 lifecycle classification, including the two independent pre-reconciliation coding matrices, agreement statistics, and the final reconciliation record. |

Each directory contains its own `README.md` with file-level documentation and the relationship between that directory and the review protocol.

### Reliability artifacts

The [`04-reliability/`](04-reliability/) directory contains:

- [`facet2_coder_A.csv`](04-reliability/facet2_coder_A.csv): independent pre-reconciliation coding produced by Author/Coder A for the 22 empirical/technical studies and the 10 Facet-2 lifecycle capabilities.
- [`facet2_coder_B.csv`](04-reliability/facet2_coder_B.csv): corresponding independent pre-reconciliation coding produced by Author/Coder B using the same predefined coding scheme.
- [`facet2_agreement_summary.csv`](04-reliability/facet2_agreement_summary.csv): overall and capability-level agreement statistics computed before reconciliation.
- [`facet2_reconciliation.csv`](04-reliability/facet2_reconciliation.csv): side-by-side comparison of the two independent judgments and the final consensus classification established after discussion of the initially discrepant cases.
- [`README.md`](04-reliability/README.md): detailed description of the reliability procedure, coding scale, agreement measures, reconciliation process, and reproduction rules.

The reliability assessment covers:

- **22** empirical/technical studies;
- **10** Facet-2 lifecycle capabilities;
- **220** paired study-capability judgments;
- **201** pre-reconciliation agreements;
- **19** pre-reconciliation disagreements;
- **91.36%** raw agreement;
- **0.853** unweighted Cohen's kappa;
- **0.951** quadratic-weighted Cohen's kappa.

All 19 pre-reconciliation disagreements occurred between adjacent categories of the ordinal `Absent < Partial < Explicit` scale. The independent coding matrices are the source of the agreement statistics, whereas the reconciled classifications are used for the final Facet-2 synthesis reported in the manuscript.

## Identifiers and traceability

Two local identifier families are used throughout the package:

- `Pxxx`: studies originating from the automatic database search.
- `SBxx`: studies originating from backward or forward snowballing.

These identifiers connect PDF filenames, screening records, data extraction rows, reliability-assessment records, and LaTeX citation keys. DOI and venue metadata should be used as the authoritative bibliographic identifiers when available.

For the reliability assessment, each individual coding judgment is uniquely paired using:

`study_id + capability_code`

This allows the two independent coding matrices to be compared deterministically across all 220 Facet-2 judgments.

## Data formats

- **CSV files** are the portable, machine-readable exports used for inspection, analysis, reliability assessment, and reconciliation.
- **XLSX files** preserve the editable working sheets, including filtered or selected views used during screening.
- **DOCX/TXT files** contain auxiliary protocol notes or manuscript-oriented working material.

The package does not require a dedicated software environment. CSV files can be processed with any tabular-data tool, while XLSX files can be inspected with a compatible spreadsheet application.

## Suggested reproduction path

To audit the review manually:

1. Inspect the search formulation in `Query.docx` and the raw exports in `00-data/`.
2. Verify that the merged file in `01-ic-ec/` contains 1,733 unique records.
3. Review the IC/EC definitions and the record-level mapping in `01-ic-ec/`.
4. Inspect the 152 full-text candidates in `01-ic-ec/04_final_selected_paper.xlsx`.
5. Review the snowballing candidate set and decisions in `02-snowballing/`.
6. Use the extraction legend and the two full-text coding workbooks in `03-data-extraction/` to audit the classification.
7. Compare the final 26 rows in `03-data-extraction/final_selected_papers.csv` with the synthesis reported in the manuscript.
8. Inspect `04-reliability/facet2_coder_A.csv` and `04-reliability/facet2_coder_B.csv` and verify that each contains exactly 220 unique `study_id + capability_code` judgments for the 22 empirical/technical studies and 10 Facet-2 lifecycle capabilities.
9. Recompute the pre-reconciliation agreement statistics and compare them with `04-reliability/facet2_agreement_summary.csv`: 201/220 agreements, 91.36% raw agreement, unweighted Cohen's kappa = 0.853, and quadratic-weighted Cohen's kappa = 0.951.
10. Inspect the 19 initially discrepant judgments in `04-reliability/facet2_reconciliation.csv` and verify the final consensus classifications used in the manuscript-level Facet-2 synthesis.

When reproducing the reliability analysis, agreement statistics must be computed from the two independent coder matrices **before** using the reconciliation file. The reconciled decisions must not replace or overwrite the original pre-reconciliation judgments.

## Interpretation notes

The coded fields capture what is documented in each publication. An explicit lifecycle capability in the dataset indicates that the study reports evidence for that capability; it does not constitute an independent certification of production readiness or continued software maintenance.

The venue-related criteria and thresholds are those defined in the manuscript. Screening helper fields and automatic proxies should be interpreted together with the final manual decisions, which are the authoritative inclusion/exclusion outcomes.

The independent Coder A and Coder B matrices represent pre-reconciliation judgments. The agreement statistics are calculated exclusively from these independent judgments. The reconciliation file documents the subsequent consensus process and provides the final classifications used for the revised manuscript's Facet-2 aggregate results.

## Copyright and public-release notice

Bibliographic metadata, screening decisions, original coding produced by the authors, inter-coder reliability records, and reconciliation decisions can be shared as replication material.

The package does not redistribute copyrighted full-text publications unless their redistribution is explicitly permitted by the applicable license.

## Citation

Please cite the associated paper when using this package. Replace the placeholder below with the final bibliographic record after publication:

```bibtex
@misc{slr_mlops_eda_hwsw,
  title  = {Lifecycle Coverage for Machine-Learning-Enabled Electronic Design Automation and Hardware/Software Co-Design},
  author = {Vittoriano Muttillo, Giacomo Valente, Romina Eramo, Luigi Pomante},
  year   = {2026},
  note   = {Replication package; replace with the final publication metadata}
}
