---
name: neuron-simulation-workflows
description: This skill should be used when users ask about simulation workflows in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Simulation Workflows

## High-Signal Playbook

### Route conditions
- Use this skill for setup->run->restart->output execution flows, standard run controls, batching, and parallel workflow orchestration.
- Route model construction/parameterization details to `neuron-inputs-and-modeling`.
- Route plotting/export specifics to `neuron-analysis-and-output`.
- Route API-language semantics to `neuron-api-and-scripting`.

### Triage questions
- Single run, serial sweep, or distributed parameter sweep?
- Fixed step (`dt`) or variable step (`CVode`)?
- Need checkpoint/restart (`SaveState`) or only one-pass output?
- Serial, MPI, bulletin-board, or CoreNEURON/GPU execution?
- Is the workflow interactive GUI or script/headless?
- What must be recorded/exported each run?

### Canonical workflow
1. Load standard run system (`from neuron import gui` or `n.load_file("stdrun.hoc")`).
2. Build/load model and configure stimuli/parameters.
3. Attach recording (`Vector.record`, `NetCon.record`, or `batch_save` list).
4. Initialize explicitly (`finitialize`) before each run.
5. Execute with `run`/`continuerun` for interactive flows; `batch_run` for efficient in-core sampling.
6. For sweeps, isolate per-run parameter setter and result collector.
7. For MPI bulletin-board workflows, offload expensive work to workers and return minimal payload.
8. Use `SaveState` for restarts only when model structure remains unchanged.
9. Validate outputs and rerun with small solver/discretization perturbations.
10. Only after docs are exhausted, inspect source entry points below.

### Minimal working example
```python
# Programmatic batch run (docs/progref/simctrl/batch.rst)
from neuron import n

soma = n.Section("soma")
soma.L = 10
soma.diam = 10
soma.insert(n.hh)

iclamp = n.IClamp(soma(0.5))
iclamp.dur = 0.2
iclamp.delay = 0.3
iclamp.amp = 0.5

n.batch_save()
n.batch_save(n._ref_t, soma(0.5)._ref_v)
n.finitialize(-65)
n.batch_run(2, 0.1, "hhsim.dat", "My HH sim")
```

```python
# Bulletin-board sweep pattern (docs/courses/code/initbatpar.py)
from neuron import n
pc = n.ParallelContext()
pc.runworker()
for run_id in range(10):
    pc.submit(fi, run_id)  # fi sets params, runs, returns compact results
while pc.working():
    run_id, metric = pc.pyret()
pc.done()
```

### Pitfalls and fixes
- Repeated `InitRun` clicks in GUI can recurse `run()`; use Stop before relaunching (`runctrl.rst` warning).
- Overriding `init`/`advance` without `cvode.re_init()` or `fcurrent()`/`frecord_init()` after state edits leads to inconsistent states.
- `batch_run` without `batch_save` variable pointers yields unusable output.
- `SaveState` is invalid if sections/mechanisms/NetCon structure changes between save and restore.
- Python mode launch nuance: `nrniv -python` only executes first script/`-c`.
- In distributed sweeps, returning excessive data from workers can dominate runtime.

### Convergence and validation checks
- Run reaches intended `tstop`; no NaNs/infs in key variables.
- Spike timing/frequency or target metrics are reproducible for fixed seeds.
- Results are stable under modest `dt` or CVode tolerance refinement.
- Serial and MPI versions agree on a shared benchmark scenario.
- Save/restore returns to identical state when structural constraints are respected.

## Scope
- Handle questions about simulation setup, execution flow, and runtime controls.
- Keep responses docs-first; escalate to source only when docs do not resolve behavior.

## Primary documentation references
- `docs/progref/simctrl/stdrun.rst`
- `docs/progref/simctrl/runctrl.rst`
- `docs/progref/simctrl/programmatic.rst`
- `docs/progref/simctrl/batch.rst`
- `docs/progref/simctrl/savstate.rst`
- `docs/progref/simctrl/sessionsave.rst`
- `docs/scripting.rst`
- `docs/courses/bulletin_board_walkthrough.rst`
- `docs/dev/gpu-testing.rst`
- `docs/dev/workflow-code-paths.rst`
- `docs/dealing_simulations_generate_lot.rst`
- `docs/coreneuron/running-a-simulation.rst`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic inventory.
- Use executable examples before reading source.
- If ambiguity remains, inspect `references/source_map.md` and start with the entry points below.
- Cite exact documentation file paths in responses.

## Tutorials and examples
- `docs/tutorials`
- `docs/courses`
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
- `share/lib/hoc/stdrun.hoc`
- `src/nrnoc/fadvance.cpp`
- `src/coreneuron/sim/finitialize.cpp`
- `src/coreneuron/sim/fadvance_core.cpp`
- `src/coreneuron/network/netcvode.cpp`
- `share/lib/python/neuron/coreneuron.py`
- `share/lib/python/neuron/rxdtests/run_all.py`
- `share/lib/python/neuron/expect_hocerr.py`
- `share/lib/python/neuron/sections.py`
- `share/lib/python/neuron/psection.py`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" src share/lib/python share/lib/hoc`).
