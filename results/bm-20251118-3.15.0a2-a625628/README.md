# Results

- fork: python/v3.15.0a2
- version: 3.15.0a2
- config: 
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

- Geometric mean: 1.057x faster (HPT: reliability of 97.30%, 1.00x faster at 99th %ile)
- Memory usage: 1.11x
- missing benchmarks: networkx_connected_components, networkx_k_core, networkx_shortest_path
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628/bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.html)
- [📄table](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.md)
- [📈time plot](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.008x slower (HPT: reliability of 98.54%, 1.00x slower at 99th %ile)
- Memory usage: 1.01x
- missing benchmarks: networkx_connected_components, networkx_k_core, networkx_shortest_path
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628/bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.html)
- [📄table](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.md)
- [📈time plot](bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.svg)

## linux x86_64 (centurion_gcc15)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628.json)

### vs. 3.13.0

- Geometric mean: 1.107x faster (HPT: reliability of 100.00%, 1.04x faster at 99th %ile)
- Memory usage: 1.11x
- missing benchmarks: networkx_connected_components, networkx_k_core, networkx_shortest_path
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628/bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.html)
- [📄table](bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.md)
- [📈time plot](bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.026x faster (HPT: reliability of 100.00%, 1.01x faster at 99th %ile)
- Memory usage: 1.01x
- missing benchmarks: networkx_connected_components, networkx_k_core, networkx_shortest_path
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628/bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.html)
- [📄table](bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.md)
- [📈time plot](bm-20251118-centurion_gcc15-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628.json)

### vs. 3.13.0

- Geometric mean: 1.073x faster (HPT: reliability of 99.98%, 1.00x faster at 99th %ile)
- Memory usage: 1.10x
- missing benchmarks: networkx_connected_components, networkx_k_core, networkx_shortest_path, sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628/bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.html)
- [📄table](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.md)
- [📈time plot](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.007x faster (HPT: reliability of 68.50%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- missing benchmarks: networkx_connected_components, networkx_k_core, networkx_shortest_path, sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251118-3.15.0a2-a625628/bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.html)
- [📄table](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.md)
- [📈time plot](bm-20251118-centurion_gcc9-x86_64-python-v3.15.0a2-3.15.0a2-a625628-vs-3.14.0.svg)

