---
name: neuron-scm
description: This skill should be used when users ask about scm in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Scm

## Scope
- Handle source-control and release-workflow questions for NEURON.
- Tie release-process answers to concrete version/compatibility checks.

## Primary documentation references
- `docs/scm/index.rst`

## Quick release-readiness playbook
1. Read the relevant workflow doc section from `docs/scm/index.rst`.
2. Capture current runtime and Python package versions:
```bash
nrniv -nobanner -c 'nrnversion()' -c 'nrnversion(7)' -c 'quit()'
python3 -c "import neuron; print(neuron.__version__)"
```
3. Validate that release artifacts and compatibility checks align with that version set.
4. Escalate to source only for unresolved version/compatibility details.

## Validation checkpoints
- Runtime and package versions are consistent.
- Compatibility checks pass for intended NEURON/CoreNEURON pair.
- Tool wrappers referenced by release docs (`nrnivmodl`, env scripts) match shipped behavior.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnoc/nrnversion.cpp`
- `src/coreneuron/config/neuron_version.hpp.in`
- `src/nrniv/nrncore_write/utils/nrncore_utils.cpp`
- `src/nrniv/nrncore_write.cpp`
- `src/nrnoc/init.cpp`
- `packaging/python/build_wheels.bash`
- `bin/nrnivmodl.in`
- `bin/nrnpyenv.sh.in`
- Prefer targeted source search (for example: `rg -n "version|compatibility|release" src/nrnoc src/coreneuron src/nrniv packaging/python`).
