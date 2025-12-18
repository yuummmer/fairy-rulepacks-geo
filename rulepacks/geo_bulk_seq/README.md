# geo_bulk_seq

Starter **GEO bulk-seq** rulepack for FAIRy.

## Files
- `v0_1_0.json` — rulepack definition (JSON)

## Fixtures
This rulepack expects two tab-separated manifests:

- `fixtures/samples.tsv` — one row per biological sample
- `fixtures/files.tsv` — one row per file, mapped to `sample_id`

## Quick test (from fairy-core)
```bash
fairy preflight \
  --rulepack /path/to/fairy-rulepacks-geo/rulepacks/geo_bulk_seq/v0_1_0.json \
  --samples  /path/to/fairy-rulepacks-geo/rulepacks/geo_bulk_seq/fixtures/samples.tsv \
  --files    /path/to/fairy-rulepacks-geo/rulepacks/geo_bulk_seq/fixtures/files.tsv \
  --out out/geo_bulk_seq_report.json
```

## Notes
This is a starter profile and will evolve as additional GEO bulk-seq cases are added.