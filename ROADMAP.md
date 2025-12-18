# GEO rulepacks roadmap

## geo_bulk_seq
### v0.1 (starter) — current focus
- Required columns present
- Biological context present (tissue/cell_line/cell_type)
- sample_id crosscheck between samples.tsv and files.tsv
- Paired-end completeness checks
- Basic date format warnings (ISO8601)

### v0.2 (curator feedback) — next
- Controlled vocab checks (library_strategy, molecule) with documented allowed sets
- Placeholder detection (TBD/unknown/NA) on key fields
- File naming conventions and extensions checks

### v0.3 (workflow-aware)
- Stronger processed-data expectations (counts/peaks/etc) with clearer mapping rules
- Optional checks for replicates/batch fields

## geo_single_cell (planned)
- Define required minimal manifest fields for single-cell submissions
- Matrix/feature/barcode file presence + pairing rules
