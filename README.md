# viva-munk-studies

[![workspace-ci](https://github.com/vivarium-collective/viva-munk-studies/actions/workflows/workspace-ci.yml/badge.svg)](https://github.com/vivarium-collective/viva-munk-studies/actions/workflows/workspace-ci.yml)

The **studies and investigations** for [viva-munk](https://github.com/vivarium-collective/viva-munk) —
pymunk-based 2D multi-cell physics — as a vivarium-workbench workspace.

The **simulator** lives in [`viva-munk`](https://github.com/vivarium-collective/viva-munk)
(the `viva_munk` package). This repo holds only the investigation content:
`studies/`, `investigations/`, and `workspace.yaml`. Each `study.yaml` pins the
simulator it ran against — `simulator: {package: viva-munk, ref, registry: git}` —
so every result is reproducible against an exact simulator version.

## Studies

`attachment`, `bending-pressure`, `biofilm`, `chemotaxis`, `daughter-machine`,
`glucose-growth`, `inclusion-bodies`, `mother-machine`, `quorum-sensing` — each
exercises a `viva_munk.composites.*` composite.

## Run / browse

```bash
uv sync                 # installs the pinned simulator (viva-munk) + workbench
# browse the studies and results in the vivarium-workbench, or run a study's
# composite directly via the viva_munk experiment runner.
```

## Relationship to viva-munk

- `viva-munk` — the simulator package (`viva_munk`): processes, composites,
  visualizations. Other repos (`sms-ecoli`, `v2ecoli`, `viva-tumor-tcell`,
  `mosaic-compose`, `viva-multicell-blueprint`, `viva-casebook`) depend on it.
- `viva-munk-studies` (this repo) — the investigation workspace that *uses* the
  simulator, pinned per study. Extracted from `viva-munk` with `git filter-repo`
  (studies + investigations, full history preserved).
