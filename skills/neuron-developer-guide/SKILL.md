---
name: neuron-developer-guide
description: This skill should be used when users ask about developer guide in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Developer Guide

## Scope
- Handle questions about developer architecture, extension points, and contribution workflow.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/dev/index.rst`
- `docs/nmodl/transpiler/contributing.rst`
- `docs/scm/guidelines/SCMGuidelines.md`
- `docs/progref/programming/internals.rst`
- `docs/guide/step_3_connect_the_cells.rst`
- `docs/guide/step_3_connect_cells.rst`

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
- `src/nmodl/visitors/neuron_solve_visitor.hpp`
- `src/nmodl/visitors/neuron_solve_visitor.cpp`
- `src/nmodl/main.cpp`
- `src/nmodl/visitors/sympy_solver_visitor.hpp`
- `src/nmodl/visitors/sympy_solver_visitor.cpp`
- `src/nmodl/visitors/main.cpp`
- `src/nmodl/parser/main_units.cpp`
- `src/nmodl/parser/main_nmodl.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
