---
name: neuron-using-session-files-for-saving
description: This skill should be used when users ask about using session files for saving in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Using Session Files For Saving

## Scope
- Handle practical workflows for saving/retrieving GUI session state and complementary model state.
- Keep guidance runnable and explicit about what session files do and do not preserve.

## Primary documentation references
- `docs/guide/using_session_files_for_saving.rst`

## Quick session workflow playbook
1. Save a session from a minimal run context:
```bash
nrniv -nobanner -c 'load_file("stdrun.hoc")' -c 'save_session("session_demo.ses")' -c 'quit()'
```
2. Reload the session and verify expected windows/settings are restored.
3. For exact numerical continuation, pair session workflows with `SaveState`.

## Validation checkpoints
- `.ses` file loads cleanly.
- Expected GUI windows/graph setup reappear.
- If continuity is required, `SaveState` restore reproduces intended dynamics.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/ivoc/pwman.cpp`
- `src/ivoc/graph.cpp`
- `src/nrniv/shape.cpp`
- `src/nrniv/shapeplt.cpp`
- `src/nrniv/savstate.cpp`
- `src/nrniv/bbsavestate.cpp`
- `share/lib/hoc/stdrun.hoc`
- `share/lib/hoc/wingroup.hoc`
- Prefer targeted source search (for example: `rg -n "save_session|print_session|save_window_|Retrieve Session" src/ivoc src/nrniv share/lib/hoc`).
