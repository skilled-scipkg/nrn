# neuron source map: Step 3 Connect The Cells Continued

Generated from source roots:
- `src`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `connect`
- `cells`
- `netcon`
- `event`

## Fast source navigation
- `rg -n "NetCon|PreSyn|weight|delay" src/nrncvode src/nrnoc src/coreneuron`
- `rg -n "setup_fornetcon|partrans|multisend" src/nrniv src/coreneuron`

## Suggested source entry points
- `src/nrncvode/netcvode.cpp` | delivery scheduling and event-queue semantics for connected networks
- `src/nrncvode/netcon.h` | NetCon structure fields (weight, delay, source/target pointers)
- `src/nrniv/partrans.cpp` | pointer transfer and distributed connection exchange paths
- `src/nrniv/multisend_setup.cpp` | multisend setup logic affecting network connectivity scaling
- `src/coreneuron/io/setup_fornetcon.cpp` | CoreNEURON NetCon setup from serialized model state
- `src/coreneuron/network/netcon.hpp` | CoreNEURON connection object layout and invariants
- `src/coreneuron/network/netcvode.cpp` | event processing for connected cells in CoreNEURON
- `src/nrniv/prcellstate.cpp` | per-cell state dump useful for connectivity/debug checkpoints
