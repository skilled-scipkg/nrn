# neuron source map: Step 1 Define Type Of Cell2

Generated from source roots:
- `src`
- `share/lib/hoc`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `synapse`
- `cell type`
- `netstim`
- `netcon`

## Fast source navigation
- `rg -n "NetStim|noiseFromRandom123|net_receive" src/nrnoc src/coreneuron`
- `rg -n "NetCon|PreSyn|Point_process" src/nrncvode src/nrnoc src/coreneuron`

## Suggested source entry points
- `src/nrnoc/netstim.mod` | NetStim parameter semantics and random stream behavior
- `src/coreneuron/mechanism/mech/modfile/netstim.mod` | CoreNEURON NetStim behavior parity checks
- `src/nrncvode/netcon.h` | NetCon data model used for connecting event sources/targets
- `src/nrncvode/netcvode.cpp` | event delivery and queue behavior for synaptic connectivity
- `src/nrnoc/point.cpp` | point-process attachment and pointer resolution
- `src/nrnoc/treeset.cpp` | tree/event setup ordering that impacts attach/connect behavior
- `src/coreneuron/network/netcon.hpp` | CoreNEURON-side connection representation
- `src/coreneuron/network/netcvode.cpp` | CoreNEURON event processing checks for connected cells
