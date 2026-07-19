# Inclusion/Exclusion Screening

This directory documents the merge, de-duplication, metadata filtering, and initial inclusion/exclusion (IC/EC) screening applied to the records retrieved from the four digital libraries.

## Stage summary

- Raw records: **1,864**
- Duplicates removed: **131**
- Unique records: **1,733**
- Excluded because of low or missing venue classification: **339**
- Excluded because of non-target document type: **259**
- Records retained for detailed IC/EC mapping: **1,135**
- Studies selected for full-text assessment: **152**

## Files

| File | Description |
|---|---|
| `00_export_selected_papers_merged.csv` | Harmonized and de-duplicated master export containing 1,733 unique records from all databases. |
| `00_ic_ec_criteria_legend.csv` | Definitions of the IC/EC screening fields and the evidence source or proxy used for each field. |
| `01_excluded_papers_low_rank.csv` | Records excluded because the venue did not satisfy the ranking threshold adopted in the manuscript. |
| `02_excluded_other_document_types.csv` | Records excluded because they were not eligible peer-reviewed article/conference study types. |
| `03_paper_ic_ec_mapping.csv` | Machine-readable record-level screening matrix for the 1,135 studies retained after the first metadata exclusions. |
| `03_paper_ic_ec_mapping.xlsx` | Editable screening workbook. It contains the complete mapping and a `Selected` sheet with the 152 studies retained for full-text assessment. |
| `04_final_selected_paper.xlsx` | Compact bibliographic list of the 152 studies selected for full-text assessment after initial IC/EC screening. |

## Screening fields

The mapping records domain relevance, ML/AI relevance, lifecycle/workflow relevance, alignment with the research questions, peer-review/document-type eligibility, and venue eligibility. It also records exclusion indicators for isolated tasks, runtime-only acceleration, generic ML, and generic process/MLOps work outside the EDA and HW/SW co-design domain.

The short field names are explained in `00_ic_ec_criteria_legend.csv`. The final acceptance decision should be treated as authoritative; proxy fields are screening aids and should not be interpreted independently of the manual review.

## Workflow

1. Merge the files from [`../00-data/`](../00-data/).
2. Normalize the shared bibliographic fields.
3. Remove duplicate records using bibliographic identifiers and title-level comparison.
4. Apply metadata-level exclusions for venue classification and document type.
5. Apply the IC/EC criteria to title and abstract information.
6. Retain the 152 studies listed in `04_final_selected_paper.xlsx` for full-text reading and data extraction.

## Relationship to later stages

The 152 full-text candidates are coded in [`../03-data-extraction/data_extraction_form_full.xlsx`](../03-data-extraction/data_extraction_form_full.xlsx). Additional candidates identified through citation chasing are processed separately in [`../02-snowballing/`](../02-snowballing/).

## Audit guidance

When auditing a decision, use the DOI and title to trace the record back to the merged export, then compare the individual IC/EC fields with the criteria stated in the manuscript. Venue classification is a protocol-level filter and is distinct from the later full-text assessment of substantive relevance.
