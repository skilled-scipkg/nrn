# neuron source map: Troubleshooting

Generated from source roots:
- `bin`
- `src`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `debug`
- `error`
- `failure`
- `diagnostic`

## Fast source navigation
- `rg -n "hoc_execerror|warning|incompatible|failed" src/oc src/nrniv src/coreneuron`
- `rg -n "expect_hocerr|raise|Exception" share/lib/python/neuron`

## Suggested source entry points
- `src/oc/debug.cpp` | low-level debug hooks and instrumentation helpers
- `src/oc/hoc.cpp` | interpreter error/reporting paths (`hoc_execerror`, parser/runtime failures)
- `src/nrniv/nrnpy.cpp` | Python runtime selection and mismatch diagnostics
- `src/nrniv/savstate.cpp` | save/restore consistency warnings and structure mismatch errors
- `src/nrniv/bbsavestate.cpp` | distributed state consistency diagnostics in parallel runs
- `src/nrniv/nrncore_write/utils/nrncore_utils.cpp` | NEURON/CoreNEURON compatibility error generation
- `src/coreneuron/io/phase2.cpp` | model/mechanism compatibility checks when loading CoreNEURON data
- `share/lib/python/neuron/expect_hocerr.py` | regression helper for expected interpreter error behavior
- `bin/nrndiagnose.sh.in` | user-facing diagnostics script entry point
