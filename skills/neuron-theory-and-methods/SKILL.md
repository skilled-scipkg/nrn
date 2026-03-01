---
name: neuron-theory-and-methods
description: This skill should be used when users ask about theory and methods in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Theory and Methods

## Scope
- Handle questions about theoretical background and algorithmic methods.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/courses/numerical-methods-exercises.rst`
- `docs/nmodl/transpiler/contents/cable_equations.rst`

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
- `src/nmodl/visitors/solve_without_method_visitor.hpp`
- `src/nmodl/visitors/solve_without_method_visitor.cpp`
- `src/nmodl/visitors/neuron_solve_visitor.hpp`
- `src/nmodl/visitors/neuron_solve_visitor.cpp`
- `src/nmodl/main.cpp`
- `src/nmodl/visitors/sympy_solver_visitor.hpp`
- `src/nmodl/visitors/sympy_solver_visitor.cpp`
- `src/nmodl/visitors/main.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
