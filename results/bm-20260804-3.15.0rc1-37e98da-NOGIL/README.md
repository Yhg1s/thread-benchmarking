# Results

- fork: python/v3.15.0rc1
- version: 3.15.0rc1
- config: NOGIL
- commit hash: [37e98da](https://github.com/python/cpython/commit/37e98da)
- commit date: 2026-08-04T14:07:27+03:00
- ref: v3.15.0rc1

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da.json)

### vs. 3.13.0

- Geometric mean: 1.345x faster (HPT: reliability of 99.44%, 1.00x faster at 99th %ile)
- Memory usage: 1.61x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.html)
- [📄table](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.md)
- [📈time plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.265x faster (HPT: reliability of 99.22%, 1.00x slower at 99th %ile)
- Memory usage: 1.48x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.html)
- [📄table](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.md)
- [📈time plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.051x faster (HPT: reliability of 98.32%, 1.00x slower at 99th %ile)
- Memory usage: 1.57x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.html)
- [🧠memory plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.html)
- [📄table](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.md)
- [📈time plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.svg)

## linux x86_64 (centurion_gcc15)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da.json)

### vs. 3.13.0

- Geometric mean: 1.312x faster (HPT: reliability of 80.96%, 1.00x faster at 99th %ile)
- Memory usage: 1.62x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.html)
- [📄table](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.md)
- [📈time plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.216x faster (HPT: reliability of 100.00%, 1.03x slower at 99th %ile)
- Memory usage: 1.50x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.html)
- [📄table](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.md)
- [📈time plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.013x faster (HPT: reliability of 100.00%, 1.03x slower at 99th %ile)
- Memory usage: 1.60x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.html)
- [🧠memory plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.html)
- [📄table](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.md)
- [📈time plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.svg)

## linux x86_64 (centurion_gcc9)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da.json)

### vs. 3.13.0

- Geometric mean: 1.268x faster (HPT: reliability of 61.23%, 1.00x slower at 99th %ile)
- Memory usage: 1.64x
- missing benchmarks: genshi_text, genshi_xml, sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.html)
- [📄table](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.md)
- [📈time plot](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.192x faster (HPT: reliability of 100.00%, 1.05x slower at 99th %ile)
- Memory usage: 1.48x
- missing benchmarks: genshi_text, genshi_xml, sqlalchemy_imperative
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.html)
- [📄table](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.md)
- [📈time plot](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.024x faster (HPT: reliability of 100.00%, 1.03x slower at 99th %ile)
- Memory usage: 1.57x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.html)
- [🧠memory plot](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-NOGIL/bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.html)
- [📄table](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.md)
- [📈time plot](bm-20260804-centurion_gcc9-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.svg)

