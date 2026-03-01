---
name: neuron-troubleshooting
description: This skill should be used when users ask about troubleshooting in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Troubleshooting

## Scope
- Handle known issues, runtime failures, and debugging workflows.
- Prioritize fast reproduction, targeted diagnostics, and verifiable fixes.

## Primary documentation references
- `docs/courses/quality_issues_with_morphometric.rst`
- `docs/progref/programming/errors.rst`

## Quick diagnostics playbook
1. Capture environment and launcher context:
```bash
nrniv -nobanner -c 'nrnversion()' -c 'nrnversion(7)' -c 'quit()'
python3 -c "import neuron; print(neuron.__version__)"
```
2. Reproduce with the smallest possible script.
3. Add one diagnostic at a time (pointer/value checks, shape/topology checks, save/restore checks).
4. Escalate to source when a doc-backed expectation and runtime behavior diverge.

## Validation checkpoints
- Failure is reproducible with a minimal script.
- Proposed fix removes the error without introducing new warnings.
- A short regression rerun confirms stable behavior.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/oc/debug.cpp`
- `src/oc/hoc.cpp`
- `src/nrniv/nrnpy.cpp`
- `src/nrniv/savstate.cpp`
- `src/nrniv/bbsavestate.cpp`
- `src/nrniv/nrncore_write/utils/nrncore_utils.cpp`
- `src/coreneuron/io/phase2.cpp`
- `share/lib/python/neuron/expect_hocerr.py`
- `bin/nrndiagnose.sh.in`
- Prefer targeted source search (for example: `rg -n "hoc_execerror|warning|incompatible|failed" src/oc src/nrniv src/coreneuron`).
