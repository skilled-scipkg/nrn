# neuron source map: Using The D Lambda Rule

Generated from source roots:
- `src`
- `share/lib/hoc`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `d_lambda`
- `lambda_f`
- `nseg`
- `discretization`

## Fast source navigation
- `rg -n "lambda_f|geom_nseg|d_lambda|nseg" share/lib/hoc src/nrnoc src/nrnpython src/nrniv`
- `rg -n "nrn_change_nseg|nseg must" src/nrnoc src/nrnpython src/nrniv`

## Suggested source entry points
- `share/lib/hoc/stdlib.hoc` | `lambda_f()` implementation used by d_lambda workflows
- `share/lib/hoc/celbild/celgeom.hoc` | `geom_nseg` generation and d_lambda GUI/export logic
- `src/nrnoc/cabcode.cpp` | authoritative `nseg` mutation rules and validation
- `src/nrnoc/solve.cpp` | node allocation/reallocation consequences of `nseg` changes
- `src/nrnoc/init.cpp` | defaults/bounds for `nseg` and related setup checks
- `src/nrnpython/nrnpy_nrn.cpp` | Python attribute path for reading/writing section `nseg`
- `src/nrniv/neuronapi.cpp` | C API-level `nrn_nseg_get`/`nrn_nseg_set` behavior
- `share/lib/python/neuron/gui2/utilities.py` | GUI utility calculations that depend on `nseg`
