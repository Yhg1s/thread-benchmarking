# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.345x faster
- HPT reliability: 99.44%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.61x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 11.2 ms: 1.01x slower                                                    |
| docutils       | 1.89 sec                                                           | 2.17 sec: 1.15x slower                                                   |
| fastapi_http   | 215 ms                                                             | 191 ms: 1.13x faster                                                     |
| html5lib       | 50.9 ms                                                            | 46.8 ms: 1.09x faster                                                    |
| tornado_http   | 98.9 ms                                                            | 93.9 ms: 1.05x faster                                                    |
| Geometric mean | (ref)                                                              | 1.02x faster                                                             |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 532 ms: 1.47x faster                                                     |
| async_tree_eager_io_tg           | 731 ms                                                             | 546 ms: 1.34x faster                                                     |
| async_tree_eager_io              | 753 ms                                                             | 564 ms: 1.33x faster                                                     |
| async_tree_io                    | 743 ms                                                             | 559 ms: 1.33x faster                                                     |
| async_tree_memoization_tg        | 421 ms                                                             | 322 ms: 1.31x faster                                                     |
| coroutines                       | 18.2 ms                                                            | 15.2 ms: 1.20x faster                                                    |
| async_tree_none                  | 312 ms                                                             | 271 ms: 1.15x faster                                                     |
| async_tree_none_tg               | 290 ms                                                             | 252 ms: 1.15x faster                                                     |
| async_tree_memoization           | 392 ms                                                             | 347 ms: 1.13x faster                                                     |
| asyncio_tcp                      | 316 ms                                                             | 287 ms: 1.10x faster                                                     |
| asyncio_websockets               | 313 ms                                                             | 287 ms: 1.09x faster                                                     |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 465 ms: 1.09x faster                                                     |
| async_tree_eager_memoization     | 221 ms                                                             | 204 ms: 1.08x faster                                                     |
| async_generators                 | 251 ms                                                             | 248 ms: 1.01x faster                                                     |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 348 ms: 1.02x slower                                                     |
| async_tree_eager                 | 88.3 ms                                                            | 90.4 ms: 1.02x slower                                                    |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.33 sec: 1.04x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 461 ms: 1.53x slower                                                     |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 309 ms: 1.77x slower                                                     |
| async_tree_eager_tg              | 56.8 ms                                                            | 226 ms: 3.98x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.00x slower                                                             |

Benchmark hidden because not significant (1): async_tree_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 20.6 ns: 1.04x faster                                                    |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| decimal_factorial | 177 ms                                                             | 189 ms: 1.07x slower                                                     |
| decimal_pi        | 228 ms                                                             | 245 ms: 1.07x slower                                                     |
| Geometric mean    | (ref)                                                              | 1.07x slower                                                             |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| quadtree_nbody | 675 ms                                                             | 655 ms: 1.03x faster                                                     |
| pidigits       | 216 ms                                                             | 215 ms: 1.00x faster                                                     |
| float          | 59.2 ms                                                            | 63.9 ms: 1.08x slower                                                    |
| nbody          | 75.8 ms                                                            | 82.4 ms: 1.09x slower                                                    |
| Geometric mean | (ref)                                                              | 1.03x slower                                                             |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| regex_dna      | 159 ms                                                             | 154 ms: 1.03x faster                                                     |
| regex_compile  | 102 ms                                                             | 103 ms: 1.01x slower                                                     |
| regex_v8       | 15.0 ms                                                            | 15.7 ms: 1.05x slower                                                    |
| Geometric mean | (ref)                                                              | 1.00x slower                                                             |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large         | 325 ms                                                             | 1.91 ms: 169.73x faster                                                  |
| ascii85_large        | 824 ms                                                             | 13.8 ms: 59.77x faster                                                   |
| base85_large         | 267 ms                                                             | 5.17 ms: 51.61x faster                                                   |
| base32_small         | 6.46 ms                                                            | 185 us: 34.82x faster                                                    |
| ascii85_small        | 15.7 ms                                                            | 512 us: 30.75x faster                                                    |
| base85_small         | 4.85 ms                                                            | 192 us: 25.30x faster                                                    |
| base16_large         | 42.7 ms                                                            | 6.27 ms: 6.81x faster                                                    |
| base64_large         | 5.69 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| base16_small         | 836 us                                                             | 330 us: 2.53x faster                                                     |
| urlsafe_base64_small | 328 us                                                             | 224 us: 1.46x faster                                                     |
| tomli_loads          | 1.77 sec                                                           | 1.39 sec: 1.27x faster                                                   |
| xml_etree_iterparse  | 86.8 ms                                                            | 73.8 ms: 1.18x faster                                                    |
| base64_small         | 222 us                                                             | 208 us: 1.07x faster                                                     |
| xml_etree_parse      | 121 ms                                                             | 116 ms: 1.04x faster                                                     |
| xml_etree_generate   | 70.6 ms                                                            | 67.9 ms: 1.04x faster                                                    |
| json_dumps           | 7.26 ms                                                            | 7.02 ms: 1.03x faster                                                    |
| unpickle_pure_python | 161 us                                                             | 165 us: 1.03x slower                                                     |
| xml_etree_process    | 49.9 ms                                                            | 51.2 ms: 1.03x slower                                                    |
| pickle_pure_python   | 245 us                                                             | 256 us: 1.05x slower                                                     |
| pickle_dict          | 19.0 us                                                            | 20.3 us: 1.07x slower                                                    |
| unpickle             | 10.8 us                                                            | 11.9 us: 1.10x slower                                                    |
| json_loads           | 18.2 us                                                            | 20.5 us: 1.13x slower                                                    |
| pickle               | 7.21 us                                                            | 8.16 us: 1.13x slower                                                    |
| pickle_list          | 2.66 us                                                            | 3.38 us: 1.27x slower                                                    |
| Geometric mean       | (ref)                                                              | 3.03x faster                                                             |

