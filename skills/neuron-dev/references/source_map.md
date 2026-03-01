# neuron source map: Dev

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `dev`
- `morphology`
- `api`
- `section`

## Fast source navigation
- `rg -n "nseg|nrn_change_nseg|Section|topology" src/nrnoc src/nrnpython src/nrniv`
- `rg -n "shape|PlotShape|psection" src/nrniv share/lib/python/neuron`

## Suggested source entry points
- `src/nrnpython/nrnpy_nrn.cpp` | Python `Section`/segment attribute behavior (`nseg`, section properties)
- `src/nrnoc/cabcode.cpp` | core section geometry and `nseg` mutation logic
- `src/nrnoc/solve.cpp` | node allocation/reallocation after topology or `nseg` changes
- `src/nrniv/neuronapi.cpp` | C API wrappers (`nrn_nseg_get`, `nrn_nseg_set`) used by tooling
- `src/nrnoc/psection.cpp` | section introspection and printable model state paths
- `src/nrniv/shape.cpp` | shape rendering/state save path for morphology debugging
- `src/nrniv/ppshape.cpp` | point-process shape overlays used in GUI checks
- `share/lib/python/neuron/psection.py` | Python-side section inspection formatting/fields
