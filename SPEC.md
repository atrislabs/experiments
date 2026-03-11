# SPEC

The `experiments` framework exists to make self-improvement loops honest.

## Contract

Every experiment pack must provide:

- `program.md` - human intent
- `measure.py` - machine-checkable truth
- `loop.py` - keep/revert execution loop
- `results.tsv` - append-only trial history

Preferred:

- `reset.py` - restore broken or baseline state
- `proposals/` - deterministic mutations for demos and tests

## Keep/Revert Standard

An experiment is only valid if it can reject a loser and keep a winner.

## Promotion Standard

This framework repo owns the schema.
Product repos own concrete packs under `atris/experiments/`.
