---
name: neuron-set-up-a-subsetdomainiterator
description: This skill should be used when users ask about set up a subsetdomainiterator in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Set Up A Subsetdomainiterator

## Scope
- Handle questions about documentation grouped under the 'set-up-a-subsetdomainiterator' theme.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/guide/set_up_a_subsetdomainiterator.rst`

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
- `src/nrnoc/treeset.h`
- `src/nrnoc/treeset.cpp`
- `src/nrniv/multisend_setup.cpp`
- `src/nrncvode/cvtrset.cpp`
- `src/mswin/pre_setup_exe.sh.in`
- `src/mswin/nrnsetupmingw.nsi.in`
- `src/coreneuron/network/partrans_setup.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
