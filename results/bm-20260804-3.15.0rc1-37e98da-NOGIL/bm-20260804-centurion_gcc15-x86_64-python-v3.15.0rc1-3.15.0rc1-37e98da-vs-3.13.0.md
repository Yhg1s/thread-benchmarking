# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.312x faster
- HPT reliability: 80.96%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.62x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.9 ms                                                          | 11.8 ms: 1.08x slower                                                  |
| docutils       | 1.98 sec                                                         | 2.23 sec: 1.13x slower                                                 |
| fastapi_http   | 215 ms                                                           | 182 ms: 1.18x faster                                                   |
| html5lib       | 49.1 ms                                                          | 46.6 ms: 1.05x faster                                                  |
| tornado_http   | 99.2 ms                                                          | 91.9 ms: 1.08x faster                                                  |
| Geometric mean | (ref)                                                            | 1.02x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_io_tg                 | 777 ms                                                           | 536 ms: 1.45x faster                                                   |
| async_tree_eager_io              | 749 ms                                                           | 559 ms: 1.34x faster                                                   |
| async_tree_io                    | 741 ms                                                           | 558 ms: 1.33x faster                                                   |
| async_tree_eager_io_tg           | 724 ms                                                           | 548 ms: 1.32x faster                                                   |
| async_tree_memoization_tg        | 417 ms                                                           | 326 ms: 1.28x faster                                                   |
| coroutines                       | 17.6 ms                                                          | 15.1 ms: 1.16x faster                                                  |
| async_tree_none                  | 310 ms                                                           | 269 ms: 1.15x faster                                                   |
| asyncio_tcp                      | 326 ms                                                           | 286 ms: 1.14x faster                                                   |
| async_tree_memoization           | 389 ms                                                           | 344 ms: 1.13x faster                                                   |
| async_tree_none_tg               | 289 ms                                                           | 256 ms: 1.13x faster                                                   |
| async_tree_eager_memoization     | 215 ms                                                           | 200 ms: 1.07x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 492 ms: 1.07x faster                                                   |
| asyncio_websockets               | 304 ms                                                           | 288 ms: 1.05x faster                                                   |
| async_tree_eager                 | 90.0 ms                                                          | 90.7 ms: 1.01x slower                                                  |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 369 ms: 1.02x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.33 sec: 1.03x slower                                                 |
| async_generators                 | 262 ms                                                           | 281 ms: 1.07x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 486 ms: 1.51x slower                                                   |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 315 ms: 1.82x slower                                                   |
| async_tree_eager_tg              | 58.6 ms                                                          | 228 ms: 3.89x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.01x slower                                                           |

Benchmark hidden because not significant (1): async_tree_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

