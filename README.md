# experiments

Karpathy-style experiment framework for Atris.

This repo defines the schema, validation rules, and benchmark harness for self-improvement loops.
Live experiment packs belong inside product repos at `atris/experiments/`.

## Schema

```text
atris/experiments/
├── README.md
├── validate.py
├── benchmark_validate.py
├── benchmark_runtime.py
└── <experiment-slug>/
    ├── program.md
    ├── measure.py
    ├── loop.py
    ├── results.tsv
    ├── reset.py            # preferred
    ├── proposals/          # optional
    └── <bounded-target>    # candidate.py, system_prompt.txt, etc.
```

## Rules

1. One bounded mutation target per experiment.
2. `measure.py` must use an external metric the agent cannot fake.
3. `loop.py` must keep only improvements and revert regressions.
4. `program.md` stays short and task-specific.
5. `results.tsv` stays append-only.

## Repo Contents

- `template/pack/` - starter files for a new experiment
- `validate.py` - structural and bloat checks
- `benchmark_validate.py` - validator benchmark on fixed good/bad fixtures
- `benchmark_runtime.py` - runtime benchmark on example packs
- `examples/` - tiny reference implementation

## Commands

```bash
python validate.py examples
python benchmark_validate.py
python benchmark_runtime.py
```
