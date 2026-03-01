---
name: neuron-index
description: This skill should be used when users ask how to use neuron and the correct generated documentation skill must be selected before going deeper into source code.
---

# neuron Skills Index

## Route the request
- Classify the request into one primary topic skill and at most one secondary skill.
- Prefer docs-first resolution; inspect source only when docs cannot explain behavior.
- For simulation execution tasks, prioritize this route order:
  1. `neuron-build-and-install`
  2. `neuron-getting-started`
  3. `neuron-inputs-and-modeling`
  4. `neuron-simulation-workflows`
  5. `neuron-analysis-and-output`

## First simulation bootstrap (if user has no runnable baseline)
```bash
python3 - <<'PY'
from neuron import h
h.load_file("stdrun.hoc")
s = h.Section(name="soma")
s.L = s.diam = 12.6
s.insert("hh")
ic = h.IClamp(s(0.5)); ic.delay = 1; ic.dur = 1; ic.amp = 0.3
h.finitialize(-65)
h.continuerun(20)
print("final_v", s(0.5).v)
PY
```

## Validation checkpoints
- Script reaches target `tstop` without runtime errors.
- At least one non-trivial output value is produced (`final_v` finite).
- Next routed skill is chosen based on the user's bottleneck (build/model/run/output/API).

## Generated topic skills
- `neuron-build-and-install`: Build and Install (build, installation, compilation, and environment setup)
- `neuron-inputs-and-modeling`: Inputs and Modeling (inputs, system setup, models, and physical parameterization)
- `neuron-analysis-and-output`: Analysis and Output (output formats, analysis, and post-processing)
- `neuron-api-and-scripting`: API and Scripting (language bindings, APIs, and programmatic interfaces)
- `neuron-simulation-workflows`: Simulation Workflows (simulation setup, execution flow, and runtime controls)
- `neuron-getting-started`: Getting Started (initial setup, quickstarts, and core concepts)
- `neuron-examples-and-tutorials`: Examples and Tutorials (worked examples, tutorials, and cookbook usage)
- `neuron-developer-guide`: Developer Guide (developer architecture, extension points, and contribution workflow)
- `neuron-parallel-hpc`: Parallel and HPC (MPI/OpenMP/GPU execution, scaling, and batch systems)
- `neuron-theory-and-methods`: Theory and Methods (theoretical background and algorithmic methods)
- `neuron-troubleshooting`: Troubleshooting (known issues, diagnostics, and debugging patterns)
- `neuron-progref`: Progref (programmer reference and runtime control topics)
- `neuron-courses`: Courses
- `neuron-nmodl`: Nmodl
- `neuron-data`: Data
- `neuron-dev`: Dev
- `neuron-videos`: Videos
- `neuron-changelog`: Changelog
- `neuron-using-session-files-for-saving`: Using Session Files For Saving
- `neuron-saveses`: Saveses
- `neuron-step-3-connect-the-cells-continued`: Step 3 Connect The Cells Continued
- `neuron-step-3-connect-cells-continued`: Step 3 Connect Cells Continued
- `neuron-set-up-a-subsetdomainiterator`: Set Up A Subsetdomainiterator
- `neuron-using-the-d-lambda-rule`: Using The D Lambda Rule
- `neuron-step-1-define-type-of-cell2`: Step 1 Define Type Of Cell2
- `neuron-scm`: Scm
- `neuron-removed-features`: Removed Features
- `neuron-publications-using-neuron`: Publications Using Neuron
- `neuron-advanced-topics`: Advanced and Specialized Topics

## Escalate only when needed
- Start from the selected topic skill primary references.
- If those references are insufficient, inspect topic `references/doc_map.md`.
- If documentation still leaves ambiguity, inspect topic `references/source_map.md`.
- Use targeted symbol search while inspecting source (for example: `rg -n "<symbol_or_keyword>" src share/lib/python share/lib/hoc`).

## Index references
- `references/doc_map.md`
- `references/source_map.md`