Benchmark hidden because not significant (1): noop

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                           | 186 ms: 1.08x slower                                                   |
| decimal_pi        | 210 ms                                                           | 236 ms: 1.13x slower                                                   |
| Geometric mean    | (ref)                                                            | 1.10x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| pidigits       | 181 ms                                                           | 179 ms: 1.01x faster                                                   |
| quadtree_nbody | 620 ms                                                           | 625 ms: 1.01x slower                                                   |
| float          | 56.6 ms                                                          | 63.5 ms: 1.12x slower                                                  |
| nbody          | 66.8 ms                                                          | 81.4 ms: 1.22x slower                                                  |
| Geometric mean | (ref)                                                            | 1.08x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 1.99 ms                                                          | 2.05 ms: 1.03x slower                                                  |
| regex_dna      | 144 ms                                                           | 149 ms: 1.04x slower                                                   |
| regex_compile  | 97.7 ms                                                          | 101 ms: 1.04x slower                                                   |
| regex_v8       | 14.7 ms                                                          | 15.5 ms: 1.06x slower                                                  |
| Geometric mean | (ref)                                                            | 1.04x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 286 ms                                                           | 2.10 ms: 136.26x faster                                                |
| ascii85_large        | 814 ms                                                           | 10.1 ms: 80.27x faster                                                 |
| base85_large         | 243 ms                                                           | 3.31 ms: 73.36x faster                                                 |
| ascii85_small        | 15.5 ms                                                          | 485 us: 31.93x faster                                                  |
| base32_small         | 5.69 ms                                                          | 208 us: 27.32x faster                                                  |
| base85_small         | 4.41 ms                                                          | 177 us: 24.94x faster                                                  |
| base16_large         | 31.6 ms                                                          | 7.65 ms: 4.13x faster                                                  |
| base64_large         | 6.32 ms                                                          | 1.55 ms: 4.09x faster                                                  |
| urlsafe_base64_small | 379 us                                                           | 254 us: 1.49x faster                                                   |
| base16_small         | 656 us                                                           | 441 us: 1.49x faster                                                   |
| tomli_loads          | 1.63 sec                                                         | 1.38 sec: 1.18x faster                                                 |
| json_dumps           | 7.49 ms                                                          | 7.09 ms: 1.06x faster                                                  |
| base64_small         | 228 us                                                           | 221 us: 1.03x faster                                                   |
| xml_etree_iterparse  | 69.6 ms                                                          | 70.4 ms: 1.01x slower                                                  |
| pickle_dict          | 21.9 us                                                          | 23.4 us: 1.07x slower                                                  |
| pickle_pure_python   | 223 us                                                           | 242 us: 1.09x slower                                                   |
| unpickle_pure_python | 149 us                                                           | 163 us: 1.10x slower                                                   |
| pickle               | 8.22 us                                                          | 9.49 us: 1.16x slower                                                  |
| unpickle             | 10.3 us                                                          | 12.0 us: 1.17x slower                                                  |
| xml_etree_generate   | 66.3 ms                                                          | 77.7 ms: 1.17x slower                                                  |
| xml_etree_process    | 48.1 ms                                                          | 57.0 ms: 1.19x slower                                                  |
| json_loads           | 16.7 us                                                          | 20.7 us: 1.24x slower                                                  |
| pickle_list          | 3.03 us                                                          | 3.94 us: 1.30x slower                                                  |
| unpickle_list        | 3.45 us                                                          | 4.54 us: 1.32x slower                                                  |
| Geometric mean       | (ref)                                                            | 2.81x faster                                                           |

