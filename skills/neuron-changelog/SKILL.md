---
name: neuron-changelog
description: This skill should be used when users ask about changelog in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Changelog

## Scope
- Handle questions about release-to-release behavior changes and migration impact.
- Stay docs-first and use source only to validate ambiguous version-specific behavior.

## Primary documentation references
- `docs/changelog.md`

## Quick release-check playbook
1. Identify the target release section in `docs/changelog.md`.
2. Capture runtime version metadata from the user environment:
```bash
nrniv -nobanner -c 'nrnversion()' -c 'nrnversion(7)' -c 'quit()'
python3 -c "import neuron; print(neuron.__version__)"
```
3. Map the reported behavior to the exact changelog item.
4. If release notes are insufficient, inspect `references/source_map.md` for version/compatibility implementation.

## Validation checkpoints
- Runtime `nrnversion()` aligns with the release branch being discussed.
- Python package version and runtime version are not contradictory.
- Any claimed compatibility constraint is tied to a concrete source check.

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic document list.
- If ambiguity remains after docs, inspect `references/source_map.md` and start with the ranked source entry points.
- Cite exact documentation file paths in responses.

## Source entry points for unresolved issues
- `src/nrnoc/nrnversion.cpp`
- `src/nrnoc/nrnversionmacros.h`
- `src/coreneuron/config/neuron_version.hpp.in`
- `src/nrniv/nrncore_write/utils/nrncore_utils.cpp`
- `src/nrniv/nrncore_write.cpp`
- `packaging/python/build_wheels.bash`
- `bin/nrnpyenv.sh.in`
- `bin/nrnivmodl.in`
- Prefer targeted source search (for example: `rg -n "nrnversion\(|NRN_VERSION|check_coreneuron_compatibility" src bin packaging/python`).
