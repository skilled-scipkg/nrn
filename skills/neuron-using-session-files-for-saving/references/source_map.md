# neuron source map: Using Session Files For Saving

Generated from source roots:
- `src`
- `share/lib/hoc`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `session`
- `save`
- `retrieve`
- `window`

## Fast source navigation
- `rg -n "save_session|print_session|save_window_|Retrieve Session" src/ivoc src/nrniv share/lib/hoc`
- `rg -n "SaveState|BBSaveState" src/nrniv`

## Suggested source entry points
- `src/ivoc/pwman.cpp` | session file generation/retrieval UI and command handlers
- `src/ivoc/graph.cpp` | graph serialization commands written into session files
- `src/nrniv/shape.cpp` | shape window persistence and replay commands
- `src/nrniv/shapeplt.cpp` | shape plot session-save command emission
- `src/nrniv/savstate.cpp` | numerical state save/restore (complements visual session files)
- `src/nrniv/bbsavestate.cpp` | parallel save/restore behavior for distributed jobs
- `share/lib/hoc/stdrun.hoc` | front-end commands users invoke to save/load sessions
- `share/lib/hoc/wingroup.hoc` | grouped-window behavior used during session save/retrieve
