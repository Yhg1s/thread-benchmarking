# Results

- fork: python/v3.13.0
- version: 3.13.0
- config: JIT
- commit hash: [60403a5](https://github.com/python/cpython/commit/60403a5)
- commit date: 2024-10-07T07:02:14+02:00
- ref: v3.13.0

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json)

### vs. 3.13.0

- Geometric mean: 1.007x faster (HPT: reliability of 75.51%, 1.00x faster at 99th %ile)
- Memory usage: 1.06x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.13.0.html)
- [📄table](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.13.0.md)
- [📈time plot](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.054x slower (HPT: reliability of 99.96%, 1.00x slower at 99th %ile)
- Memory usage: 0.98x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.14.0.html)
- [📄table](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.14.0.md)
- [📈time plot](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.007x faster (HPT: reliability of 75.51%, 1.00x faster at 99th %ile)
- Memory usage: 1.06x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base-mem.html)
- [🧠memory plot](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base.html)
- [📄table](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base.md)
- [📈time plot](bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5.json)

### vs. 3.13.0

- Geometric mean: 1.005x slower (HPT: reliability of 90.37%, 1.00x slower at 99th %ile)
- Memory usage: 1.07x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.13.0.html)
- [📄table](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.13.0.md)
- [📈time plot](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.064x slower (HPT: reliability of 99.92%, 1.01x slower at 99th %ile)
- Memory usage: 1.00x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.14.0.html)
- [📄table](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.14.0.md)
- [📈time plot](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.005x slower (HPT: reliability of 90.37%, 1.00x slower at 99th %ile)
- Memory usage: 1.07x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base-mem.html)
- [🧠memory plot](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20241007-3.13.0-60403a5-JIT/bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base.html)
- [📄table](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base.md)
- [📈time plot](bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5-vs-base.svg)

