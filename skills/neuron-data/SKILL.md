---
name: neuron-data
description: This skill should be used when users ask about data in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Data

## Scope
- Handle questions about documentation grouped under the 'data' theme.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/guide/data/readme.txt`
- `docs/guide/data/units.dat.txt`
- `docs/guide/data/solution.ses.txt`
- `docs/guide/data/idraw-readme.txt`
- `docs/guide/data/finithnd1.hoc.txt`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- Use tutorials/examples as executable usage patterns when available.
- Use tests as behavior or regression references when available.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Tutorials and examples
- `docs/courses`
- `docs/rxd-tutorials`
- `docs/tutorials`
- `share/demo`
- `share/examples`
- `src/nrnpython/examples`

## Test references
- `test`
- `share/lib/python/neuron/rxdtests`
- `share/lib/python/neuron/tests`

## Optional deeper inspection
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

## Source entry points for unresolved issues
- `src/neuron/model_data_fwd.hpp`
- `src/neuron/model_data.hpp`
- `src/neuron/cache/model_data.hpp`
- `src/coreneuron/io/nrn2core_data_init.cpp`
- `src/coreneuron/io/core2nrn_data_return.hpp`
- `src/coreneuron/io/core2nrn_data_return.cpp`
- `src/nmodl/utils/table_data.hpp`
- `src/nmodl/utils/table_data.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
