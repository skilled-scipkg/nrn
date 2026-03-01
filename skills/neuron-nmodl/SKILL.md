---
name: neuron-nmodl
description: This skill should be used when users ask about nmodl in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Nmodl

## Scope
- Handle questions about documentation grouped under the 'nmodl' theme.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/nmodl/transpiler/index.rst`
- `docs/nmodl/transpiler/notebooks/README.rst`
- `docs/nmodl/language/nmodl_neuron_extension.rst`
- `docs/nmodl/transpiler/nmodl.rst`
- `docs/nmodl/transpiler/contents/ions.rst`
- `docs/nmodl/transpiler/test_status.txt`
- `docs/nmodl/transpiler/notebooks.rst`
- `docs/nmodl/transpiler/contents/currents.rst`
- `docs/nmodl/transpiler/contents/pointers.rst`
- `docs/nmodl/transpiler/contents/longitudinal_diffusion.rst`
- `docs/nmodl/transpiler/contents/cvode.rst`

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
- `src/nmodl/visitors/longitudinal_diffusion_visitor.hpp`
- `src/nmodl/visitors/longitudinal_diffusion_visitor.cpp`
- `src/nmodl/visitors/cvode_visitor.hpp`
- `src/nmodl/visitors/cvode_visitor.cpp`
- `src/nmodl/visitors/after_cvode_to_cnexp_visitor.hpp`
- `src/nmodl/visitors/after_cvode_to_cnexp_visitor.cpp`
- `src/nmodl/language/utils.py`
- `src/nmodl/language/nodes.py`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
