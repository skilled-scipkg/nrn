---
name: neuron-build-and-install
description: This skill should be used when users ask about build and install in neuron; it prioritizes documentation references and then source inspection only for unresolved details.
---

# neuron: Build and Install

## High-Signal Playbook

### Route conditions
- Use this skill for install, build, wheel, CMake, dependency, and `nrnivmodl` startup failures.
- Route model-definition questions to `neuron-inputs-and-modeling`.
- Route runtime control / checkpoint / batch-run questions to `neuron-simulation-workflows`.
- Route Python/HOC API semantics to `neuron-api-and-scripting`.

### Triage questions
- Are you installing from binary (`pip`/release installer) or building from source?
- OS and architecture (`Linux`, `macOS arm64/x86_64`, `Windows`, `WSL`)?
- Need GUI (`InterViews`/X11), MPI, CoreNEURON, or RXD?
- Need one Python version or dynamic Python (`NRN_ENABLE_PYTHON_DYNAMIC`)?
- Is this a local workstation build or HPC/cluster build?
- Is failure during configure, compile, import, or runtime loading?

### Canonical workflow
1. Decide binary vs source install (`docs/install/install_instructions.md`, `README.md`).
2. For fast start, use `pip3 install neuron` (Linux/macOS wheels) or platform installer.
3. For CoreNEURON/MPI/vendor compiler needs, do source build with CMake (`docs/cmake_doc/options.rst`).
4. Configure minimal known-good CMake options first; add MPI/CoreNEURON only after baseline build works.
5. Build and run tests (`ctest`) before installing or publishing artifacts.
6. Validate import and CLI (`import neuron`, `nrniv -nobanner -c 'nrnversion()'`).
7. If custom MOD mechanisms are used, compile with `nrnivmodl` and run `special`/`nrniv` accordingly (`docs/scripting.rst`).
8. Only after docs are exhausted, inspect source entry points listed below.

### Minimal working example
```bash
# Binary install + smoke test (docs/install/install_instructions.md)
pip3 install neuron
python3 -c "import neuron; neuron.test(); quit()"
nrniv -nobanner -c 'nrnversion()' -c 'quit()'
```

```bash
# Source build baseline (docs/cmake_doc/options.rst)
git clone https://github.com/neuronsimulator/nrn
cd nrn
mkdir build && cd build
cmake .. \
  -DNRN_ENABLE_INTERVIEWS=OFF \
  -DNRN_ENABLE_MPI=OFF \
  -DNRN_ENABLE_RX3D=OFF \
  -DPYTHON_EXECUTABLE=$(which python3) \
  -DCMAKE_INSTALL_PREFIX=$PWD/install
cmake --build . --parallel 8 --target install
ctest --output-on-failure
```

### Pitfalls and fixes
- Incomplete source tarball (missing submodules): use git clone or full source package (`docs/cmake_doc/options.rst` warning).
- `CoreNEURON` builds too heavy: lower parallelism and/or set `-DNMODL_ENABLE_PYTHON_BINDINGS=OFF` (`docs/cmake_doc/options.rst`).
- `Could not load libnrnpython3`: verify Python selection with `nrnpyenv.sh`, set `-pyexe` or `NRN_PYLIB` (`docs/install/install_instructions.md`).
- MPI library not found from wheel install: set `LD_LIBRARY_PATH`/`DYLD_LIBRARY_PATH` or `MPI_LIB_NRN_PATH`.
- Mac arm64/x86_64 mismatch: align Python, NEURON, and `nrnivmodl` architecture flags (`docs/install/install_instructions.md`).
- `nrnivmodl` regressions on NEURON >= 9 with old MOD code: follow `docs/guide/porting_mechanisms_to_cpp.rst`.
- Cluster build-node/compute-node mismatch for `nocmodl`/`modlunit`: set `NRN_NMODL_CXX_FLAGS` (`docs/install/install_instructions.md`).

### Convergence and validation checks
- `python3 -c "import neuron; neuron.test(); quit()"` succeeds.
- `nrniv -nobanner -c 'nrnversion()' -c 'quit()'` succeeds.
- `nrnivmodl` builds mechanisms in a sample MOD directory.
- Optional: `ctest -R parallel_tests` passes for MPI-enabled builds.
- Optional: one known tutorial script runs without import/loader errors.

## Scope
- Handle questions about build, installation, compilation, and environment setup.
- Keep responses docs-first; escalate to source only when docs do not resolve behavior.

## Primary documentation references
- `README.md`
- `docs/install/install_instructions.md`
- `docs/cmake_doc/options.rst`
- `docs/install/python_wheels.md`
- `docs/install/windows.md`
- `docs/install/mac_pkg.md`
- `docs/scripting.rst`
- `docs/guide/porting_mechanisms_to_cpp.rst`

## Workflow
- Start with the primary references above.
- If details are missing, inspect `references/doc_map.md` for the complete topic inventory.
- Use tests/examples as executable references before reading source.
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
- `packaging/python`
- `cmake`
- `src`
- `bin`

## Source entry points for unresolved issues
- `CMakeLists.txt`
- `cmake/BuildOptionDefaults.cmake`
- `packaging/python/build_wheels.bash`
- `packaging/python/Dockerfile`
- `src/nrnpython/CMakeLists.txt`
- `src/coreneuron/CMakeLists.txt`
- `src/modlunit/units.cpp`
- `src/mac/CMakeLists.txt`
- `bin/nrnivmodl-cmake.in`
- Prefer targeted source search (for example: `rg -n "<symbol_or_keyword>" CMakeLists.txt cmake packaging/python src bin`).
