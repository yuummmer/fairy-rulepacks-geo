# FAIRy GEO Rulepacks (CC0)
Community-shareable rulepacks for validating datasets intended for submission to **NCBI GEO** using the **FAIRy** engine.

## Quick look

**Preflight (GEO bulk-seq)** — generate a submission readiness report from the included fixtures.

![FAIRy GEO preflight example](docs/assets/preflight_cli.png)

## Quickstart (copy/paste)
Run a complete **submission-readiness** check using the included tiny fixtures (`samples.tsv` + `files.tsv`).

```bash
# 1) Install FAIRy (engine)
# See: https://github.com/yuummmer/fairy-core
# (After install, you should have: fairy --help)

# 2) From this repo:
mkdir -p .tmp

fairy preflight \
  --rulepack rulepacks/geo_bulk_seq/v0_2_0.json \
  --samples  rulepacks/geo_bulk_seq/fixtures/samples.tsv \
  --files    rulepacks/geo_bulk_seq/fixtures/files.tsv \
  --out      .tmp/geo_bulk_seq_report.json

# Outputs:
ls .tmp/
less .tmp/geo_bulk_seq_report.md   # press q to quit (or open in your editor)

cat .tmp/geo_bulk_seq_report.json | head
```
Why **preflight**? GEO submissions are a _package_, not a single file. Preflight checks the full submission object (multiple tables + consistency) and reports whether it is **submission ready**.

## Run on your own GEO submission metadata
Prepare two TSVs matching the fixture schemas:

- `samples.tsv` — one row per biological sample
- `files.tsv` — one row per data file, linked to samples

```bash
mkdir -p .tmp

fairy preflight \
  --rulepack rulepacks/geo_bulk_seq/v0_2_0.json \
  --samples  /path/to/your/samples.tsv \
  --files    /path/to/your/files.tsv \
  --out      .tmp/geo_bulk_seq_report.json

```
## Rulepacks
- `rulepacks/geo_bulk_seq/` — GEO bulk RNA-seq style uploads (starter profile)
Rulepacks are versioned independently from fairy-core. Use the explicit version file (e.g. v0_2_0.json) for reproducible results.

## License

Rulepacks and fixtures in this repository are released under CC0-1.0.