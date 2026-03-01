# neuron source map: Scm

Generated from source roots:
- `bin`
- `src`
- `packaging/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `scm`
- `release`
- `version`
- `workflow`

## Fast source navigation
- `rg -n "version|compatibility|release" src/nrnoc src/coreneuron src/nrniv packaging/python`
- `rg -n "nrnivmodl|nrnpyenv" bin`

## Suggested source entry points
- `src/nrnoc/nrnversion.cpp` | single source of runtime version strings shown to users
- `src/coreneuron/config/neuron_version.hpp.in` | CoreNEURON version templating used in release builds
- `src/nrniv/nrncore_write/utils/nrncore_utils.cpp` | compatibility enforcement during NEURON/CoreNEURON workflows
- `src/nrniv/nrncore_write.cpp` | orchestration path that triggers compatibility guards
- `src/nrnoc/init.cpp` | mechanism compatibility checks surfaced during startup/loading
- `packaging/python/build_wheels.bash` | wheel/release automation script entry point
- `bin/nrnivmodl.in` | end-user mechanism build wrapper shipped with releases
- `bin/nrnpyenv.sh.in` | support script for selecting compatible Python runtime