Benchmark hidden because not significant (1): xml_etree_parse

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.36 ms                                                          | 7.56 ms: 1.19x slower                                                  |
| python_startup         | 9.38 ms                                                          | 11.2 ms: 1.20x slower                                                  |
| Geometric mean         | (ref)                                                            | 1.19x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 27.3 ms                                                          | 31.5 ms: 1.16x slower                                                  |
| mako            | 7.43 ms                                                          | 13.6 ms: 1.83x slower                                                  |
| Geometric mean  | (ref)                                                            | 1.45x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 220 ms                                                           | 55.3 ms: 3.98x faster                                                  |
| thread_mandelbrot_optimized | 218 ms                                                           | 55.8 ms: 3.90x faster                                                  |
| thread_pipeline_optimized   | 25.6 ms                                                          | 7.38 ms: 3.47x faster                                                  |
| thread_accumulate_optimized | 39.8 ms                                                          | 11.8 ms: 3.36x faster                                                  |
| thread_counter_optimized    | 18.7 ms                                                          | 5.67 ms: 3.30x faster                                                  |
| thread_accumulate_naive     | 40.9 ms                                                          | 12.6 ms: 3.25x faster                                                  |
| thread_memo_optimized       | 18.2 ms                                                          | 6.17 ms: 2.95x faster                                                  |
| thread_montecarlo_optimized | 13.3 ms                                                          | 4.63 ms: 2.88x faster                                                  |
| thread_pipeline_naive       | 52.1 ms                                                          | 20.2 ms: 2.58x faster                                                  |
| thread_memo_naive           | 39.0 ms                                                          | 22.2 ms: 1.76x faster                                                  |
| thread_counter_naive        | 22.6 ms                                                          | 13.1 ms: 1.73x faster                                                  |
| thread_montecarlo_naive     | 17.8 ms                                                          | 35.8 ms: 2.01x slower                                                  |
| Geometric mean              | (ref)                                                            | 2.52x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 286 ms                                                           | 2.10 ms: 136.26x faster                                                |
| ascii85_large                    | 814 ms                                                           | 10.1 ms: 80.27x faster                                                 |
| base85_large                     | 243 ms                                                           | 3.31 ms: 73.36x faster                                                 |
| ascii85_small                    | 15.5 ms                                                          | 485 us: 31.93x faster                                                  |
| base32_small                     | 5.69 ms                                                          | 208 us: 27.32x faster                                                  |
| base85_small                     | 4.41 ms                                                          | 177 us: 24.94x faster                                                  |
| base16_large                     | 31.6 ms                                                          | 7.65 ms: 4.13x faster                                                  |
| base64_large                     | 6.32 ms                                                          | 1.55 ms: 4.09x faster                                                  |
| thread_mandelbrot_naive          | 220 ms                                                           | 55.3 ms: 3.98x faster                                                  |
| thread_mandelbrot_optimized      | 218 ms                                                           | 55.8 ms: 3.90x faster                                                  |
| thread_pipeline_optimized        | 25.6 ms                                                          | 7.38 ms: 3.47x faster                                                  |
| thread_accumulate_optimized      | 39.8 ms                                                          | 11.8 ms: 3.36x faster                                                  |
| thread_counter_optimized         | 18.7 ms                                                          | 5.67 ms: 3.30x faster                                                  |
| thread_accumulate_naive          | 40.9 ms                                                          | 12.6 ms: 3.25x faster                                                  |
| thread_memo_optimized            | 18.2 ms                                                          | 6.17 ms: 2.95x faster                                                  |
| thread_montecarlo_optimized      | 13.3 ms                                                          | 4.63 ms: 2.88x faster                                                  |
| thread_pipeline_naive            | 52.1 ms                                                          | 20.2 ms: 2.58x faster                                                  |
| pylint                           | 226 ms                                                           | 91.3 ms: 2.48x faster                                                  |
| gc_traversal                     | 3.16 ms                                                          | 1.34 ms: 2.36x faster                                                  |
| mdp                              | 2.11 sec                                                         | 984 ms: 2.14x faster                                                   |
| thread_memo_naive                | 39.0 ms                                                          | 22.2 ms: 1.76x faster                                                  |
| thread_counter_naive             | 22.6 ms                                                          | 13.1 ms: 1.73x faster                                                  |
| argparse_many_optionals          | 12.6 ms                                                          | 8.11 ms: 1.55x faster                                                  |
| urlsafe_base64_small             | 379 us                                                           | 254 us: 1.49x faster                                                   |
| base16_small                     | 656 us                                                           | 441 us: 1.49x faster                                                   |
| create_gc_cycles                 | 1.70 ms                                                          | 1.17 ms: 1.46x faster                                                  |
| async_tree_io_tg                 | 777 ms                                                           | 536 ms: 1.45x faster                                                   |
| deepcopy                         | 267 us                                                           | 196 us: 1.36x faster                                                   |
| go                               | 121 ms                                                           | 89.7 ms: 1.35x faster                                                  |
| async_tree_eager_io              | 749 ms                                                           | 559 ms: 1.34x faster                                                   |
| async_tree_io                    | 741 ms                                                           | 558 ms: 1.33x faster                                                   |
| async_tree_eager_io_tg           | 724 ms                                                           | 548 ms: 1.32x faster                                                   |
| deepcopy_memo                    | 26.6 us                                                          | 20.7 us: 1.28x faster                                                  |
| async_tree_memoization_tg        | 417 ms                                                           | 326 ms: 1.28x faster                                                   |
| scimark_sor                      | 97.0 ms                                                          | 78.7 ms: 1.23x faster                                                  |
| tomli_loads                      | 1.63 sec                                                         | 1.38 sec: 1.18x faster                                                 |
| fastapi_http                     | 215 ms                                                           | 182 ms: 1.18x faster                                                   |
| pathlib                          | 12.4 ms                                                          | 10.6 ms: 1.17x faster                                                  |
| coroutines                       | 17.6 ms                                                          | 15.1 ms: 1.16x faster                                                  |
| async_tree_none                  | 310 ms                                                           | 269 ms: 1.15x faster                                                   |
| asyncio_tcp                      | 326 ms                                                           | 286 ms: 1.14x faster                                                   |
| async_tree_memoization           | 389 ms                                                           | 344 ms: 1.13x faster                                                   |
| async_tree_none_tg               | 289 ms                                                           | 256 ms: 1.13x faster                                                   |
| pyflate                          | 358 ms                                                           | 324 ms: 1.11x faster                                                   |
| bpe_tokeniser                    | 3.40 sec                                                         | 3.14 sec: 1.09x faster                                                 |
| thrift                           | 2.07 ms                                                          | 1.91 ms: 1.08x faster                                                  |
| tornado_http                     | 99.2 ms                                                          | 91.9 ms: 1.08x faster                                                  |
| async_tree_eager_memoization     | 215 ms                                                           | 200 ms: 1.07x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 527 ms                                                           | 492 ms: 1.07x faster                                                   |
| pycparser                        | 884 ms                                                           | 828 ms: 1.07x faster                                                   |
| deepcopy_reduce                  | 2.37 us                                                          | 2.24 us: 1.06x faster                                                  |
| json_dumps                       | 7.49 ms                                                          | 7.09 ms: 1.06x faster                                                  |
| html5lib                         | 49.1 ms                                                          | 46.6 ms: 1.05x faster                                                  |
| asyncio_websockets               | 304 ms                                                           | 288 ms: 1.05x faster                                                   |
| base64_small                     | 228 us                                                           | 221 us: 1.03x faster                                                   |
| chaos                            | 45.0 ms                                                          | 44.2 ms: 1.02x faster                                                  |
| pidigits                         | 181 ms                                                           | 179 ms: 1.01x faster                                                   |
| hexiom                           | 4.42 ms                                                          | 4.37 ms: 1.01x faster                                                  |
| pprint_safe_repr                 | 541 ms                                                           | 539 ms: 1.00x faster                                                   |
| async_tree_eager                 | 90.0 ms                                                          | 90.7 ms: 1.01x slower                                                  |
| quadtree_nbody                   | 620 ms                                                           | 625 ms: 1.01x slower                                                   |
| xml_etree_iterparse              | 69.6 ms                                                          | 70.4 ms: 1.01x slower                                                  |
| sqlglot_v2_transpile             | 1.20 ms                                                          | 1.21 ms: 1.01x slower                                                  |
| scimark_fft                      | 211 ms                                                           | 214 ms: 1.02x slower                                                   |
| sqlglot_v2_optimize              | 40.0 ms                                                          | 40.8 ms: 1.02x slower                                                  |
| sqlglot_v2_parse                 | 953 us                                                           | 974 us: 1.02x slower                                                   |
| pprint_pformat                   | 1.11 sec                                                         | 1.13 sec: 1.02x slower                                                 |
| generators                       | 22.0 ms                                                          | 22.5 ms: 1.02x slower                                                  |
| async_tree_eager_cpu_io_mixed    | 360 ms                                                           | 369 ms: 1.02x slower                                                   |
| regex_effbot                     | 1.99 ms                                                          | 2.05 ms: 1.03x slower                                                  |
| sympy_integrate                  | 15.4 ms                                                          | 15.9 ms: 1.03x slower                                                  |
| telco                            | 5.50 ms                                                          | 5.67 ms: 1.03x slower                                                  |
| logging_silent                   | 60.6 ns                                                          | 62.5 ns: 1.03x slower                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.33 sec: 1.03x slower                                                 |
| comprehensions                   | 11.6 us                                                          | 12.0 us: 1.03x slower                                                  |
| regex_dna                        | 144 ms                                                           | 149 ms: 1.04x slower                                                   |
| regex_compile                    | 97.7 ms                                                          | 101 ms: 1.04x slower                                                   |
| richards_super                   | 41.3 ms                                                          | 43.0 ms: 1.04x slower                                                  |
| sqlglot_v2_normalize             | 79.1 ms                                                          | 83.2 ms: 1.05x slower                                                  |
| scimark_monte_carlo              | 44.3 ms                                                          | 46.7 ms: 1.05x slower                                                  |
| deltablue                        | 2.52 ms                                                          | 2.66 ms: 1.06x slower                                                  |
| regex_v8                         | 14.7 ms                                                          | 15.5 ms: 1.06x slower                                                  |
| json                             | 3.49 ms                                                          | 3.72 ms: 1.06x slower                                                  |
| meteor_contest                   | 89.9 ms                                                          | 95.7 ms: 1.06x slower                                                  |
| sympy_sum                        | 104 ms                                                           | 111 ms: 1.06x slower                                                   |
| nqueens                          | 57.3 ms                                                          | 61.1 ms: 1.07x slower                                                  |
| sympy_str                        | 193 ms                                                           | 206 ms: 1.07x slower                                                   |
| pickle_dict                      | 21.9 us                                                          | 23.4 us: 1.07x slower                                                  |
| logging_format                   | 5.23 us                                                          | 5.60 us: 1.07x slower                                                  |
| async_generators                 | 262 ms                                                           | 281 ms: 1.07x slower                                                   |
| networkx_k_core                  | 2.15 sec                                                         | 2.31 sec: 1.07x slower                                                 |
| logging_simple                   | 4.60 us                                                          | 4.96 us: 1.08x slower                                                  |
| sympy_expand                     | 330 ms                                                           | 356 ms: 1.08x slower                                                   |
| decimal_factorial                | 173 ms                                                           | 186 ms: 1.08x slower                                                   |
| chameleon                        | 10.9 ms                                                          | 11.8 ms: 1.08x slower                                                  |
| pickle_pure_python               | 223 us                                                           | 242 us: 1.09x slower                                                   |
| xdsl_constant_fold               | 36.7 ms                                                          | 39.9 ms: 1.09x slower                                                  |
| spectral_norm                    | 64.1 ms                                                          | 69.8 ms: 1.09x slower                                                  |
| raytrace                         | 199 ms                                                           | 218 ms: 1.10x slower                                                   |
| unpickle_pure_python             | 149 us                                                           | 163 us: 1.10x slower                                                   |
| argparse_subparsers              | 446 us                                                           | 491 us: 1.10x slower                                                   |
| scimark_lu                       | 70.2 ms                                                          | 78.0 ms: 1.11x slower                                                  |
| float                            | 56.6 ms                                                          | 63.5 ms: 1.12x slower                                                  |
| decimal_pi                       | 210 ms                                                           | 236 ms: 1.13x slower                                                   |
| fannkuch                         | 265 ms                                                           | 299 ms: 1.13x slower                                                   |
| docutils                         | 1.98 sec                                                         | 2.23 sec: 1.13x slower                                                 |
| sqlalchemy_imperative            | 13.8 ms                                                          | 15.7 ms: 1.14x slower                                                  |
| pickle                           | 8.22 us                                                          | 9.49 us: 1.16x slower                                                  |
| django_template                  | 27.3 ms                                                          | 31.5 ms: 1.16x slower                                                  |
| unpickle                         | 10.3 us                                                          | 12.0 us: 1.17x slower                                                  |
| xml_etree_generate               | 66.3 ms                                                          | 77.7 ms: 1.17x slower                                                  |
| mypy2                            | 726 ms                                                           | 853 ms: 1.17x slower                                                   |
| xml_etree_process                | 48.1 ms                                                          | 57.0 ms: 1.19x slower                                                  |
| unpack_sequence                  | 26.2 ns                                                          | 31.2 ns: 1.19x slower                                                  |
| python_startup_no_site           | 6.36 ms                                                          | 7.56 ms: 1.19x slower                                                  |
| networkx_connected_components    | 460 ms                                                           | 547 ms: 1.19x slower                                                   |
| python_startup                   | 9.38 ms                                                          | 11.2 ms: 1.20x slower                                                  |
| scimark_sparse_mat_mult          | 2.66 ms                                                          | 3.20 ms: 1.20x slower                                                  |
| networkx_shortest_path           | 464 ms                                                           | 560 ms: 1.21x slower                                                   |
| nbody                            | 66.8 ms                                                          | 81.4 ms: 1.22x slower                                                  |
| json_loads                       | 16.7 us                                                          | 20.7 us: 1.24x slower                                                  |
| typing_runtime_protocols         | 106 us                                                           | 131 us: 1.24x slower                                                   |
| pickle_list                      | 3.03 us                                                          | 3.94 us: 1.30x slower                                                  |
| crypto_pyaes                     | 50.0 ms                                                          | 65.5 ms: 1.31x slower                                                  |
| unpickle_list                    | 3.45 us                                                          | 4.54 us: 1.32x slower                                                  |
| coverage                         | 52.2 ms                                                          | 74.5 ms: 1.43x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 321 ms                                                           | 486 ms: 1.51x slower                                                   |
| async_tree_eager_memoization_tg  | 173 ms                                                           | 315 ms: 1.82x slower                                                   |
| mako                             | 7.43 ms                                                          | 13.6 ms: 1.83x slower                                                  |
| thread_montecarlo_naive          | 17.8 ms                                                          | 35.8 ms: 2.01x slower                                                  |
| async_tree_eager_tg              | 58.6 ms                                                          | 228 ms: 3.89x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.31x faster                                                           |

Benchmark hidden because not significant (4): xml_etree_parse, noop, async_tree_cpu_io_mixed, richards
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_gcc15-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.312x faster

# HPT report

- Reliability score: 80.96% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.62x