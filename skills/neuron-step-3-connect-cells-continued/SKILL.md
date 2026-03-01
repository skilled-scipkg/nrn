---
name: neuron-step-3-connect-cells-continued
description: This skill should be used when users ask about step 3 connect cells continued in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Step 3 Connect Cells Continued

## Scope
- Handle advanced connection-parameter and event-routing questions for multi-cell NEURON models.
- Keep guidance tied to runnable connectivity checks.

## Primary documentation references
- `docs/guide/step_3_connect_cells_continued.rst`

## Quick simulation-start playbook
1. Create a two-cell event path and run a short test:
```python
from neuron import h
h.load_file("stdrun.hoc")
pre = h.NetStim(); pre.start = 1; pre.number = 4; pre.interval = 8
soma = h.Section(name="soma"); soma.insert("hh")
syn = h.ExpSyn(soma(0.5))
nc = h.NetCon(pre, syn); nc.weight[0] = 0.002; nc.delay = 0.5
h.finitialize(-65); h.continuerun(50)
print("events configured with delay", nc.delay)
```
2. Record one output metric (spikes or membrane trace) for comparison.
3. If event ordering/parallel behavior is unclear, inspect `references/source_map.md`.

## Validation checkpoints
- Run reaches `tstop` with no event-queue warnings.
- Parameter edits (weight/delay) visibly affect output.
- Serial reruns with same inputs are deterministic.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrncvode/netcvode.cpp`
- `src/nrncvode/netcon.h`
- `src/nrniv/partrans.cpp`
- `src/nrniv/multisend_setup.cpp`
- `src/coreneuron/io/setup_fornetcon.cpp`
- `src/coreneuron/network/netcon.hpp`
- `src/coreneuron/network/netcvode.cpp`
- `src/nrniv/prcellstate.cpp`
- Prefer targeted source search (for example: `rg -n "NetCon|PreSyn|weight|delay|setup_fornetcon" src/nrncvode src/nrniv src/coreneuron`).
