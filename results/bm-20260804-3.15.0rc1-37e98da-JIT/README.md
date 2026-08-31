# Results

- fork: python/v3.15.0rc1
- version: 3.15.0rc1
- config: JIT
- commit hash: [37e98da](https://github.com/python/cpython/commit/37e98da)
- commit date: 2026-08-04T14:07:27+03:00
- ref: v3.15.0rc1

## linux x86_64 (centurion_clang22)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da.json)

### vs. 3.13.0

- Geometric mean: 1.361x faster (HPT: reliability of 100.00%, 1.05x faster at 99th %ile)
- Memory usage: 1.17x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.html)
- [📄table](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.md)
- [📈time plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.278x faster (HPT: reliability of 98.05%, 1.00x faster at 99th %ile)
- Memory usage: 1.07x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.html)
- [📄table](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.md)
- [📈time plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.060x faster (HPT: reliability of 100.00%, 1.02x faster at 99th %ile)
- Memory usage: 1.03x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.html)
- [🧠memory plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.html)
- [📄table](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.md)
- [📈time plot](bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.svg)

## linux x86_64 (centurion_gcc15)

- [GitHub Action run](https://github.com/faster-cpython/bench_runner/actions/runs/False)
- cpu model: Intel(R) Core(TM) Ultra 7 265K
- platform: Linux-6.12.20-amd64-x86_64-with-glibc2.42
- [raw results](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da.json)

### vs. 3.13.0

- Geometric mean: 1.384x faster (HPT: reliability of 100.00%, 1.08x faster at 99th %ile)
- Memory usage: 1.12x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.html)
- [📄table](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.md)
- [📈time plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.13.0.svg)

### vs. 3.14.0

- Geometric mean: 1.281x faster (HPT: reliability of 99.89%, 1.01x faster at 99th %ile)
- Memory usage: 1.04x
- missing benchmarks: genshi_text, genshi_xml
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.html)
- [📄table](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.md)
- [📈time plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-3.14.0.svg)

### vs. base

- Geometric mean: 1.064x faster (HPT: reliability of 100.00%, 1.03x faster at 99th %ile)
- Memory usage: 1.02x
- [🔬interactive memory plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.html)
- [🧠memory plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base-mem.svg)
- [🔍interactive time plot](https://yhg1s.github.io/thread-benchmarking/results/bm-20260804-3.15.0rc1-37e98da-JIT/bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.html)
- [📄table](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.md)
- [📈time plot](bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da-vs-base.svg)

