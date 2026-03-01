---
name: neuron-parallel-hpc
description: This skill should be used when users ask about parallel and hpc in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Parallel and HPC

## Scope
- Handle questions about MPI/OpenMP/GPU execution, scaling, and batch systems.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/coreneuron/compatibility.rst`
- `docs/progref/compilationoptions.rst`

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
- `src/coreneuron/mpi/nrnmpiuse.h`
- `src/coreneuron/mpi/nrnmpidec.h`
- `src/coreneuron/mpi/nrnmpi.h`
- `src/coreneuron/gpu/nrn_acc_manager.hpp`
- `src/coreneuron/gpu/nrn_acc_manager.cpp`
- `src/coreneuron/mpi/lib/nrnmpi.hpp`
- `src/coreneuron/mpi/lib/nrnmpi.cpp`
- `src/coreneuron/mpi/lib/mpispike.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
