---
name: neuron-progref
description: This skill should be used when users ask about progref in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Progref

## High-Signal Playbook

### Route conditions
- Use this skill for programmer-reference questions on runtime control, interpreter behavior, environment variables, and state/session handling.
- Route model-construction semantics to `neuron-inputs-and-modeling`.
- Route run pipelines and batch/parallel execution strategy to `neuron-simulation-workflows`.
- Route Python/HOC API idioms to `neuron-api-and-scripting`.

### Triage questions
- Is the issue in Python mode, HOC mode, or mixed?
- Is the request about command launch options or interpreter runtime behavior?
- Is dynamic code loading/execution (`execute`, `execute1`, `load_proc`) involved?
- Is session/state persistence (`save_session`, `SaveState`, `BBSaveState`) required?
- Is this single-process or MPI execution?
- Is failure from syntax/parse errors, runtime math errors, or unexpected control flow?

### Canonical workflow
1. Find the exact reference page in `docs/progref` for the symbol or function family.
2. Confirm Python vs HOC tab syntax before trying code.
3. Build a minimal reproducer (`nrniv -c ...` or short Python script).
4. For dynamic execution, prefer `execute1` when non-aborting error capture is needed.
5. For launch behavior, inspect env-variable rules and verify with `nrnversion(7)`.
6. For restart needs, use `SaveState`/`save_session` semantics from simctrl docs.
7. For unresolved behavior, inspect `share/lib/hoc/stdrun.hoc` and source entry points.

### Minimal working example
```bash
# Quick runtime/option introspection (docs/progref/programming/system.rst)
nrniv -nobanner -c 'nrnversion()' -c 'nrnversion(7)' -c 'quit()'
```

```python
from neuron import n

# execute1 returns 0 on interpreter error instead of aborting
ok = n.execute1("x = 1/0", 0)
print("execute1 status:", ok)

s = n.ref("")
n.sprint(s, "version=%s", n.nrnversion())
print(s[0])
```

### Pitfalls and fixes
- Assuming `execute1` throws: it returns status (`0` on error), so always check return value.
- Dynamic code from untrusted input: treat as arbitrary code execution risk.
- `initnrn()` as a full reset: it is not a complete process reset (`programmatic.rst` warning).
- `SaveState` after structural edits (new/deleted sections, changed mechanisms): unsupported and often invalid.
- MPI abort behavior on interpreter error: use `execute1` and/or `ParallelContext.mpiabort_on_error`.
- Misreading command-line options actually used: verify with `n.nrnversion(7)`.

### Convergence and validation checks
- `n.nrnversion(7)` matches intended startup options.
- `execute1` failure paths are explicitly handled.
- Save/restore cycles reproduce deterministic trajectories when model structure is unchanged.
- Same script behavior is confirmed in both expected launch modes (`python` vs `nrniv`).
- Batch/session persistence restores intended state/window configuration.

## Scope
- Handle questions about documentation grouped under the 'progref' theme.
- Keep responses docs-first; escalate to source only when docs do not resolve behavior.

## Primary documentation references
- `docs/progref/programming/system.rst`
- `docs/progref/programming/dynamiccode.rst`
- `docs/progref/envvariables.rst`
- `docs/progref/simctrl/programmatic.rst`
- `docs/progref/simctrl/stdrun.rst`
- `docs/progref/simctrl/savstate.rst`
- `docs/progref/simctrl/sessionsave.rst`
- `docs/progref/simctrl/batch.rst`
- `docs/progref/simctrl/bbsavestate.rst`
- `docs/progref/simctrl/interpretermanagement.rst`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic inventory.
- Use executable examples before reading source.
- If ambiguity remains, inspect `references/source_map.md` and start with the entry points below.
- Cite exact documentation file paths in responses.

## Tutorials and examples
- `docs/courses`
- `docs/tutorials`
- `share/examples`
- `src/nrnpython/examples`

## Test references
- `test`
- `share/lib/python/neuron/tests`
- `share/lib/python/neuron/rxdtests`

## Optional deeper inspection
- `src`
- `share/lib/python`
- `share/lib/hoc`

## Source entry points for unresolved issues
- `src/nrnoc/nrnversion.cpp`
- `src/nrnoc/nrnversionmacros.h`
- `src/nrniv/savstate.cpp`
- `src/nrniv/bbsavestate.h`
- `src/nrniv/bbsavestate.cpp`
- `share/lib/hoc/stdrun.hoc`
- `src/oc/oc_mcran4.cpp`
- `src/oc/math.cpp`
- `share/lib/python/neuron/gui.py`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" src share/lib/python share/lib/hoc`).
