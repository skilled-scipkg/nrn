# neuron source map: Getting Started

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `2021`
- `basics`
- `builder`
- `cellbuilder`
- `channel`
- `chapter`
- `circuit`
- `cmake`
- `compact`
- `course`
- `courses`
- `custom`
- `data`
- `dev`
- `display`
- `dist`
- `geometry`
- `get`
- `getting`
- `gui`
- `hints`
- `hoc`
- `hocdomain`
- `import3d`
- `inhomogeneous`
- `initialization`
- `intro`
- `introduction`
- `language`
- `linear`

## Fast source navigation
- `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`
- `rg -n "class|def|struct|namespace" bin src packaging/python share/lib/python`
- If a doc mentions a function/class, search that exact symbol first, then inspect nearby implementation files.

## Suggested source entry points
- `src/nmodl/language/templates/code_generator.cmake` | score: 15 | matched tokens: cmake, language, nmodl
- `src/nmodl/language/CMakeLists.txt` | score: 12 | matched tokens: cmake, language, nmodl
- `src/nmodl/utils/table_data.hpp` | score: 10 | matched tokens: data, nmodl
- `src/nmodl/utils/table_data.cpp` | score: 10 | matched tokens: data, nmodl
- `src/nmodl/language/utils.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/nodes.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/node_info.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/language_parser.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/code_generator_opts.in` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/code_generator.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/argument.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/symtab_visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/symtab_visitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/nmodl_visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/nmodl_visitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/lookup_visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/lookup_visitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/json_visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/json_visitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/checkparent_visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/checkparent_visitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/ast_visitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/visitors/ast_visitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/pybind/pyvisitor.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/pybind/pyvisitor.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/pybind/pysymtab.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/pybind/pynode.cpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/pybind/pyast.hpp` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/templates/pybind/pyast.cpp` | score: 10 | matched tokens: language, nmodl
