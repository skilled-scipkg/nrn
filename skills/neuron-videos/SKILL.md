---
name: neuron-videos
description: This skill should be used when users ask about videos in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Videos

## Scope
- Handle questions that map video/course material to runnable NEURON workflows.
- Translate tutorial narratives into concise, verifiable simulation steps.

## Primary documentation references
- `docs/videos/index.rst`
- `docs/videos/neuron-course-2021.rst`

## Quick tutorial-reproduction playbook
1. Choose the exact video/tutorial section and extract the minimal script fragment.
2. Run a short equivalent simulation (single cell or small network) locally.
3. Verify one observable shown in the video (trace shape, spike count, or morphology plot).
4. Escalate to source only if tutorial behavior differs from current runtime.

## Validation checkpoints
- Script executes with current runtime versions.
- One quantitative output matches tutorial expectations.
- Any differences are explained by version/options and documented.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnoc/fadvance.cpp`
- `src/nrniv/shape.cpp`
- `src/ivoc/graph.cpp`
- `share/lib/python/neuron/gui.py`
- `share/lib/python/neuron/gui2/plotshape.py`
- `src/coreneuron/io/reports/report_handler.cpp`
- `src/coreneuron/io/output_spikes.cpp`
- `src/nrnoc/nrnversion.cpp`
- Prefer targeted source search (for example: `rg -n "fadvance|finitialize|Graph|PlotShape|gui" src share/lib/python/neuron`).
