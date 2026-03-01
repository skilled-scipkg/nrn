---
name: neuron-publications-using-neuron
description: This skill should be used when users ask about publications using neuron in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Publications Using Neuron

## Scope
- Handle questions about publication references and reproducibility expectations for NEURON-based studies.
- Keep responses practical for reproducing reported simulations and outputs.

## Primary documentation references
- `docs/publications-using-neuron.rst`

## Quick reproducibility playbook
1. Select one publication/model target and record runtime provenance:
```bash
nrniv -nobanner -c 'nrnversion()' -c 'nrnversion(7)' -c 'quit()'
```
2. Run a minimal reproduction script with fixed random streams (if stochastic).
3. Export one deterministic output artifact (e.g., spike times or voltage trace).
4. Compare key metrics across two reruns before scaling the experiment.

## Validation checkpoints
- Same input seed/config yields matching metrics across reruns.
- Output format and units align with the publication claim.
- Runtime provenance (version/options) is captured with results.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnoc/fadvance.cpp`
- `src/nrncvode/netcvode.cpp`
- `src/nrniv/prcellstate.cpp`
- `src/nrniv/savstate.cpp`
- `src/coreneuron/io/output_spikes.cpp`
- `src/coreneuron/io/reports/report_handler.cpp`
- `src/nrnoc/nrnversion.cpp`
- `src/coreneuron/config/neuron_version.hpp.in`
- Prefer targeted source search (for example: `rg -n "SaveState|prcellstate|output_spikes|report" src/nrniv src/coreneuron`).
