---
name: neuron-inputs-and-modeling
description: This skill should be used when users ask about inputs and modeling in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Inputs and Modeling

## High-Signal Playbook

### Route conditions
- Use this skill for cell/network specification, mechanism insertion, units, and stochastic input setup.
- Route installation/compilation issues to `neuron-build-and-install`.
- Route run/restart/batch execution controls to `neuron-simulation-workflows`.
- Route Python/HOC language interop questions to `neuron-api-and-scripting`.

### Triage questions
- Is this a single-cell, network, or RXD-style model?
- Are mechanisms built-in, custom MOD, or both?
- Is morphology stylized (`Section`) or imported from data files?
- Fixed-step (`dt`) or variable-step (`CVode`) integration?
- Must results be reproducible across serial vs MPI layouts?
- Which quantities/units are most critical (conductance, concentration, geometry)?
- Is the target NEURON-only, or NEURON + CoreNEURON?

### Canonical workflow
1. Define and connect sections (`docs/progref/modelspec/programmatic/topology.rst`).
2. Set geometry and cable properties (`L`, `diam`, `Ra`, `cm`, `nseg`).
3. Insert mechanisms and set parameters (`docs/progref/modelspec/programmatic/mechanisms.rst`).
4. For custom MOD files, check units consistency with `modlunit` (`docs/guide/units.rst`).
5. Add stimuli/synapses/network links (`docs/progref/modelspec/programmatic/network.rst`).
6. For randomness, assign distinct Random123 streams (`docs/guide/randomness.rst`).
7. Initialize with explicit units (`neuron.units`) and run a short smoke simulation.
8. Refine `nseg`, `dt`, or CVode tolerances before large sweeps.
9. Only after docs are exhausted, inspect source entry points below.

### Minimal working example
```python
from neuron import n
from neuron.units import ms, mV
n.load_file("stdrun.hoc")

soma = n.Section("soma")
dend = n.Section("dend")
dend.connect(soma(1))
for sec in (soma, dend):
    sec.Ra = 100
    sec.cm = 1
soma.L = soma.diam = 12.6
dend.L = 200
dend.diam = 1
soma.insert(n.hh)
dend.insert("pas")

stim = n.IClamp(soma(0.5))
stim.delay = 1 * ms
stim.dur = 1 * ms
stim.amp = 0.3

n.finitialize(-65 * mV)
n.continuerun(40 * ms)
```

```python
# Independent random streams for NetStim objects (docs/guide/randomness.rst)
ns0, ns1 = n.NetStim(), n.NetStim()
for i, ns in enumerate((ns0, ns1)):
    ns.interval = 10
    ns.number = 10
    ns.start = 1
    ns.noise = 1
    ns.noiseFromRandom123(i, 0, 0)
```

### Pitfalls and fixes
- Correlated spike trains from shared RNG: use `noiseFromRandom123` per NetStim (`docs/guide/randomness.rst`).
- Silent unit mistakes in custom MOD: run `modlunit` and use proper unit conversion syntax (`docs/guide/units.rst`).
- Section loops/reconnections: use `disconnect()` before reconnecting (`topology.rst`).
- Confusing section-level vs range variables (`Ra` is section-level): check `topology.rst` and mechanisms docs.
- Skipping `stdrun.hoc` before `continuerun`: load standard run tools first.
- Overly coarse `nseg`/`dt`: apply `d_lambda` guidance and rerun sensitivity checks.

### Convergence and validation checks
- `n.topology()` matches intended structure.
- `modlunit` reports no unresolved units issues for custom mechanisms.
- Key traces remain qualitatively stable when refining `dt`/`nseg` or CVode tolerances.
- Serial and MPI runs agree when Random123 streams are assigned deterministically.
- Core state variables remain in plausible physiological ranges.

## Scope
- Handle questions about inputs, system setup, models, and physical parameterization.
- Keep responses docs-first; escalate to source only when docs do not resolve behavior.

## Primary documentation references
- `docs/progref/modelspec/programmatic.rst`
- `docs/progref/modelspec/programmatic/topology.rst`
- `docs/progref/modelspec/programmatic/mechanisms.rst`
- `docs/progref/modelspec/programmatic/network.rst`
- `docs/guide/units.rst`
- `docs/guide/randomness.rst`
- `docs/guide/using_the_d_lambda_rule.rst`
- `docs/nmodl/transpiler/language.rst`
- `docs/nmodl/transpiler/contents/globals.rst`
- `docs/courses/interactive_modeling.rst`
- `docs/guide/example_of_simple_network.rst`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic inventory.
- Use tutorials/examples as executable references before reading source.
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
- `docs/courses/code`

## Source entry points for unresolved issues
- `src/nrnoc/netstim.mod`
- `src/nrnoc/psection.cpp`
- `src/neuron/model_data.hpp`
- `src/neuron/cache/model_data.hpp`
- `src/nmodl/parser/main_units.cpp`
- `src/nmodl/lexer/main_units.cpp`
- `src/nmodl/units/units.cpp`
- `src/coreneuron/utils/randoms/nrnran123.cpp`
- `src/coreneuron/io/nrn2core_data_init.cpp`
- `src/coreneuron/mechanism/mech/modfile/netstim.mod`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" src share/lib/python docs/courses/code`).
