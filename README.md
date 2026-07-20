# Replication Package: ML and MLOps in EDA and HW/SW Co-Design

This repository contains the replication material for a systematic literature review on machine learning (ML) and Machine Learning Operations (MLOps) practices in Electronic Design Automation (EDA) and hardware/software (HW/SW) co-design for embedded systems.

The package preserves the complete evidence trail used in the review: database exports, merged and de-duplicated records, inclusion/exclusion decisions, backward and forward snowballing, full-text coding forms, and the final set of primary studies.

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
6. **Final evidence base:** 26 primary studies were included in the data extraction and synthesis.

The canonical final dataset is [`03-data-extraction/final_selected_papers.csv`](03-data-extraction/final_selected_papers.csv), with an editable spreadsheet counterpart in [`03-data-extraction/final_selected_papers.xlsx`](03-data-extraction/final_selected_papers.xlsx).

## Repository structure

| Path | Purpose |
|---|---|
| [`Query.docx`](Query.docx) | Search string, database-specific search links, review goal, research questions, and a working summary of the selection process. |
| [`00-data/`](00-data/) | Raw bibliographic exports from the four digital libraries. These files represent the starting point of the review. |
| [`01-ic-ec/`](01-ic-ec/) | Merged records, de-duplication output, venue/document-type exclusions, inclusion/exclusion criteria, and the initial screening decisions. |
| [`02-snowballing/`](02-snowballing/) | Backward and forward snowballing candidates, their screening decisions, and the studies retained for snowballing full-text assessment. |
| [`03-data-extraction/`](03-data-extraction/) | Full-text data extraction forms, coding legend, final selected studies, and the final synthesis dataset. |

Each directory contains its own `README.md` with file-level documentation and the relationship between that directory and the review protocol.

## Identifiers and traceability

Two local identifier families are used throughout the package:

- `Pxxx`: studies originating from the automatic database search.
- `SBxx`: studies originating from backward or forward snowballing.

These identifiers connect PDF filenames, screening records, data extraction rows, and LaTeX citation keys. DOI and venue metadata should be used as the authoritative bibliographic identifiers when available.

## Data formats

- **CSV files** are the portable, machine-readable exports used for inspection and analysis.
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

## Interpretation notes

The coded fields capture what is documented in each publication. An explicit lifecycle capability in the dataset indicates that the study reports evidence for that capability; it does not constitute an independent certification of production readiness or continued software maintenance.

The venue-related criteria and thresholds are those defined in the manuscript. Screening helper fields and automatic proxies should be interpreted together with the final manual decisions, which are the authoritative inclusion/exclusion outcomes.

## Copyright and public-release notice

Bibliographic metadata, screening decisions, and original coding produced by the authors can be shared as replication material. 

## Citation

Please cite the associated paper when using this package. Replace the placeholder below with the final bibliographic record after publication:

```bibtex
@misc{slr_mlops_eda_hwsw,
  title  = {Lifecycle Support for ML-Enabled EDA and HW/SW Co-Design: A Systematic Literature Review, Taxonomy, and Research Agenda},
  author = {See the associated manuscript},
  year   = {2026},
  note   = {Replication package; replace with the final publication metadata}
}
```

## Package status

This repository is an evidence and traceability package for the systematic review. The manuscript remains the authoritative source for the protocol, terminology, interpretation of the results, threats to validity, limitations, and research agenda.
