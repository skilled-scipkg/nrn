# neuron source map: Saveses

Generated from source roots:
- `src`
- `share/lib/hoc`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `saveses`
- `session`
- `save_window`
- `retrieve`

## Fast source navigation
- `rg -n "save_session|print_session|save_window_|Retrieve Session" src/ivoc src/nrniv share/lib/hoc`
- `rg -n "SaveState|BBSaveState" src/nrniv`

## Suggested source entry points
- `src/ivoc/pwman.cpp` | `save_session`/retrieve controller and session file emission logic
- `src/ivoc/graph.cpp` | graph serialization snippets written into `.ses` files
- `src/nrniv/shape.cpp` | shape window save/restore statements (`save_window_...`)
- `src/nrniv/shapeplt.cpp` | shape-plot persistence details for session replay
- `src/nrniv/savstate.cpp` | model state save/restore (complements GUI session save)
- `src/nrniv/bbsavestate.cpp` | distributed save/restore path for parallel jobs
- `share/lib/hoc/stdrun.hoc` | user-facing load/save session commands and wrappers
- `share/lib/hoc/wingroup.hoc` | multi-window grouping hooks used during session saves
