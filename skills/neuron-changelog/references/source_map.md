# neuron source map: Changelog

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `changelog`
- `version`
- `release`
- `compatibility`

## Fast source navigation
- `rg -n "nrnversion\\(|NRN_VERSION|check_coreneuron_compatibility" src bin packaging/python`
- `rg -n "version|compat" src/nrnoc src/coreneuron src/nrniv packaging/python`

## Suggested source entry points
- `src/nrnoc/nrnversion.cpp` | runtime version reporting path (`nrnversion`, option reporting)
- `src/nrnoc/nrnversionmacros.h` | compile-time version macros used by binaries and docs
- `src/coreneuron/config/neuron_version.hpp.in` | CoreNEURON version stamp synced with NEURON
- `src/nrniv/nrncore_write/utils/nrncore_utils.cpp` | NEURON/CoreNEURON compatibility checks and user-facing errors
- `src/nrniv/nrncore_write.cpp` | write path that enforces version compatibility before export
- `packaging/python/build_wheels.bash` | wheel build/release version plumbing
- `bin/nrnpyenv.sh.in` | Python compatibility diagnostics used in release troubleshooting
- `bin/nrnivmodl.in` | user-facing tool wrapper included in release artifacts
