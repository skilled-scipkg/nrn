# neuron source map: Build and Install

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `2022`
- `bio`
- `brody`
- `build`
- `cellb`
- `cellbuilder1`
- `cellbuilder2`
- `cells`
- `cmake`
- `cmakelists`
- `code`
- `compile`
- `courses`
- `coverage`
- `debug`
- `dependencies`
- `faq`
- `formatting`
- `generating`
- `hopfield`
- `incfcns`
- `install`
- `installation`
- `instructions`
- `mac`
- `make`
- `movie`
- `network`
- `nmodl`
- `nrnivmodl`

## Fast source navigation
- `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`
- `rg -n "class|def|struct|namespace" bin src packaging/python share/lib/python`
- If a doc mentions a function/class, search that exact symbol first, then inspect nearby implementation files.

## Suggested source entry points
- `src/nmodl/codegen/CMakeLists.txt` | score: 26 | matched tokens: cmake, cmakelists, code, make, nmodl
- `src/nmodl/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/mac/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, mac, make
- `src/nmodl/visitors/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/utils/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/symtab/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/solver/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/pybind/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/printer/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/parser/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/lexer/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/language/CMakeLists.txt` | score: 24 | matched tokens: cmake, cmakelists, make, nmodl
- `src/nmodl/language/templates/code_generator.cmake` | score: 21 | matched tokens: cmake, code, make, nmodl
- `bin/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/sparse13/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/nrnpython/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/nrniv/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/neuronmusic/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/mswin/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/gnu/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `src/coreneuron/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `share/lib/python/scripts/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `share/lib/python/neuron/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `share/lib/python/neuron/rxd/geometry3d/CMakeLists.txt` | score: 19 | matched tokens: cmake, cmakelists, make
- `bin/nrnivmodl_makefile_cmake.in` | score: 16 | matched tokens: cmake, make, nrnivmodl
- `bin/nrnivmodl-cmake.in` | score: 16 | matched tokens: cmake, make, nrnivmodl
- `bin/nrnivmodl_core_makefile.in` | score: 11 | matched tokens: make, nrnivmodl
- `src/nmodl/printer/code_printer.hpp` | score: 10 | matched tokens: code, nmodl
- `src/nmodl/printer/code_printer.cpp` | score: 10 | matched tokens: code, nmodl
- `src/nmodl/language/code_generator_opts.in` | score: 10 | matched tokens: code, nmodl
