---
name: neuron-step-1-define-type-of-cell2
description: This skill should be used when users ask about step 1 define type of cell2 in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Step 1 Define Type Of Cell2

## Scope
- Handle questions about defining synapse-capable cell types and early network wiring primitives.
- Keep workflows runnable and immediately verifiable with a minimal event-driven simulation.

## Primary documentation references
- `docs/guide/step_1_define_type_of_cell2.rst`

## Quick simulation-start playbook
1. Build a minimal source->target synapse setup:
```python
from neuron import h
h.load_file("stdrun.hoc")
pre = h.NetStim(); pre.start = 1; pre.number = 5; pre.interval = 10; pre.noise = 0
soma = h.Section(name="soma"); soma.insert("hh")
syn = h.ExpSyn(soma(0.5))
nc = h.NetCon(pre, syn); nc.weight[0] = 0.001; nc.delay = 1
h.finitialize(-65); h.continuerun(60)
print("weight", nc.weight[0], "delay", nc.delay)
```
2. Confirm event source/target types and NetCon parameters.
3. Escalate to source for delivery-queue or attach semantics only if needed.

## Validation checkpoints
- NetCon weight/delay match intended values.
- Simulation reaches target `tstop` without event-delivery errors.
- Re-running with same parameters gives stable event timing.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnoc/netstim.mod`
- `src/coreneuron/mechanism/mech/modfile/netstim.mod`
- `src/nrncvode/netcon.h`
- `src/nrncvode/netcvode.cpp`
- `src/nrnoc/point.cpp`
- `src/nrnoc/treeset.cpp`
- `src/coreneuron/network/netcon.hpp`
- `src/coreneuron/network/netcvode.cpp`
- Prefer targeted source search (for example: `rg -n "NetStim|noiseFromRandom123|NetCon|PreSyn" src/nrnoc src/nrncvode src/coreneuron`).
