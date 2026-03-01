# neuron source map: Parallel and HPC

Generated from source roots:
- `bin`
- `src`
- `packaging/python`
- `share/lib/python`

Use this map only after exhausting the topic docs in `doc_map.md`.

## Topic query tokens
- `compatibility`
- `compilationoptions`
- `coreneuron`
- `gpu`
- `hpc`
- `mpi`
- `openmp`
- `parallel`
- `performance`
- `progref`
- `scaling`
- `slurm`

## Fast source navigation
- `rg -n "<symbol_or_keyword>" bin src packaging/python share/lib/python`
- `rg -n "class|def|struct|namespace" bin src packaging/python share/lib/python`
- If a doc mentions a function/class, search that exact symbol first, then inspect nearby implementation files.

## Suggested source entry points
- `src/coreneuron/mpi/nrnmpiuse.h` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/nrnmpidec.h` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/nrnmpi.h` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/gpu/nrn_acc_manager.hpp` | score: 10 | matched tokens: coreneuron, gpu
- `src/coreneuron/gpu/nrn_acc_manager.cpp` | score: 10 | matched tokens: coreneuron, gpu
- `src/coreneuron/mpi/lib/nrnmpi.hpp` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/lib/nrnmpi.cpp` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/lib/mpispike.cpp` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/core/resolve.cpp` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/core/nrnmpi_def_cinc.cpp` | score: 10 | matched tokens: coreneuron, mpi
- `src/coreneuron/mpi/core/nrnmpi.hpp` | score: 10 | matched tokens: coreneuron, mpi
- `src/parallel/bbssrvmpi.cpp` | score: 7 | matched tokens: mpi, parallel
- `src/parallel/bbssrv2mpi.h` | score: 7 | matched tokens: mpi, parallel
- `src/parallel/bbssrv2mpi.cpp` | score: 7 | matched tokens: mpi, parallel
- `src/parallel/bbsdirectmpi.cpp` | score: 7 | matched tokens: mpi, parallel
- `src/parallel/bbsclimpi.cpp` | score: 7 | matched tokens: mpi, parallel
- `src/coreneuron/config/neuron_version.hpp.in` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/coreneuron.hpp` | score: 5 | matched tokens: coreneuron
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.hpp` | score: 5 | matched tokens: coreneuron
- `src/nmodl/codegen/codegen_coreneuron_cpp_visitor.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/sim/treeset_core.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/sim/solve_core.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/sim/multicore.hpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/sim/multicore.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/sim/fadvance_core.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/io/nrn2core_direct.h` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/io/nrn2core_data_init.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/io/core2nrn_data_return.hpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/io/core2nrn_data_return.cpp` | score: 5 | matched tokens: coreneuron
- `src/coreneuron/apps/main1.cpp` | score: 5 | matched tokens: coreneuron
