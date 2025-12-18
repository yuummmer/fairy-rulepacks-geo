# FAIRy GEO Rulepacks (CC0)

This repo contains community-shareable rulepacks for validating datasets intended for submission to GEO.

## Rulepacks
- `rulepacks/geo_bulk_seq/` — GEO bulk RNA-seq style uploads (starter profile)

## How to use
1) Install FAIRy (from `fairy-core`)
2) Clone this repo
3) Run FAIRy pointing at the rulepack you want

## Example (adjust flags to your CLI):

```bash
fairy validate --rulepack rulepacks/geo_bulk_seq --input path/to/your.csv
```
## Versioning

Rulepacks version independently from `fairy-core`. See each rulepack folder for its version(s).

## License

Rulepacks and fixtures in this repository are released under CC0-1.0.