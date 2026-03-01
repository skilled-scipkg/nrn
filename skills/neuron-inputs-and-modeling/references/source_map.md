# neuron source map: Inputs and Modeling

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `basis`
- `batch`
- `board`
- `boundary`
- `bulletin`
- `cell`
- `channel`
- `coreneuron`
- `courses`
- `data`
- `define`
- `dis`
- `discontinuities`
- `field`
- `force`
- `forcefield`
- `geometry`
- `guitools`
- `heres`
- `idraw`
- `inhomogeneous`
- `input`
- `inputs`
- `interactive`
- `language`
- `material`
- `model`
- `modeldb`
- `modeling`
- `modelspec`

## Fast source navigation
- `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`
- `rg -n "class|def|struct|namespace" bin src packaging/python share/lib/python`
- If a doc mentions a function/class, search that exact symbol first, then inspect nearby implementation files.

## Suggested source entry points
- `src/nmodl/visitors/state_discontinuity_visitor.hpp` | score: 12 | matched tokens: dis, nmodl, state
- `src/nmodl/visitors/state_discontinuity_visitor.cpp` | score: 12 | matched tokens: dis, nmodl, state
- `src/neuron/model_data_fwd.hpp` | score: 10 | matched tokens: data, model
- `src/neuron/model_data.hpp` | score: 10 | matched tokens: data, model
- `src/nmodl/parser/main_units.cpp` | score: 10 | matched tokens: nmodl, units
- `src/nmodl/lexer/main_units.cpp` | score: 10 | matched tokens: nmodl, units
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.hpp` | score: 10 | matched tokens: coreneuron, nmodl
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.cpp` | score: 10 | matched tokens: coreneuron, nmodl
- `src/neuron/cache/model_data.hpp` | score: 10 | matched tokens: data, model
- `src/coreneuron/io/nrn2core_data_init.cpp` | score: 10 | matched tokens: coreneuron, data
- `src/coreneuron/io/core2nrn_data_return.hpp` | score: 10 | matched tokens: coreneuron, data
- `src/coreneuron/io/core2nrn_data_return.cpp` | score: 10 | matched tokens: coreneuron, data
- `src/nmodl/visitors/units_visitor.hpp` | score: 10 | matched tokens: nmodl, units
- `src/nmodl/visitors/units_visitor.cpp` | score: 10 | matched tokens: nmodl, units
- `src/nmodl/utils/table_data.hpp` | score: 10 | matched tokens: data, nmodl
- `src/nmodl/utils/table_data.cpp` | score: 10 | matched tokens: data, nmodl
- `src/nmodl/units/units.hpp` | score: 10 | matched tokens: nmodl, units
- `src/nmodl/units/units.cpp` | score: 10 | matched tokens: nmodl, units
- `src/nmodl/language/utils.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/nodes.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/node_info.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/language_parser.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/code_generator_opts.in` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/code_generator.py` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/CMakeLists.txt` | score: 10 | matched tokens: language, nmodl
- `src/nmodl/language/argument.py` | score: 10 | matched tokens: language, nmodl
- `src/coreneuron/utils/units.hpp` | score: 10 | matched tokens: coreneuron, units
- `src/coreneuron/permute/data_layout.hpp` | score: 10 | matched tokens: coreneuron, data
- `src/nrniv/nrncore_write/data/cell_group.h` | score: 10 | matched tokens: cell, data
- `src/nrniv/nrncore_write/data/cell_group.cpp` | score: 10 | matched tokens: cell, data
