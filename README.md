# FAIRy GEO Rulepacks (CC0)
Community-shareable rulepacks for validating datasets intended for submission to **NCBI GEO** using the **FAIRy** engine.

## Quick look

**Preflight (GEO bulk-seq)** — generate a submission readiness report from the included fixtures.

![FAIRy GEO preflight example](docs/assets/preflight_cli.png)

## Quickstart (copy/paste)

Run a complete **submission-readiness** check using the included tiny fixtures (`samples.tsv` + `files.tsv`).

> Tip: This repo includes both a PASS fixture and an intentionally failing fixture so you can see what findings look like.

### 1) Install FAIRy (engine)
FAIRy is currently installed from source (editable install):

```bash
# from wherever you keep projects
git clone https://github.com/yuummmer/fairy-core.git
cd fairy-core

python -m venv .venv && source .venv/bin/activate
pip install -e .

fairy --help

# 2) From this FAIRy-rulepacks-geo repo:
mkdir -p .tmp

# PASS example (smoke test)
fairy preflight \
  --rulepack rulepacks/geo_bulk_seq/v0_2_0.json \
  --samples  rulepacks/geo_bulk_seq/fixtures/samples.tsv \
  --files    rulepacks/geo_bulk_seq/fixtures/files.tsv \
  --out      .tmp/geo_bulk_seq_pass.json

# FAIL/WARN example (recommended demo)
fairy preflight \
  --rulepack rulepacks/geo_bulk_seq/v0_2_0.json \
  --samples  rulepacks/geo_bulk_seq/fixtures/samples_bad.tsv \
  --files    rulepacks/geo_bulk_seq/fixtures/files.tsv \
  --out      .tmp/geo_bulk_seq_fail.json

# Inspect outputs
ls -la .tmp/
head -n 60 .tmp/geo_bulk_seq_fail.json

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