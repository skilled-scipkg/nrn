---
name: neuron-saveses
description: This skill should be used when users ask about saveses in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Saveses

## Scope
- Handle legacy and modern usage of session-file save/retrieve workflows.
- Focus on reproducible GUI/session startup paths for repeated simulation runs.

## Primary documentation references
- `docs/guide/saveses.rst`

## Quick session-save playbook
1. Start a minimal run and create a session file:
```bash
nrniv -nobanner -c 'load_file("stdrun.hoc")' -c 'save_session("quick_save.ses")' -c 'quit()'
```
2. Reopen with `nrniv quick_save.ses` (or `load_file("quick_save.ses")`) and rerun.
3. Use `SaveState` only when full state continuity (not just GUI layout) is required.

## Validation checkpoints
- Session file is generated and reloads without syntax/runtime errors.
- Window/model controls expected by the workflow are restored.
- A short rerun after restore produces plausible output.

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
