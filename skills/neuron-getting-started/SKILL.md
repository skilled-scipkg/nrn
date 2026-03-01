---
name: neuron-getting-started
description: This skill should be used when users ask about getting started in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Getting Started

## Scope
- Handle questions about initial setup, quickstarts, and core concepts.
- Keep responses abstract and architectural for large codebases; avoid exhaustive per-function documentation unless requested.

## Primary documentation references
- `docs/courses/intro_to_the_network_builder.rst`
- `docs/courses/intro_to_gui.rst`
- `docs/guide/modelview_compact_display.rst`
- `docs/guide/import3d.rst`
- `docs/courses/custom-initialization.rst`
- `docs/videos/netpyne-course-2021.rst`
- `docs/guide/hoc_chapter_11_old_reference.rst`
- `docs/dev/hocdomain-sphinx.md`
- `docs/dev/data-structures.rst`
- `docs/courses/the_cellbuilder.rst`
- `docs/cmake_doc/options.rst`
- `docs/scm/guide/SCMGuide.md`

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
- `src/nmodl/language/templates/code_generator.cmake`
- `src/nmodl/language/CMakeLists.txt`
- `src/nmodl/utils/table_data.hpp`
- `src/nmodl/utils/table_data.cpp`
- `src/nmodl/language/utils.py`
- `src/nmodl/language/nodes.py`
- `src/nmodl/language/node_info.py`
- `src/nmodl/language/language_parser.py`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`).
