# Results

- fork: python/v3.14.0
- version: 3.14.0
- config: JIT
- commit hash: [ebf955d](https://github.com/python/cpython/commit/ebf955d)
- commit date: 2025-10-07T12:34:52+03:00
- ref: v3.14.0

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json)

### vs. 3.13.0

- Geometric mean: 1.053x faster (HPT: reliability of 98.18%, 1.00x faster at 99th %ile)
- Memory usage: 1.10x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.html)
- [📄table](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.md)
- [📈time plot](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.013x slower (HPT: reliability of 99.38%, 1.00x slower at 99th %ile)
- Memory usage: 1.01x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.html)
- [📄table](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.md)
- [📈time plot](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.013x slower (HPT: reliability of 99.38%, 1.00x slower at 99th %ile)
- Memory usage: 1.01x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base-mem.html)
- [🧠memory plot](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.html)
- [📄table](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.md)
- [📈time plot](bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.svg)

## linux x86_64 (centurion_gcc15)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json)

### vs. 3.13.0

- Geometric mean: 1.079x faster (HPT: reliability of 100.00%, 1.02x faster at 99th %ile)
- Memory usage: 1.08x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.html)
- [📄table](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.md)
- [📈time plot](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.001x slower (HPT: reliability of 98.80%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.html)
- [📄table](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.md)
- [📈time plot](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.001x slower (HPT: reliability of 98.80%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base-mem.html)
- [🧠memory plot](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.html)
- [📄table](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.md)
- [📈time plot](bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json)

### vs. 3.13.0

- Geometric mean: 1.058x faster (HPT: reliability of 99.88%, 1.00x faster at 99th %ile)
- Memory usage: 1.04x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.html)
- [📄table](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.md)
- [📈time plot](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.006x slower (HPT: reliability of 95.41%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.html)
- [📄table](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.md)
- [📈time plot](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.006x slower (HPT: reliability of 95.41%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base-mem.html)
- [🧠memory plot](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20251007-3.14.0-ebf955d-JIT/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.html)
- [📄table](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.md)
- [📈time plot](bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d-vs-base.svg)

