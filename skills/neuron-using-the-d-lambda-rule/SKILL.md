---
name: neuron-using-the-d-lambda-rule
description: This skill should be used when users ask about using the d lambda rule in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Using The D Lambda Rule

## Scope
- Handle discretization (`nseg`) guidance using d_lambda/lambda_f heuristics.
- Keep answers tied to runnable checks that expose stability vs cost tradeoffs.

## Primary documentation references
- `docs/guide/using_the_d_lambda_rule.rst`

## Quick discretization playbook
1. Start with morphology/mechanisms loaded.
2. Apply d_lambda-driven `nseg` assignment:
```hoc
load_file("stdlib.hoc")
forall nseg = int((L/(0.1*lambda_f(100)) + 0.999)/2)*2 + 1
```
3. Run a short simulation, then repeat with tighter discretization (e.g., 0.1 -> 0.05).
4. Compare target outputs (spike timing/voltage peaks) and keep the coarsest stable setting.

## Validation checkpoints
- `nseg` remains odd and positive for each section.
- Target metrics are stable when tightening discretization.
- Runtime cost increase is justified by accuracy gains.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `share/lib/hoc/stdlib.hoc`
- `share/lib/hoc/celbild/celgeom.hoc`
- `src/nrnoc/cabcode.cpp`
- `src/nrnoc/solve.cpp`
- `src/nrnoc/init.cpp`
- `src/nrnpython/nrnpy_nrn.cpp`
- `src/nrniv/neuronapi.cpp`
- `share/lib/python/neuron/gui2/utilities.py`
- Prefer targeted source search (for example: `rg -n "lambda_f|geom_nseg|d_lambda|nseg" share/lib/hoc src/nrnoc src/nrnpython src/nrniv`).
