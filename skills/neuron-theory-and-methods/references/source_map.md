# neuron source map: Theory and Methods

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `algorithm`
- `cable`
- `contents`
- `courses`
- `derivation`
- `equation`
- `equations`
- `exercises`
- `formalism`
- `method`
- `methods`
- `nmodl`
- `numerical`
- `theory`
- `transpiler`

## Fast source navigation
- `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`
- `rg -n "class|def|struct|namespace" bin src packaging/python share/lib/python`
- If a doc mentions a function/class, search that exact symbol first, then inspect nearby implementation files.

## Suggested source entry points
- `src/nmodl/visitors/solve_without_method_visitor.hpp` | score: 10 | matched tokens: method, nmodl
- `src/nmodl/visitors/solve_without_method_visitor.cpp` | score: 10 | matched tokens: method, nmodl
- `src/nmodl/visitors/neuron_solve_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/neuron_solve_visitor.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/main.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/sympy_solver_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/sympy_solver_visitor.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/main.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/parser/main_units.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/parser/main_nmodl.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/parser/main_c.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/lexer/main_units.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/lexer/main_nmodl.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/lexer/main_c.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.cpp` | score: 5 | matched tokens: nmodl
- `share/lib/python/neuron/nmodl/__init__.py` | score: 5 | matched tokens: nmodl
- `src/oc/equation.h` | score: 5 | matched tokens: equation
- `src/nmodl/CMakeLists.txt` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/visitor_utils.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/visitor_utils.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/verbatim_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/verbatim_visitor.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/verbatim_var_rename_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/verbatim_var_rename_visitor.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/var_usage_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/var_usage_visitor.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/units_visitor.hpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/units_visitor.cpp` | score: 5 | matched tokens: nmodl
- `src/nmodl/visitors/symtab_visitor_helper.hpp` | score: 5 | matched tokens: nmodl
