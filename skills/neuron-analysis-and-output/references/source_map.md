# neuron source map: Analysis and Output

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `analysis`
- `courses`
- `defaults`
- `electrotonic`
- `file`
- `glyph`
- `graph`
- `grapher`
- `gui`
- `guitools`
- `labels`
- `manager`
- `move`
- `notify`
- `nrn`
- `oldgrph`
- `output`
- `plot`
- `plots`
- `plotshape`
- `plotwhat`
- `post`
- `postprocess`
- `print`
- `printf`
- `processing`
- `programmatic`
- `programming`
- `progref`
- `rvarplt`

## Fast source navigation
- `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`
- `rg -n "class|def|struct|namespace" bin src packaging/python share/lib/python`
- If a doc mentions a function/class, search that exact symbol first, then inspect nearby implementation files.

## Suggested source entry points
- `share/lib/python/neuron/gui2/plotshape.py` | score: 13 | matched tokens: gui, plot, plots, plotshape, shape
- `src/coreneuron/gpu/nrn_acc_manager.hpp` | score: 10 | matched tokens: manager, nrn
- `src/coreneuron/gpu/nrn_acc_manager.cpp` | score: 10 | matched tokens: manager, nrn
- `src/nrnoc/gui-redirect.h` | score: 7 | matched tokens: gui, nrn
- `src/nrniv/shape.h` | score: 7 | matched tokens: nrn, shape
- `src/nrniv/shape.cpp` | score: 7 | matched tokens: nrn, shape
- `src/coreneuron/io/nrn_filehandler.hpp` | score: 7 | matched tokens: file, nrn
- `src/coreneuron/io/nrn_filehandler.cpp` | score: 7 | matched tokens: file, nrn
- `bin/nrn-enable-sanitizer.in` | score: 5 | matched tokens: nrn
- `src/oc/plot.cpp` | score: 5 | matched tokens: plot
- `src/nrnpython/nrnpy_nrn.h` | score: 5 | matched tokens: nrn
- `src/nrnpython/nrnpy_nrn.cpp` | score: 5 | matched tokens: nrn
- `src/nrnpython/nrn_pyhocobject.h` | score: 5 | matched tokens: nrn
- `src/nrnpython/nrn_metaclass.cpp` | score: 5 | matched tokens: nrn
- `src/nrnpython/nrn_export.hpp` | score: 5 | matched tokens: nrn
- `src/nrnoc/nrn_ansi.h` | score: 5 | matched tokens: nrn
- `src/mac/nrn_codesign.sh.in` | score: 5 | matched tokens: nrn
- `src/ivoc/graph.h` | score: 5 | matched tokens: graph
- `src/ivoc/graph.cpp` | score: 5 | matched tokens: graph
- `src/nmodl/visitors/semantic_analysis_visitor.hpp` | score: 5 | matched tokens: analysis
- `src/nmodl/visitors/semantic_analysis_visitor.cpp` | score: 5 | matched tokens: analysis
- `src/nmodl/utils/file_library.hpp` | score: 5 | matched tokens: file
- `src/nmodl/utils/file_library.cpp` | score: 5 | matched tokens: file
- `src/coreneuron/utils/nrn_stats.h` | score: 5 | matched tokens: nrn
- `src/coreneuron/utils/nrn_stats.cpp` | score: 5 | matched tokens: nrn
- `src/coreneuron/utils/nrn_assert.h` | score: 5 | matched tokens: nrn
- `src/coreneuron/io/output_spikes.hpp` | score: 5 | matched tokens: output
- `src/coreneuron/io/output_spikes.cpp` | score: 5 | matched tokens: output
- `src/coreneuron/io/nrn_setup.hpp` | score: 5 | matched tokens: nrn
- `src/coreneuron/io/nrn_setup.cpp` | score: 5 | matched tokens: nrn
