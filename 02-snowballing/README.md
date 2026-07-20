# Backward and Forward Snowballing

This directory documents the supplementary citation-chasing stage used to identify relevant studies that were not captured by the automatic database search.

Both backward snowballing (screening references cited by the selected studies) and forward snowballing (screening studies that cite the selected studies) were performed using the same eligibility logic adopted for the initial search.

## Stage summary

- Backward candidates: **28**
- Forward candidates: **5**
- Total snowballing candidates: **33**
- Candidates passing the initial snowballing IC/EC screening: **17**
- Additional studies retained after full-text assessment: **4**

The four final snowballing studies are `SB01`, `SB13`, `SB14`, and `SB32`.

## Files

| File | Description |
|---|---|
| `00 - snowballing_candidates.csv` | Bibliographic list of all 33 candidates identified through backward and forward snowballing. |
| `00_ic_ec_criteria_legend.csv` | Definitions of the screening fields used for snowballing candidates. |
| `01 - snowballing_candidates - ic-ec.csv` | Working screening sheet containing the candidate metadata and IC/EC columns. |
| `04_ic_ec_compiled_final.csv` | Completed, machine-readable snowballing screening matrix. |
| `04_ic_ec_compiled_final.xlsx` | Editable counterpart of the completed snowballing screening matrix. |
| `04_ic_ec_selected.xlsx` | The 17 candidates retained for snowballing full-text assessment. |

## Identifiers

Snowballing records use the `SBxx` identifier family. The numbering preserves the candidate list and allows each item to be traced across filenames, screening spreadsheets, extraction forms, and the manuscript bibliography.

## Relationship to the final evidence base

Passing the initial snowballing screening did not automatically imply final inclusion. The 17 retained candidates underwent full-text data extraction in [`../03-data-extraction/data_extraction_form_full_snowballing.xlsx`](../03-data-extraction/data_extraction_form_full_snowballing.xlsx). Four of them met the final relevance threshold and were added to the 22 studies retained from the primary database search.
