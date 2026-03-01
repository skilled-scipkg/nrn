---
name: neuron-api-and-scripting
description: This skill should be used when users ask about api and scripting in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: API and Scripting

## High-Signal Playbook

### Route conditions
- Use this skill for Python API usage, HOC/Python interop, scripting launch modes, and symbol lookup paths.
- Route install/build/runtime loader failures to `neuron-build-and-install`.
- Route model-physics specification to `neuron-inputs-and-modeling`.
- Route run/restart/batch orchestration to `neuron-simulation-workflows`.

### Triage questions
- Is the main entry point Python, HOC, or C API?
- Is code running as `python script.py`, `nrniv script.py`, or `nrniv -python ...`?
- Are you integrating legacy HOC into Python, Python into HOC, or both?
- Are custom MOD mechanisms required?
- Do you need GUI event handling (`from neuron import gui`)?
- Is the failure an unresolved symbol, wrong type, or launch-environment mismatch?

### Canonical workflow
1. Pick the primary interface (Python, HOC, or C API) from docs.
2. Build a smallest runnable script in that interface first.
3. For Python->HOC access, use `n`/HocObject idioms from `hoc-from-python.rst`.
4. For HOC->Python access, use `nrnpython(...)` or `PythonObject` patterns.
5. Keep one Python entry script when using `nrniv -python` (`docs/scripting.rst` caveat).
6. If custom MOD files are needed, compile with `nrnivmodl` and use the produced executable as needed.
7. For unresolved symbols, search docs first, then `references/source_map.md` and concrete source files below.

### Minimal working example
```python
from neuron import n

# HOC from Python
n('strdef s')
n('{x = 3 s = "hello"}')
print(n.x, n.s)

# Native Python NEURON objects
soma = n.Section("soma")
soma.insert(n.hh)
print(soma(0.5).v)
```

```hoc
// Python from HOC (docs/progref/programming/python-from-hoc.rst)
nrnpython("import sys")
nrnpython("print(sys.path)")
```

### Pitfalls and fixes
- Outdated interop idioms still work but may be non-idiomatic; prefer modern Python-first style when possible.
- Forgetting method-call parentheses (`n.vec.size` vs `n.vec.size()`).
- `nrniv -python` processes one script or one `-c` fragment only; extra entries become args.
- Python-interpreter mismatch under `nrniv -python`: control with `-pyexe` or `NRN_PYTHONEXE` (`docs/scripting.rst`).
- In Python code, `load_file("nrngui.hoc")` does not replace `from neuron import gui` for GUI event handling.
- `execute`/`exec` on user-provided strings is unsafe; treat as arbitrary code execution.

### Convergence and validation checks
- Script works the same under intended launcher (`python` vs `nrniv -python`).
- `n.nrnversion(7)` confirms startup options and environment.
- HOC/Python shared values are mutually visible where expected.
- For C API usage, `nrn_init(...)` returns success before any API calls.
- Symbol lookup path is documented in response before escalating to source files.

## Scope
- Handle questions about language bindings, APIs, and programmatic interfaces.
- Keep responses docs-first; escalate to source only when docs do not resolve behavior.

## Primary documentation references
- `docs/scripting.rst`
- `docs/tutorials/index.rst`
- `docs/rxd-tutorials/index.rst`
- `docs/progref/programming/hoc-from-python.rst`
- `docs/progref/programming/python-from-hoc.rst`
- `docs/progref/programming/dynamiccode.rst`
- `docs/progref/envvariables.rst`
- `docs/capi.rst`
- `docs/dev/nmodl-development.rst`
- `docs/guide/porting_mechanisms_to_cpp.rst`
- `docs/courses/hoc_exercises.rst`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic inventory.
- Use examples as executable references before reading source.
- If ambiguity remains, inspect `references/source_map.md` and start with the entry points below.
- Cite exact documentation file paths in responses.

## Tutorials and examples
- `docs/tutorials`
- `docs/rxd-tutorials`
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
- `share/lib/python/neuron/__init__.py`
- `share/lib/python/neuron/hclass3.py`
- `src/nrnpython/nrnpy_nrn.cpp`
- `src/nrnpython/nrn_pyhocobject.h`
- `src/nrnpython/nrn_metaclass.cpp`
- `share/lib/python/neuron/rxd/__init__.py`
- `share/lib/python/neuron/nmodl/__init__.py`
- `share/lib/python/neuron/coreneuron.py`
- `share/lib/python/neuron/rxd/rxdmath.py`
- `share/lib/python/neuron/rxd/geometry.py`
- `share/lib/python/neuron/rxd/geometry3d/scalarField.py`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" src share/lib/python share/lib/hoc`).
