# Raw Database Exports

This directory contains the unmerged bibliographic records returned by the automatic search described in the systematic literature review protocol.

These files form the immutable starting point of the selection process. They should be preserved as originally exported so that the provenance of every retrieved record can be reconstructed.

## Files

| File | Source | Records | Notes |
|---|---:|---:|---|
| `export_acm.csv` | ACM Digital Library | 994 | Main ACM export after application of the search query and database filters. |
| `export_ieee_1.csv` | IEEE Xplore | 100 | First IEEE export batch. |
| `export_ieee_2.csv` | IEEE Xplore | 100 | Second IEEE export batch. |
| `export_ieee_3.csv` | IEEE Xplore | 100 | Third IEEE export batch. |
| `export_ieee_4.csv` | IEEE Xplore | 25 | Final IEEE export batch. The four IEEE files contain 325 records in total. |
| `export_scopus.csv` | Scopus | 165 | Scopus bibliographic export. |
| `export_springer.csv` | SpringerLink | 380 | SpringerLink bibliographic export. |

The combined raw search produced **1,864 records**:

- ACM Digital Library: 994
- IEEE Xplore: 325
- Scopus: 165
- SpringerLink: 380

## Common content

The exports contain bibliographic fields such as title, authors, publication year, venue, document type, DOI, and source link. Some source-specific columns are present only in individual exports.

The files intentionally retain database-specific formatting. Harmonization, merging, and duplicate removal are performed in the next stage rather than in this directory.

## Relationship to the manuscript

This directory supports the search and identification phase of the review. The general search string and database-specific search URLs are documented in [`../Query.docx`](../Query.docx).

The next processing stage is documented in [`../01-ic-ec/`](../01-ic-ec/), where these records are merged, normalized, de-duplicated, and screened.

## Reproducibility notes

- Do not manually edit these exports after retrieval.
- Database contents and search interfaces change over time; re-running the same query at a later date may return a different number of records.
- When updating the review, store new exports separately and record the new search date rather than overwriting this snapshot.
