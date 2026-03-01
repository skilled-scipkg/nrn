---
name: neuron-examples-and-tutorials
description: This skill should be used when users ask about examples and tutorials in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Examples and Tutorials

## Scope
- Handle questions about worked examples, tutorials, and cookbook usage.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/progref/programming/projectmanagement.rst`
- `docs/dev/HOCInterpreter/HOCInterpreter.md`
- `docs/otherscripting.rst`
- `docs/guide/finitialize_handler.rst`
- `docs/guide/tutorial_artificial_neurons.rst`
- `docs/guide/tutorial_2_hybrid_nets.rst`
- `docs/videos/cns-tutorial-2021.rst`
- `docs/coreneuron/examples.rst`

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
- `src/coreneuron/sim/finitialize.cpp`
- `src/coreneuron/io/reports/sonata_report_handler.hpp`
- `src/coreneuron/io/reports/sonata_report_handler.cpp`
- `src/coreneuron/io/reports/report_handler.hpp`
- `src/coreneuron/io/reports/report_handler.cpp`
- `src/coreneuron/io/nrn_filehandler.hpp`
- `src/coreneuron/io/nrn_filehandler.cpp`
- `src/coreneuron/config/neuron_version.hpp.in`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