Benchmark hidden because not significant (1): unpickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 7.73 ms: 1.19x slower                                                    |
| python_startup         | 9.51 ms                                                            | 11.4 ms: 1.20x slower                                                    |
| Geometric mean         | (ref)                                                              | 1.19x slower                                                             |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| django_template | 28.8 ms                                                            | 32.4 ms: 1.13x slower                                                    |
| mako            | 8.30 ms                                                            | 11.5 ms: 1.38x slower                                                    |
| Geometric mean  | (ref)                                                              | 1.25x slower                                                             |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 190 ms                                                             | 51.3 ms: 3.69x faster                                                    |
| thread_mandelbrot_optimized | 189 ms                                                             | 51.7 ms: 3.66x faster                                                    |
| thread_counter_optimized    | 19.7 ms                                                            | 5.65 ms: 3.49x faster                                                    |
| thread_montecarlo_optimized | 14.2 ms                                                            | 4.34 ms: 3.27x faster                                                    |
| thread_pipeline_optimized   | 22.8 ms                                                            | 6.99 ms: 3.25x faster                                                    |
| thread_accumulate_optimized | 35.3 ms                                                            | 10.9 ms: 3.22x faster                                                    |
| thread_accumulate_naive     | 36.5 ms                                                            | 11.7 ms: 3.12x faster                                                    |
| thread_memo_optimized       | 16.8 ms                                                            | 5.70 ms: 2.95x faster                                                    |
| thread_pipeline_naive       | 49.8 ms                                                            | 19.5 ms: 2.56x faster                                                    |
| thread_counter_naive        | 23.7 ms                                                            | 12.5 ms: 1.90x faster                                                    |
| thread_memo_naive           | 37.9 ms                                                            | 21.7 ms: 1.74x faster                                                    |
| thread_montecarlo_naive     | 18.1 ms                                                            | 35.5 ms: 1.95x slower                                                    |
| Geometric mean              | (ref)                                                              | 2.52x faster                                                             |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large                     | 325 ms                                                             | 1.91 ms: 169.73x faster                                                  |
| ascii85_large                    | 824 ms                                                             | 13.8 ms: 59.77x faster                                                   |
| base85_large                     | 267 ms                                                             | 5.17 ms: 51.61x faster                                                   |
| base32_small                     | 6.46 ms                                                            | 185 us: 34.82x faster                                                    |
| ascii85_small                    | 15.7 ms                                                            | 512 us: 30.75x faster                                                    |
| base85_small                     | 4.85 ms                                                            | 192 us: 25.30x faster                                                    |
| base16_large                     | 42.7 ms                                                            | 6.27 ms: 6.81x faster                                                    |
| thread_mandelbrot_naive          | 190 ms                                                             | 51.3 ms: 3.69x faster                                                    |
| thread_mandelbrot_optimized      | 189 ms                                                             | 51.7 ms: 3.66x faster                                                    |
| base64_large                     | 5.69 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| thread_counter_optimized         | 19.7 ms                                                            | 5.65 ms: 3.49x faster                                                    |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 4.34 ms: 3.27x faster                                                    |
| thread_pipeline_optimized        | 22.8 ms                                                            | 6.99 ms: 3.25x faster                                                    |
| thread_accumulate_optimized      | 35.3 ms                                                            | 10.9 ms: 3.22x faster                                                    |
| thread_accumulate_naive          | 36.5 ms                                                            | 11.7 ms: 3.12x faster                                                    |
| thread_memo_optimized            | 16.8 ms                                                            | 5.70 ms: 2.95x faster                                                    |
| thread_pipeline_naive            | 49.8 ms                                                            | 19.5 ms: 2.56x faster                                                    |
| base16_small                     | 836 us                                                             | 330 us: 2.53x faster                                                     |
| pylint                           | 226 ms                                                             | 91.3 ms: 2.48x faster                                                    |
| gc_traversal                     | 3.20 ms                                                            | 1.52 ms: 2.11x faster                                                    |
| mdp                              | 2.05 sec                                                           | 993 ms: 2.07x faster                                                     |
| thread_counter_naive             | 23.7 ms                                                            | 12.5 ms: 1.90x faster                                                    |
| thread_memo_naive                | 37.9 ms                                                            | 21.7 ms: 1.74x faster                                                    |
| argparse_many_optionals          | 12.9 ms                                                            | 8.53 ms: 1.52x faster                                                    |
| create_gc_cycles                 | 1.77 ms                                                            | 1.20 ms: 1.47x faster                                                    |
| async_tree_io_tg                 | 781 ms                                                             | 532 ms: 1.47x faster                                                     |
| urlsafe_base64_small             | 328 us                                                             | 224 us: 1.46x faster                                                     |
| deepcopy_memo                    | 27.8 us                                                            | 19.9 us: 1.39x faster                                                    |
| deepcopy                         | 267 us                                                             | 194 us: 1.37x faster                                                     |
| go                               | 129 ms                                                             | 94.9 ms: 1.36x faster                                                    |
| async_tree_eager_io_tg           | 731 ms                                                             | 546 ms: 1.34x faster                                                     |
| async_tree_eager_io              | 753 ms                                                             | 564 ms: 1.33x faster                                                     |
| async_tree_io                    | 743 ms                                                             | 559 ms: 1.33x faster                                                     |
| async_tree_memoization_tg        | 421 ms                                                             | 322 ms: 1.31x faster                                                     |
| tomli_loads                      | 1.77 sec                                                           | 1.39 sec: 1.27x faster                                                   |
| scimark_sor                      | 96.2 ms                                                            | 78.5 ms: 1.23x faster                                                    |
| coroutines                       | 18.2 ms                                                            | 15.2 ms: 1.20x faster                                                    |
| xml_etree_iterparse              | 86.8 ms                                                            | 73.8 ms: 1.18x faster                                                    |
| pyflate                          | 374 ms                                                             | 321 ms: 1.16x faster                                                     |
| pathlib                          | 12.2 ms                                                            | 10.6 ms: 1.16x faster                                                    |
| async_tree_none                  | 312 ms                                                             | 271 ms: 1.15x faster                                                     |
| async_tree_none_tg               | 290 ms                                                             | 252 ms: 1.15x faster                                                     |
| async_tree_memoization           | 392 ms                                                             | 347 ms: 1.13x faster                                                     |
| fastapi_http                     | 215 ms                                                             | 191 ms: 1.13x faster                                                     |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.05 sec: 1.10x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 287 ms: 1.10x faster                                                     |
| asyncio_websockets               | 313 ms                                                             | 287 ms: 1.09x faster                                                     |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 465 ms: 1.09x faster                                                     |
| html5lib                         | 50.9 ms                                                            | 46.8 ms: 1.09x faster                                                    |
| deepcopy_reduce                  | 2.36 us                                                            | 2.17 us: 1.09x faster                                                    |
| async_tree_eager_memoization     | 221 ms                                                             | 204 ms: 1.08x faster                                                     |
| base64_small                     | 222 us                                                             | 208 us: 1.07x faster                                                     |
| richards                         | 38.2 ms                                                            | 36.0 ms: 1.06x faster                                                    |
| thrift                           | 2.07 ms                                                            | 1.97 ms: 1.05x faster                                                    |
| tornado_http                     | 98.9 ms                                                            | 93.9 ms: 1.05x faster                                                    |
| richards_super                   | 43.8 ms                                                            | 41.7 ms: 1.05x faster                                                    |
| fannkuch                         | 287 ms                                                             | 274 ms: 1.05x faster                                                     |
| xml_etree_parse                  | 121 ms                                                             | 116 ms: 1.04x faster                                                     |
| xml_etree_generate               | 70.6 ms                                                            | 67.9 ms: 1.04x faster                                                    |
| noop                             | 21.4 ns                                                            | 20.6 ns: 1.04x faster                                                    |
| regex_dna                        | 159 ms                                                             | 154 ms: 1.03x faster                                                     |
| json_dumps                       | 7.26 ms                                                            | 7.02 ms: 1.03x faster                                                    |
| quadtree_nbody                   | 675 ms                                                             | 655 ms: 1.03x faster                                                     |
| pycparser                        | 901 ms                                                             | 878 ms: 1.03x faster                                                     |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 41.1 ms: 1.03x faster                                                    |
| async_generators                 | 251 ms                                                             | 248 ms: 1.01x faster                                                     |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 82.8 ms: 1.01x faster                                                    |
| scimark_monte_carlo              | 47.2 ms                                                            | 46.8 ms: 1.01x faster                                                    |
| pidigits                         | 216 ms                                                             | 215 ms: 1.00x faster                                                     |
| comprehensions                   | 11.4 us                                                            | 11.5 us: 1.01x slower                                                    |
| chameleon                        | 11.1 ms                                                            | 11.2 ms: 1.01x slower                                                    |
| regex_compile                    | 102 ms                                                             | 103 ms: 1.01x slower                                                     |
| hexiom                           | 4.75 ms                                                            | 4.79 ms: 1.01x slower                                                    |
| json                             | 3.50 ms                                                            | 3.54 ms: 1.01x slower                                                    |
| logging_silent                   | 60.1 ns                                                            | 60.9 ns: 1.01x slower                                                    |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 348 ms: 1.02x slower                                                     |
| logging_simple                   | 5.06 us                                                            | 5.15 us: 1.02x slower                                                    |
| telco                            | 5.37 ms                                                            | 5.48 ms: 1.02x slower                                                    |
| async_tree_eager                 | 88.3 ms                                                            | 90.4 ms: 1.02x slower                                                    |
| unpickle_pure_python             | 161 us                                                             | 165 us: 1.03x slower                                                     |
| xml_etree_process                | 49.9 ms                                                            | 51.2 ms: 1.03x slower                                                    |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.25 ms: 1.03x slower                                                    |
| chaos                            | 43.6 ms                                                            | 45.1 ms: 1.03x slower                                                    |
| logging_format                   | 5.62 us                                                            | 5.81 us: 1.03x slower                                                    |
| pprint_safe_repr                 | 546 ms                                                             | 566 ms: 1.04x slower                                                     |
| sqlglot_v2_parse                 | 979 us                                                             | 1.02 ms: 1.04x slower                                                    |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.33 sec: 1.04x slower                                                   |
| nqueens                          | 58.3 ms                                                            | 60.8 ms: 1.04x slower                                                    |
| pickle_pure_python               | 245 us                                                             | 256 us: 1.05x slower                                                     |
| regex_v8                         | 15.0 ms                                                            | 15.7 ms: 1.05x slower                                                    |
| sympy_integrate                  | 15.4 ms                                                            | 16.3 ms: 1.06x slower                                                    |
| pprint_pformat                   | 1.13 sec                                                           | 1.19 sec: 1.06x slower                                                   |
| pickle_dict                      | 19.0 us                                                            | 20.3 us: 1.07x slower                                                    |
| decimal_factorial                | 177 ms                                                             | 189 ms: 1.07x slower                                                     |
| decimal_pi                       | 228 ms                                                             | 245 ms: 1.07x slower                                                     |
| float                            | 59.2 ms                                                            | 63.9 ms: 1.08x slower                                                    |
| raytrace                         | 197 ms                                                             | 213 ms: 1.08x slower                                                     |
| nbody                            | 75.8 ms                                                            | 82.4 ms: 1.09x slower                                                    |
| sympy_sum                        | 104 ms                                                             | 115 ms: 1.10x slower                                                     |
| unpickle                         | 10.8 us                                                            | 11.9 us: 1.10x slower                                                    |
| sympy_str                        | 193 ms                                                             | 213 ms: 1.10x slower                                                     |
| sympy_expand                     | 331 ms                                                             | 366 ms: 1.10x slower                                                     |
| xdsl_constant_fold               | 36.4 ms                                                            | 40.4 ms: 1.11x slower                                                    |
| meteor_contest                   | 85.7 ms                                                            | 95.5 ms: 1.11x slower                                                    |
| json_loads                       | 18.2 us                                                            | 20.5 us: 1.13x slower                                                    |
| django_template                  | 28.8 ms                                                            | 32.4 ms: 1.13x slower                                                    |
| argparse_subparsers              | 449 us                                                             | 506 us: 1.13x slower                                                     |
| crypto_pyaes                     | 55.6 ms                                                            | 62.9 ms: 1.13x slower                                                    |
| pickle                           | 7.21 us                                                            | 8.16 us: 1.13x slower                                                    |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.8 ms: 1.14x slower                                                    |
| generators                       | 22.2 ms                                                            | 25.3 ms: 1.14x slower                                                    |
| typing_runtime_protocols         | 112 us                                                             | 128 us: 1.14x slower                                                     |
| docutils                         | 1.89 sec                                                           | 2.17 sec: 1.15x slower                                                   |
| networkx_shortest_path           | 454 ms                                                             | 525 ms: 1.16x slower                                                     |
| networkx_connected_components    | 443 ms                                                             | 512 ms: 1.16x slower                                                     |
| mypy2                            | 741 ms                                                             | 859 ms: 1.16x slower                                                     |
| deltablue                        | 2.59 ms                                                            | 3.01 ms: 1.16x slower                                                    |
| scimark_lu                       | 70.2 ms                                                            | 82.0 ms: 1.17x slower                                                    |
| python_startup_no_site           | 6.49 ms                                                            | 7.73 ms: 1.19x slower                                                    |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 3.41 ms: 1.19x slower                                                    |
| python_startup                   | 9.51 ms                                                            | 11.4 ms: 1.20x slower                                                    |
| unpack_sequence                  | 26.4 ns                                                            | 32.4 ns: 1.23x slower                                                    |
| pickle_list                      | 2.66 us                                                            | 3.38 us: 1.27x slower                                                    |
| coverage                         | 55.0 ms                                                            | 73.8 ms: 1.34x slower                                                    |
| mako                             | 8.30 ms                                                            | 11.5 ms: 1.38x slower                                                    |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 461 ms: 1.53x slower                                                     |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 309 ms: 1.77x slower                                                     |
| thread_montecarlo_naive          | 18.1 ms                                                            | 35.5 ms: 1.95x slower                                                    |
| async_tree_eager_tg              | 56.8 ms                                                            | 226 ms: 3.98x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.34x faster                                                             |

Benchmark hidden because not significant (6): unpickle_list, regex_effbot, spectral_norm, networkx_k_core, scimark_fft, async_tree_cpu_io_mixed
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.345x faster

# HPT report

- Reliability score: 99.44% likely to be faster
- 90% likely to have a speedup of 1.01x
- 95% likely to have a speedup of 1.01x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.61x