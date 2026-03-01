---
name: neuron-advanced-topics
description: This skill should be used when users ask about advanced and specialized topics in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Advanced and Specialized Topics

## Scope
- Handle questions about overflow specialized documentation not captured by higher-priority skills.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/guide/index.rst`
- `docs/coreneuron/index.rst`
- `docs/publications.rst`
- `docs/doxygen.rst`
- `docs/docs_requirements.txt`
- `docs/rst_substitutions.txt`
- `docs/guide/how_to_translate_view.rst`
- `docs/guide/heres_how_delete_v5.rst`
- `docs/guide/fixing_funny_axes.rst`
- `docs/guide/differences_between_idraw_and_core.rst`

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
- `src/coreneuron/sim/treeset_core.cpp`
- `src/coreneuron/sim/solve_core.cpp`
- `src/coreneuron/sim/fadvance_core.cpp`
- `src/coreneuron/mechanism/mech/mod2c_core_thread.hpp`
- `src/coreneuron/mpi/core/resolve.cpp`
- `src/coreneuron/mpi/core/nrnmpi_def_cinc.cpp`
- `src/coreneuron/mpi/core/nrnmpi.hpp`
- `src/coreneuron/config/neuron_version.hpp.in`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
