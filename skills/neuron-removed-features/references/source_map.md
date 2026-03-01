# neuron source map: Removed Features

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `removed`
- `deprecated`
- `obsolete`
- `legacy`

## Fast source navigation
- `rg -n "deprecated|obsolete|legacy|removed" src/nrnoc src/nocmodl src/nmodl share/lib/python/neuron`
- `rg -n "compatibility" src/nmodl src/nrnoc src/coreneuron`

## Suggested source entry points
- `src/nrnoc/init.cpp` | legacy-units and version-compatibility guardrails (`nrnunit_use_legacy`, mech checks)
- `src/nrnoc/treeset.cpp` | obsolete activation/setup code paths called out in comments and behavior
- `src/nocmodl/nocpout.cpp` | legacy MOD-generation behavior and obsolete NET_RECEIVE notes
- `src/nmodl/codegen/codegen_compatibility_visitor.hpp` | compatibility audit rules for modern codegen
- `src/nmodl/codegen/codegen_compatibility_visitor.cpp` | implementation of incompatibility detection
- `share/lib/python/neuron/hclass3.py` | Python deprecation path (`HocBaseObject` migration)
- `src/nrnoc/netstim.mod` | legacy random APIs and removed intrinsic bursting notes
- `src/coreneuron/mechanism/mech/modfile/netstim.mod` | mirrored legacy/removed behavior in CoreNEURON modfile path
