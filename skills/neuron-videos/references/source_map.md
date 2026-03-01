# neuron source map: Videos

Generated from source roots:
- `src`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `video`
- `tutorial`
- `demo`
- `plot`

## Fast source navigation
- `rg -n "fadvance|finitialize|run" src/nrnoc src/nrncvode src/coreneuron`
- `rg -n "Graph|PlotShape|gui" src/ivoc src/nrniv share/lib/python/neuron`

## Suggested source entry points
- `src/nrnoc/fadvance.cpp` | baseline time-stepping behavior shown in most tutorials
- `src/nrniv/shape.cpp` | morphology visualization paths used by GUI tutorial content
- `src/ivoc/graph.cpp` | graph plotting mechanics visible in tutorial workflows
- `share/lib/python/neuron/gui.py` | Python GUI bootstrap used in many tutorial scripts
- `share/lib/python/neuron/gui2/plotshape.py` | Python-side PlotShape behavior in notebook/demo contexts
- `src/coreneuron/io/reports/report_handler.cpp` | report generation path for advanced tutorial outputs
- `src/coreneuron/io/output_spikes.cpp` | spike output handling for reproducible demo traces
- `src/nrnoc/nrnversion.cpp` | runtime version provenance useful when reproducing course videos
