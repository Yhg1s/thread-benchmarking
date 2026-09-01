# Results

- fork: python/v3.14.7
- version: 3.14.7
- config: JIT
- commit hash: [823f032](https://github.com/python/cpython/commit/823f032)
- commit date: 2026-08-05T13:29:49+03:00
- ref: v3.14.7

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032.json)

### vs. 3.13.0

- Geometric mean: 1.047x faster (HPT: reliability of 88.32%, 1.00x faster at 99th %ile)
- Memory usage: 1.09x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.html)
- [📄table](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.md)
- [📈time plot](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.018x slower (HPT: reliability of 99.60%, 1.00x slower at 99th %ile)
- Memory usage: 1.00x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.html)
- [📄table](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.md)
- [📈time plot](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.010x slower (HPT: reliability of 97.09%, 1.00x slower at 99th %ile)
- Memory usage: 1.00x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-base-mem.html)
- [🧠memory plot](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.html)
- [📄table](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.md)
- [📈time plot](bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.svg)

## linux x86_64 (centurion_gcc15)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032.json)

### vs. 3.13.0

- Geometric mean: 1.071x faster (HPT: reliability of 100.00%, 1.02x faster at 99th %ile)
- Memory usage: 1.09x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.html)
- [📄table](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.md)
- [📈time plot](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.007x slower (HPT: reliability of 52.87%, 1.00x slower at 99th %ile)
- Memory usage: 1.01x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.html)
- [📄table](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.md)
- [📈time plot](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.004x slower (HPT: reliability of 99.86%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-base-mem.html)
- [🧠memory plot](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.html)
- [📄table](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.md)
- [📈time plot](bm-20260805-centurion_gcc15-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032.json)

### vs. 3.13.0

- Geometric mean: 1.043x faster (HPT: reliability of 98.32%, 1.00x faster at 99th %ile)
- Memory usage: 1.07x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.html)
- [📄table](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.md)
- [📈time plot](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.019x slower (HPT: reliability of 99.61%, 1.00x slower at 99th %ile)
- Memory usage: 1.02x
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.html)
- [📄table](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.md)
- [📈time plot](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.000x faster (HPT: reliability of 85.84%, 1.00x faster at 99th %ile)
- Memory usage: 1.01x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-base-mem.html)
- [🧠memory plot](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260805-3.14.7-823f032-JIT/bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.html)
- [📄table](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.md)
- [📈time plot](bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032-vs-base.svg)

