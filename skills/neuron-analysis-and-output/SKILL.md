---
name: neuron-analysis-and-output
description: This skill should be used when users ask about analysis and output in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Analysis and Output

## High-Signal Playbook

### Route conditions
- Use this skill for plotting, graph configuration, morphology visualization, impedance/electrotonic analysis, and output export.
- Route model setup questions to `neuron-inputs-and-modeling`.
- Route run-control logic and checkpoint strategy to `neuron-simulation-workflows`.
- Route API-language interoperability to `neuron-api-and-scripting`.

### Triage questions
- Do you need GUI (`InterViews`) plots or notebook/Matplotlib/Plotly output?
- Is the target a time trace, spatial map, or impedance/electrotonic metric?
- Which variable and location should be plotted (e.g., `soma(0.5).v`, `IClamp[0].i`)?
- Need visual output, numeric export, or both?
- Is the run headless (`-nogui`) or interactive?
- Is this one-run diagnostics or repeated comparative analysis?

### Canonical workflow
1. Pick the analysis tool family: `Graph`, `PlotShape`, `Grapher`, or `Impedance`.
2. Ensure GUI/event loop setup when needed (`from neuron import gui`).
3. Define target variables explicitly (`addvar`, Plot-what browser, or `PlotShape.variable`).
4. Set scales and view ranges before/after the first run (`View = plot`, `scale`).
5. Execute simulation and refresh/flush plots.
6. Export data in the required form (`Vector`, ASCII output, PostScript/session tools).
7. Cross-check plotted values against direct vector/file outputs.
8. Only after docs are exhausted, inspect rendering/IO source entry points below.

### Minimal working example
```python
from neuron import n, gui

soma = n.Section("soma")
soma.insert(n.hh)
ic = n.IClamp(soma(0.5))
ic.delay = 0.1
ic.dur = 0.1
ic.amp = 0.3

g = n.Graph(False)
n.graphList[0].append(g)
g.addvar("v", soma(0.5)._ref_v)

n.finitialize(-65)
n.continuerun(5)
```

```python
# Notebook/Matplotlib morphology rendering (docs/progref/visualization/plotshapeclass.rst)
from matplotlib import pyplot
ps = n.PlotShape(False)
ps.variable("v")
ps.scale(-80, 40)
ps.plot(pyplot)
pyplot.show()
```

### Pitfalls and fixes
- In Python scripts, prefer Python formatting/file IO over `n.printf` unless legacy HOC compatibility is required.
- `PlotShape.plot(...)` with Interviews enabled: pass `False` to `n.PlotShape(False)` to avoid duplicate GUI windows.
- Wrong variable labels from manual typing: use Plot-what browser (`docs/guide/using_plotwhat_to_specify_a_variable.rst`).
- Graph appears flat or clipped: apply `View = plot` and verify axis ranges.
- Shape plots support range variables, not arbitrary expressions (`plotshape.rst`).
- Extended impedance computation can be ill-conditioned with excitable channels; review method limits in impedance docs.

### Convergence and validation checks
- Confirm plotted symbol/location matches intended variable and units.
- Verify at least one numeric export (`Vector`/ASCII) matches plotted trajectories.
- For impedance studies, check trends across frequency/location are physically consistent.
- Repeat with fixed seeds and same solver settings when comparing runs.
- Ensure plotted conclusions are stable under modest `dt`/solver sensitivity checks.

## Scope
- Handle questions about output formats, analysis, and post-processing.
- Keep responses docs-first; escalate to source only when docs do not resolve behavior.

## Primary documentation references
- `docs/progref/visualization/graph.rst`
- `docs/progref/visualization/grapher.rst`
- `docs/progref/visualization/plotshape.rst`
- `docs/progref/visualization/plotshapeclass.rst`
- `docs/progref/analysis/programmatic/impedance.rst`
- `docs/guide/using_plotwhat_to_specify_a_variable.rst`
- `docs/guide/print_file_manager.rst`
- `docs/courses/working_with_shape_plots.rst`
- `docs/courses/electrotonic_analysis.rst`
- `docs/progref/programming/io/printf.rst`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic inventory.
- Use examples as executable references before reading source.
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
- `src/ivoc/graph.cpp`
- `src/oc/plot.cpp`
- `src/nrniv/shape.cpp`
- `src/nrniv/ppshape.cpp`
- `share/lib/python/neuron/gui2/plotshape.py`
- `src/nrnoc/gui-redirect.h`
- `src/coreneuron/io/output_spikes.cpp`
- `src/nrnpython/nrnpy_nrn.cpp`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" src share/lib/python share/lib/hoc`).
