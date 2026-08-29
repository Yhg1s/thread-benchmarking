# Results

- fork: python/v3.15.0a4
- version: 3.15.0a4
- config: NOGIL
- commit hash: [43cd277](https://github.com/python/cpython/commit/43cd277)
- commit date: 2026-01-13T12:26:56+02:00
- commit merge base: [c4ab024530feb3a66d51bcef2e33b309ca0d543f](https://github.com/python/cpython/commit/c4ab024530feb3a66d51bcef2e33b309ca0d543f)
- ref: v3.15.0a4

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json)

### vs. 3.13.0

- Geometric mean: 1.066x faster (HPT: reliability of 90.88%, 1.00x slower at 99th %ile)
- Memory usage: 1.60x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.html)
- [📄table](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.md)
- [📈time plot](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.001x faster (HPT: reliability of 100.00%, 1.05x slower at 99th %ile)
- Memory usage: 1.46x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.html)
- [📄table](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.md)
- [📈time plot](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.051x slower (HPT: reliability of 100.00%, 1.10x slower at 99th %ile)
- Memory usage: 1.45x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base-mem.html)
- [🧠memory plot](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.html)
- [📄table](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.md)
- [📈time plot](bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.svg)

## linux x86_64 (centurion_gcc15)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json)

### vs. 3.13.0

- Geometric mean: 1.117x faster (HPT: reliability of 90.77%, 1.00x faster at 99th %ile)
- Memory usage: 1.59x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.html)
- [📄table](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.md)
- [📈time plot](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.037x faster (HPT: reliability of 99.96%, 1.01x slower at 99th %ile)
- Memory usage: 1.47x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.html)
- [📄table](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.md)
- [📈time plot](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.015x faster (HPT: reliability of 100.00%, 1.03x slower at 99th %ile)
- Memory usage: 1.45x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base-mem.html)
- [🧠memory plot](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.html)
- [📄table](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.md)
- [📈time plot](bm-20260113-centurion_gcc15-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277.json)

### vs. 3.13.0

- Geometric mean: 1.080x faster (HPT: reliability of 73.70%, 1.00x slower at 99th %ile)
- Memory usage: 1.57x
- missing benchmarks: sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.html)
- [📄table](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.md)
- [📈time plot](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.015x faster (HPT: reliability of 100.00%, 1.03x slower at 99th %ile)
- Memory usage: 1.45x
- missing benchmarks: sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.html)
- [📄table](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.md)
- [📈time plot](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.000x faster (HPT: reliability of 100.00%, 1.04x slower at 99th %ile)
- Memory usage: 1.43x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base-mem.html)
- [🧠memory plot](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260113-3.15.0a4-43cd277-NOGIL/bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.html)
- [📄table](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.md)
- [📈time plot](bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277-vs-base.svg)

