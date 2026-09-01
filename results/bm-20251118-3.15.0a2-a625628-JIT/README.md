# Results

- fork: python/v3.15.0a2
- version: 3.15.0a2
- config: JIT
- commit hash: [a625628](https://github.com/python/cpython/commit/a625628)
- commit date: 2025-11-18T16:51:17+02:00
- commit merge base: [f46785f8bc118e0efb840af1e520777b1baa03d9](https://github.com/python/cpython/commit/f46785f8bc118e0efb840af1e520777b1baa03d9)
- ref: v3.15.0a2

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628.json)

### vs. 3.13.0

- Geometric mean: 1.113x faster (HPT: reliability of 100.00%, 1.03x faster at 99th %ile)
- Memory usage: 1.11x
- missing benchmarks: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.html)
- [📄table](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.md)
- [📈time plot](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.039x faster (HPT: reliability of 99.87%, 1.00x faster at 99th %ile)
- Memory usage: 1.02x
- missing benchmarks: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.html)
- [📄table](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.md)
- [📈time plot](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.049x faster (HPT: reliability of 99.79%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- missing benchmarks: 🔴 async_tree_eager_memoization_tg, docutils, quadtree_nbody
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base-mem.html)
- [🧠memory plot](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base.html)
- [📄table](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base.md)
- [📈time plot](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628.json)

### vs. 3.13.0

- Geometric mean: 1.100x faster (HPT: reliability of 99.96%, 1.02x faster at 99th %ile)
- Memory usage: 1.02x
- missing benchmarks: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody, sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.html)
- [📄table](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.md)
- [📈time plot](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.028x faster (HPT: reliability of 99.88%, 1.00x faster at 99th %ile)
- Memory usage: 1.03x
- missing benchmarks: async_tree_eager_memoization_tg, docutils, networkx_connected_components, networkx_k_core, networkx_shortest_path, quadtree_nbody, sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.html)
- [📄table](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.md)
- [📈time plot](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.021x faster (HPT: reliability of 82.10%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- missing benchmarks: 🔴 async_tree_eager_memoization_tg, docutils, quadtree_nbody
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base-mem.html)
- [🧠memory plot](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628-JIT/bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base.html)
- [📄table](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base.md)
- [📈time plot](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-base.svg)

