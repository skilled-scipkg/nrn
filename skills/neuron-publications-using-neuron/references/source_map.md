# neuron source map: Publications Using Neuron

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `publications`
- `reproducibility`
- `state`
- `output`

## Fast source navigation
- `rg -n "SaveState|prcellstate|output_spikes|report" src/nrniv src/coreneuron`
- `rg -n "nrnversion|compatibility" src/nrnoc src/coreneuron`

## Suggested source entry points
- `src/nrnoc/fadvance.cpp` | main integrator step path used by nearly all published simulations
- `src/nrncvode/netcvode.cpp` | event queue/timing behavior for spike-driven reproducibility checks
- `src/nrniv/prcellstate.cpp` | deterministic per-cell state dump path for cross-run comparisons
- `src/nrniv/savstate.cpp` | save/restore behavior used in restart/reproducibility workflows
- `src/coreneuron/io/output_spikes.cpp` | spike output serialization path for published benchmark traces
- `src/coreneuron/io/reports/report_handler.cpp` | report variable lookup and output sampling behavior
- `src/nrnoc/nrnversion.cpp` | runtime provenance metadata for methods sections
- `src/coreneuron/config/neuron_version.hpp.in` | version lock-step between NEURON and CoreNEURON
