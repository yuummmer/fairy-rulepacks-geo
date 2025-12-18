# Contributing to FAIRy GEO rulepacks

Thanks for helping improve FAIRy’s GEO rulepacks! This repository is **CC0-1.0** so rulepacks can be reused widely.

## What to contribute
- New/updated rules in `rulepacks/**/v*.json`
- Tiny fixtures in `rulepacks/**/fixtures/`
- Documentation improvements (README updates, examples, troubleshooting)

## Local smoke test
You’ll need FAIRy installed from `fairy-core`.

From this repo root:

```bash
fairy preflight \
  --rulepack rulepacks/geo_bulk_seq/v0_1_0.json \
  --samples  rulepacks/geo_bulk_seq/fixtures/samples.tsv \
  --files    rulepacks/geo_bulk_seq/fixtures/files.tsv \
  --out      out/report.json
```

## Fixture guidelines
- Keep fixtures tiny (a few rows)
- Prefer adding a focused failing fixture when adding a new rule
- Make sure fixtures are safe to share publicly (no real sample IDs / PHI)

## Versioning
- Patch bump for clarifications/fixture tweaks
- Minor bump for new rules or behavior changes that may add WARN/FAIL

## License
By contributing to this repo, you agree your contributions are released under *CC0-1.0*.