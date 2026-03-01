# neuron source map: Index

Generated from source roots:
- `src`
- `share/lib/python`
- `share/lib/hoc`

Use this map only after routing and exhausting topic docs.

## Fast source navigation
- `rg -n "nrnversion|fadvance|finitialize|NetCon|save_session" src share/lib/python share/lib/hoc`

## Cross-topic source entry points
- `src/nrnoc/fadvance.cpp` | core time stepping path
- `src/nrncvode/netcvode.cpp` | event queue and NetCon delivery behavior
- `src/nrniv/savstate.cpp` | restart and save/restore semantics
- `src/ivoc/pwman.cpp` | session file save/retrieve workflow
- `src/nrnpython/nrnpy_nrn.cpp` | Python API bridge for sections/mechanisms
- `src/nrnoc/nrnversion.cpp` | runtime/version provenance
- `share/lib/hoc/stdrun.hoc` | standard run tool defaults
- `share/lib/python/neuron/__init__.py` | Python package startup behavior
