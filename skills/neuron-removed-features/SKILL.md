---
name: neuron-removed-features
description: This skill should be used when users ask about removed features in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Removed Features

## Scope
- Handle migration questions for removed/deprecated/legacy behavior.
- Emphasize safe replacement workflows and quick compatibility checks.

## Primary documentation references
- `docs/removed_features.rst`

## Quick migration playbook
1. Identify the removed/deprecated feature in `docs/removed_features.rst`.
2. Build a smallest script that demonstrates old vs replacement behavior.
3. Run a smoke simulation using the replacement path.
4. If behavior is unclear, inspect compatibility logic in `references/source_map.md`.

## Validation checkpoints
- Replacement workflow runs without deprecated-path failures.
- Numerical behavior remains stable on a short reference run.
- Any residual warning/error is traceable to a documented compatibility rule.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnoc/init.cpp`
- `src/nrnoc/treeset.cpp`
- `src/nocmodl/nocpout.cpp`
- `src/nmodl/codegen/codegen_compatibility_visitor.hpp`
- `src/nmodl/codegen/codegen_compatibility_visitor.cpp`
- `share/lib/python/neuron/hclass3.py`
- `src/nrnoc/netstim.mod`
- `src/coreneuron/mechanism/mech/modfile/netstim.mod`
- Prefer targeted source search (for example: `rg -n "deprecated|obsolete|legacy|removed" src/nrnoc src/nocmodl src/nmodl share/lib/python/neuron`).
