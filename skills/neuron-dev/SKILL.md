---
name: neuron-dev
description: This skill should be used when users ask about dev in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Dev

## Scope
- Handle developer-facing questions linked to internal APIs, morphology internals, and section/segment behavior.
- Prefer docs-first guidance and escalate to source when behavior is implementation-sensitive.

## Primary documentation references
- `docs/dev/how-do-i/how-do-i.rst`
- `docs/dev/morphology/morphology.rst`

## Quick simulation-start playbook
1. Build a minimal section-based model and run one short step:
```bash
python3 - <<'PY'
from neuron import h
h.load_file("stdrun.hoc")
s = h.Section(name="soma")
s.L = s.diam = 12.6
s.insert("hh")
h.finitialize(-65)
h.continuerun(1)
print("v(0.5)=", s(0.5).v)
PY
```
2. Use `psection()`/`topology()` output to confirm geometry and mechanism insertion.
3. Escalate to source only if observed runtime behavior differs from docs.

## Validation checkpoints
- `v(0.5)` is finite after `continuerun`.
- `nseg`, `L`, `diam`, and inserted mechanisms match intended setup.
- Topology/section state is stable across repeated short runs.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnpython/nrnpy_nrn.cpp`
- `src/nrnoc/cabcode.cpp`
- `src/nrnoc/solve.cpp`
- `src/nrniv/neuronapi.cpp`
- `src/nrnoc/psection.cpp`
- `src/nrniv/shape.cpp`
- `src/nrniv/ppshape.cpp`
- `share/lib/python/neuron/psection.py`
- Prefer targeted source search (for example: `rg -n "nseg|nrn_change_nseg|Section|topology" src/nrnoc src/nrnpython src/nrniv`).
