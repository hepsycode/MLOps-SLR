# Full-Text Data Extraction and Final Evidence Base

This directory contains the full-text coding forms and the canonical final dataset used to answer the three research questions and build the classification framework, synthesis, discussion, and research agenda reported in the manuscript.

## Stage summary

- Full-text candidates from the primary database search: **152**
- Final studies retained from the primary search: **22**
- Full-text candidates from snowballing: **17**
- Final studies retained from snowballing: **4**
- Final evidence base: **26 primary studies**

## Files

| File | Description |
|---|---|
| `data_extraction_form_full.xlsx` | Full-text extraction workbook for the 152 studies retained after the initial database-search screening. |
| `data_extraction_form_full_snowballing.xlsx` | Full-text extraction workbook for the 17 snowballing studies retained after their initial screening. |
| `data_extraction_form_legend.csv` | Definitions of the 31 extraction fields used to code bibliographic data, RQ1 characteristics, RQ2 lifecycle coverage, RQ3 limitations/gaps, and reviewer notes. |
| `final_selected_papers.csv` | Canonical machine-readable dataset containing the 26 final primary studies and their completed coding. |
| `final_selected_papers.xlsx` | Editable spreadsheet counterpart of the canonical final dataset. |
| `Nuovo documento di testo.txt` | Non-canonical working note containing a draft LaTeX table and a study-identifier list. It is retained for provenance but should not be used as the authoritative dataset. |

## Coding structure

The extraction form is organized around the review questions:

### RQ1: ML-enabled approaches

The fields record study type, EDA/application subdomain, HW/SW co-design relevance, ML techniques, the addressed problem, and the principal contribution. These fields support the classification by abstraction level, design domain, ML role, and modeling family.

### RQ2: Lifecycle and integration coverage

The fields record data management, model training, validation/testing, deployment or serving, monitoring and feedback, automation/CI/CD support, integration patterns, and the tools, frameworks, or platforms used by each study.

### RQ3: Limitations and research gaps

The fields capture reported limitations, threats or constraints, initial gap tags, and the relevance of each study to the synthesis and positioning of the review.

## Canonical source rule

Use `final_selected_papers.csv` as the authoritative machine-readable source for analysis and manuscript tables. The XLSX version is intended for convenient manual inspection. 

## Traceability

Each row uses either a `Pxxx` or `SBxx` identifier. That identifier links the extraction record to the corresponding PDF, screening decision, and LaTeX citation key. DOI, title, and venue fields provide external bibliographic traceability.

## Interpretation note

The extraction records the evidence reported in the publication. A value indicating lifecycle support should be interpreted as documented coverage, not as an independent audit of the implementation, production maturity, or current availability of the software artifact.