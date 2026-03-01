---
name: neuron-courses
description: This skill should be used when users ask about courses in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Courses

## Scope
- Handle questions about documentation grouped under the 'courses' theme.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/courses/neuron_scripting_exercises.rst`
- `docs/courses/saving_windows.rst`
- `docs/courses/rxd_exercises.rst`
- `docs/courses/using_nmodl_files.rst`
- `docs/courses/using_nsg_portal.rst`
- `docs/courses/exercises2018.rst`
- `docs/courses/artificial_cells_neuron.rst`
- `docs/courses/code/test0.hoc.txt`
- `docs/courses/code/net2spec.ho.txt`
- `docs/courses/code/net1spec.ho.txt`
- `docs/courses/code/initbatser.ho.txt`
- `docs/courses/code/initbatpar.ho.txt`

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
- `src/nmodl/printer/code_printer.hpp`
- `src/nmodl/printer/code_printer.cpp`
- `src/nmodl/language/code_generator_opts.in`
- `src/nmodl/language/code_generator.py`
- `src/nmodl/language/templates/code_generator.cmake`
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.hpp`
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.cpp`
- `src/nrnpython/rxd_intracellular.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
