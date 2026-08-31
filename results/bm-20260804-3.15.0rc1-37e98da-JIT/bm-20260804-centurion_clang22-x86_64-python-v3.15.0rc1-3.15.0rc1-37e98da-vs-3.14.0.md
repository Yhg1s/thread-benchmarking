# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.278x faster
- HPT reliability: 98.05%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.07x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 10.5 ms: 1.03x slower                                                    |
| fastapi_http   | 222 ms                                                             | 208 ms: 1.07x faster                                                     |
| html5lib       | 45.3 ms                                                            | 47.6 ms: 1.05x slower                                                    |
| Geometric mean | (ref)                                                              | 1.00x slower                                                             |

Benchmark hidden because not significant (2): docutils, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 271 ms: 1.19x faster                                                     |
| async_tree_eager                 | 83.0 ms                                                            | 78.1 ms: 1.06x faster                                                    |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 185 ms: 1.01x slower                                                     |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 332 ms: 1.02x slower                                                     |
| asyncio_websockets               | 305 ms                                                             | 311 ms: 1.02x slower                                                     |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 440 ms: 1.03x slower                                                     |
| coroutines                       | 15.1 ms                                                            | 15.8 ms: 1.04x slower                                                    |
| async_tree_eager_tg              | 182 ms                                                             | 192 ms: 1.05x slower                                                     |
| async_tree_none_tg               | 224 ms                                                             | 236 ms: 1.05x slower                                                     |
| async_tree_memoization           | 285 ms                                                             | 300 ms: 1.05x slower                                                     |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 451 ms: 1.05x slower                                                     |
| async_tree_eager_io              | 568 ms                                                             | 606 ms: 1.07x slower                                                     |
| async_generators                 | 231 ms                                                             | 252 ms: 1.09x slower                                                     |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 410 ms: 1.10x slower                                                     |
| async_tree_memoization_tg        | 279 ms                                                             | 313 ms: 1.12x slower                                                     |
| async_tree_eager_io_tg           | 565 ms                                                             | 635 ms: 1.12x slower                                                     |
| async_tree_io                    | 549 ms                                                             | 621 ms: 1.13x slower                                                     |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 270 ms: 1.14x slower                                                     |
| async_tree_io_tg                 | 545 ms                                                             | 636 ms: 1.17x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.05x slower                                                             |

Benchmark hidden because not significant (1): async_tree_none

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 17.5 ns: 1.10x faster                                                    |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| decimal_pi        | 209 ms                                                             | 205 ms: 1.02x faster                                                     |
| decimal_factorial | 174 ms                                                             | 175 ms: 1.01x slower                                                     |
| Geometric mean    | (ref)                                                              | 1.01x faster                                                             |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| nbody          | 74.2 ms                                                            | 43.8 ms: 1.69x faster                                                    |
| float          | 51.2 ms                                                            | 40.0 ms: 1.28x faster                                                    |
| quadtree_nbody | 654 ms                                                             | 552 ms: 1.18x faster                                                     |
| Geometric mean | (ref)                                                              | 1.27x faster                                                             |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| regex_compile  | 97.0 ms                                                            | 88.1 ms: 1.10x faster                                                    |
| regex_dna      | 147 ms                                                             | 152 ms: 1.03x slower                                                     |
| regex_v8       | 15.0 ms                                                            | 15.5 ms: 1.04x slower                                                    |
| regex_effbot   | 1.98 ms                                                            | 2.28 ms: 1.15x slower                                                    |
| Geometric mean | (ref)                                                              | 1.03x slower                                                             |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large         | 289 ms                                                             | 1.90 ms: 152.41x faster                                                  |
| ascii85_large        | 681 ms                                                             | 13.8 ms: 49.45x faster                                                   |
| base85_large         | 249 ms                                                             | 5.13 ms: 48.60x faster                                                   |
| base32_small         | 5.71 ms                                                            | 159 us: 35.84x faster                                                    |
| ascii85_small        | 13.0 ms                                                            | 490 us: 26.59x faster                                                    |
| base85_small         | 4.66 ms                                                            | 183 us: 25.42x faster                                                    |
| base64_large         | 5.70 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| urlsafe_base64_small | 340 us                                                             | 210 us: 1.62x faster                                                     |
| base64_small         | 227 us                                                             | 172 us: 1.32x faster                                                     |
| json_dumps           | 7.52 ms                                                            | 6.01 ms: 1.25x faster                                                    |
| unpickle_pure_python | 163 us                                                             | 131 us: 1.25x faster                                                     |
| xml_etree_process    | 50.0 ms                                                            | 42.6 ms: 1.17x faster                                                    |
| pickle_pure_python   | 251 us                                                             | 217 us: 1.16x faster                                                     |
| xml_etree_generate   | 68.1 ms                                                            | 61.9 ms: 1.10x faster                                                    |
| tomli_loads          | 1.49 sec                                                           | 1.37 sec: 1.09x faster                                                   |
| xml_etree_iterparse  | 85.5 ms                                                            | 80.9 ms: 1.06x faster                                                    |
| json_loads           | 18.6 us                                                            | 17.9 us: 1.04x faster                                                    |
| pickle_dict          | 20.0 us                                                            | 19.8 us: 1.01x faster                                                    |
| unpickle             | 10.5 us                                                            | 10.6 us: 1.01x slower                                                    |
| pickle               | 8.04 us                                                            | 8.19 us: 1.02x slower                                                    |
| xml_etree_parse      | 118 ms                                                             | 122 ms: 1.04x slower                                                     |
| pickle_list          | 3.03 us                                                            | 3.31 us: 1.09x slower                                                    |
| base16_small         | 265 us                                                             | 354 us: 1.34x slower                                                     |
| base16_large         | 6.35 ms                                                            | 10.1 ms: 1.59x slower                                                    |
| Geometric mean       | (ref)                                                              | 2.73x faster                                                             |

Benchmark hidden because not significant (1): unpickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| python_startup_no_site | 6.52 ms                                                            | 6.12 ms: 1.06x faster                                                    |
| python_startup         | 9.93 ms                                                            | 9.76 ms: 1.02x faster                                                    |
| Geometric mean         | (ref)                                                              | 1.04x faster                                                             |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| mako            | 8.69 ms                                                            | 7.28 ms: 1.19x faster                                                    |
| django_template | 30.5 ms                                                            | 34.8 ms: 1.14x slower                                                    |
| Geometric mean  | (ref)                                                              | 1.02x faster                                                             |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 8.30 ms: 1.49x faster                                                    |
| thread_mandelbrot_naive     | 207 ms                                                             | 186 ms: 1.11x faster                                                     |
| thread_pipeline_naive       | 34.9 ms                                                            | 31.6 ms: 1.11x faster                                                    |
| thread_mandelbrot_optimized | 205 ms                                                             | 190 ms: 1.08x faster                                                     |
| thread_counter_naive        | 21.2 ms                                                            | 20.5 ms: 1.03x faster                                                    |
| thread_memo_optimized       | 17.5 ms                                                            | 17.0 ms: 1.03x faster                                                    |
| thread_pipeline_optimized   | 25.8 ms                                                            | 25.6 ms: 1.01x faster                                                    |
| thread_accumulate_naive     | 40.4 ms                                                            | 40.2 ms: 1.00x faster                                                    |
| thread_accumulate_optimized | 39.5 ms                                                            | 40.0 ms: 1.01x slower                                                    |
| thread_counter_optimized    | 18.3 ms                                                            | 18.7 ms: 1.02x slower                                                    |
| thread_montecarlo_naive     | 14.3 ms                                                            | 15.3 ms: 1.07x slower                                                    |
| thread_montecarlo_optimized | 12.9 ms                                                            | 14.2 ms: 1.10x slower                                                    |
| Geometric mean              | (ref)                                                              | 1.05x faster                                                             |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large                     | 289 ms                                                             | 1.90 ms: 152.41x faster                                                  |
| ascii85_large                    | 681 ms                                                             | 13.8 ms: 49.45x faster                                                   |
| base85_large                     | 249 ms                                                             | 5.13 ms: 48.60x faster                                                   |
| base32_small                     | 5.71 ms                                                            | 159 us: 35.84x faster                                                    |
| ascii85_small                    | 13.0 ms                                                            | 490 us: 26.59x faster                                                    |
| base85_small                     | 4.66 ms                                                            | 183 us: 25.42x faster                                                    |
| argparse_many_optionals          | 34.5 ms                                                            | 8.08 ms: 4.27x faster                                                    |
| base64_large                     | 5.70 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| richards_super                   | 40.3 ms                                                            | 18.8 ms: 2.15x faster                                                    |
| pylint                           | 222 ms                                                             | 105 ms: 2.12x faster                                                     |
| richards                         | 34.7 ms                                                            | 16.5 ms: 2.11x faster                                                    |
| nbody                            | 74.2 ms                                                            | 43.8 ms: 1.69x faster                                                    |
| urlsafe_base64_small             | 340 us                                                             | 210 us: 1.62x faster                                                     |
| scimark_sor                      | 78.2 ms                                                            | 50.8 ms: 1.54x faster                                                    |
| scimark_lu                       | 74.7 ms                                                            | 49.0 ms: 1.53x faster                                                    |
| thread_memo_naive                | 12.4 ms                                                            | 8.30 ms: 1.49x faster                                                    |
| argparse_subparsers              | 687 us                                                             | 468 us: 1.47x faster                                                     |
| spectral_norm                    | 64.1 ms                                                            | 47.7 ms: 1.34x faster                                                    |
| deltablue                        | 2.76 ms                                                            | 2.05 ms: 1.34x faster                                                    |
| base64_small                     | 227 us                                                             | 172 us: 1.32x faster                                                     |
| float                            | 51.2 ms                                                            | 40.0 ms: 1.28x faster                                                    |
| pathlib                          | 12.7 ms                                                            | 10.0 ms: 1.26x faster                                                    |
| json_dumps                       | 7.52 ms                                                            | 6.01 ms: 1.25x faster                                                    |
| scimark_fft                      | 211 ms                                                             | 169 ms: 1.25x faster                                                     |
| unpickle_pure_python             | 163 us                                                             | 131 us: 1.25x faster                                                     |
| deepcopy_memo                    | 19.1 us                                                            | 15.4 us: 1.24x faster                                                    |
| nqueens                          | 59.8 ms                                                            | 49.1 ms: 1.22x faster                                                    |
| fannkuch                         | 246 ms                                                             | 206 ms: 1.20x faster                                                     |
| logging_format                   | 6.00 us                                                            | 5.02 us: 1.20x faster                                                    |
| mako                             | 8.69 ms                                                            | 7.28 ms: 1.19x faster                                                    |
| asyncio_tcp                      | 324 ms                                                             | 271 ms: 1.19x faster                                                     |
| quadtree_nbody                   | 654 ms                                                             | 552 ms: 1.18x faster                                                     |
| xml_etree_process                | 50.0 ms                                                            | 42.6 ms: 1.17x faster                                                    |
| create_gc_cycles                 | 2.02 ms                                                            | 1.72 ms: 1.17x faster                                                    |
| pyflate                          | 309 ms                                                             | 264 ms: 1.17x faster                                                     |
| comprehensions                   | 11.4 us                                                            | 9.75 us: 1.17x faster                                                    |
| pickle_pure_python               | 251 us                                                             | 217 us: 1.16x faster                                                     |
| telco                            | 5.39 ms                                                            | 4.70 ms: 1.15x faster                                                    |
| scimark_monte_carlo              | 42.3 ms                                                            | 37.2 ms: 1.14x faster                                                    |
| logging_simple                   | 5.02 us                                                            | 4.42 us: 1.14x faster                                                    |
| sqlglot_v2_parse                 | 954 us                                                             | 844 us: 1.13x faster                                                     |
| crypto_pyaes                     | 56.7 ms                                                            | 50.4 ms: 1.12x faster                                                    |
| thread_mandelbrot_naive          | 207 ms                                                             | 186 ms: 1.11x faster                                                     |
| thread_pipeline_naive            | 34.9 ms                                                            | 31.6 ms: 1.11x faster                                                    |
| go                               | 91.1 ms                                                            | 82.5 ms: 1.10x faster                                                    |
| xml_etree_generate               | 68.1 ms                                                            | 61.9 ms: 1.10x faster                                                    |
| regex_compile                    | 97.0 ms                                                            | 88.1 ms: 1.10x faster                                                    |
| noop                             | 19.2 ns                                                            | 17.5 ns: 1.10x faster                                                    |
| gc_traversal                     | 3.36 ms                                                            | 3.07 ms: 1.10x faster                                                    |
| sympy_expand                     | 344 ms                                                             | 314 ms: 1.09x faster                                                     |
| tomli_loads                      | 1.49 sec                                                           | 1.37 sec: 1.09x faster                                                   |
| thread_mandelbrot_optimized      | 205 ms                                                             | 190 ms: 1.08x faster                                                     |
| raytrace                         | 201 ms                                                             | 188 ms: 1.07x faster                                                     |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 79.3 ms: 1.07x faster                                                    |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 39.1 ms: 1.07x faster                                                    |
| fastapi_http                     | 222 ms                                                             | 208 ms: 1.07x faster                                                     |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.13 ms: 1.07x faster                                                    |
| python_startup_no_site           | 6.52 ms                                                            | 6.12 ms: 1.06x faster                                                    |
| async_tree_eager                 | 83.0 ms                                                            | 78.1 ms: 1.06x faster                                                    |
| hexiom                           | 4.50 ms                                                            | 4.25 ms: 1.06x faster                                                    |
| xml_etree_iterparse              | 85.5 ms                                                            | 80.9 ms: 1.06x faster                                                    |
| typing_runtime_protocols         | 115 us                                                             | 110 us: 1.05x faster                                                     |
| meteor_contest                   | 85.4 ms                                                            | 81.5 ms: 1.05x faster                                                    |
| json                             | 3.46 ms                                                            | 3.32 ms: 1.04x faster                                                    |
| json_loads                       | 18.6 us                                                            | 17.9 us: 1.04x faster                                                    |
| chaos                            | 42.9 ms                                                            | 41.3 ms: 1.04x faster                                                    |
| sqlalchemy_imperative            | 14.8 ms                                                            | 14.3 ms: 1.03x faster                                                    |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.01 sec: 1.03x faster                                                   |
| thread_counter_naive             | 21.2 ms                                                            | 20.5 ms: 1.03x faster                                                    |
| thread_memo_optimized            | 17.5 ms                                                            | 17.0 ms: 1.03x faster                                                    |
| thrift                           | 2.00 ms                                                            | 1.96 ms: 1.02x faster                                                    |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                   |
| decimal_pi                       | 209 ms                                                             | 205 ms: 1.02x faster                                                     |
| python_startup                   | 9.93 ms                                                            | 9.76 ms: 1.02x faster                                                    |
| pickle_dict                      | 20.0 us                                                            | 19.8 us: 1.01x faster                                                    |
| sympy_str                        | 200 ms                                                             | 198 ms: 1.01x faster                                                     |
| thread_pipeline_optimized        | 25.8 ms                                                            | 25.6 ms: 1.01x faster                                                    |
| thread_accumulate_naive          | 40.4 ms                                                            | 40.2 ms: 1.00x faster                                                    |
| decimal_factorial                | 174 ms                                                             | 175 ms: 1.01x slower                                                     |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.91 ms: 1.01x slower                                                    |
| unpickle                         | 10.5 us                                                            | 10.6 us: 1.01x slower                                                    |
| thread_accumulate_optimized      | 39.5 ms                                                            | 40.0 ms: 1.01x slower                                                    |
| async_tree_eager_memoization     | 183 ms                                                             | 185 ms: 1.01x slower                                                     |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 332 ms: 1.02x slower                                                     |
| networkx_shortest_path           | 447 ms                                                             | 454 ms: 1.02x slower                                                     |
| pickle                           | 8.04 us                                                            | 8.19 us: 1.02x slower                                                    |
| thread_counter_optimized         | 18.3 ms                                                            | 18.7 ms: 1.02x slower                                                    |
| asyncio_websockets               | 305 ms                                                             | 311 ms: 1.02x slower                                                     |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 440 ms: 1.03x slower                                                     |
| chameleon                        | 10.3 ms                                                            | 10.5 ms: 1.03x slower                                                    |
| sympy_sum                        | 109 ms                                                             | 112 ms: 1.03x slower                                                     |
| networkx_connected_components    | 425 ms                                                             | 439 ms: 1.03x slower                                                     |
| pprint_pformat                   | 1.10 sec                                                           | 1.13 sec: 1.03x slower                                                   |
| regex_dna                        | 147 ms                                                             | 152 ms: 1.03x slower                                                     |
| regex_v8                         | 15.0 ms                                                            | 15.5 ms: 1.04x slower                                                    |
| pprint_safe_repr                 | 534 ms                                                             | 555 ms: 1.04x slower                                                     |
| xml_etree_parse                  | 118 ms                                                             | 122 ms: 1.04x slower                                                     |
| deepcopy                         | 198 us                                                             | 206 us: 1.04x slower                                                     |
| coroutines                       | 15.1 ms                                                            | 15.8 ms: 1.04x slower                                                    |
| html5lib                         | 45.3 ms                                                            | 47.6 ms: 1.05x slower                                                    |
| mdp                              | 971 ms                                                             | 1.02 sec: 1.05x slower                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 192 ms: 1.05x slower                                                     |
| async_tree_none_tg               | 224 ms                                                             | 236 ms: 1.05x slower                                                     |
| async_tree_memoization           | 285 ms                                                             | 300 ms: 1.05x slower                                                     |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 451 ms: 1.05x slower                                                     |
| logging_silent                   | 59.2 ns                                                            | 62.5 ns: 1.05x slower                                                    |
| sympy_integrate                  | 15.1 ms                                                            | 16.1 ms: 1.06x slower                                                    |
| async_tree_eager_io              | 568 ms                                                             | 606 ms: 1.07x slower                                                     |
| thread_montecarlo_naive          | 14.3 ms                                                            | 15.3 ms: 1.07x slower                                                    |
| generators                       | 24.2 ms                                                            | 26.0 ms: 1.08x slower                                                    |
| pycparser                        | 878 ms                                                             | 953 ms: 1.09x slower                                                     |
| async_generators                 | 231 ms                                                             | 252 ms: 1.09x slower                                                     |
| pickle_list                      | 3.03 us                                                            | 3.31 us: 1.09x slower                                                    |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 410 ms: 1.10x slower                                                     |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 14.2 ms: 1.10x slower                                                    |
| async_tree_memoization_tg        | 279 ms                                                             | 313 ms: 1.12x slower                                                     |
| async_tree_eager_io_tg           | 565 ms                                                             | 635 ms: 1.12x slower                                                     |
| networkx_k_core                  | 2.05 sec                                                           | 2.31 sec: 1.12x slower                                                   |
| async_tree_io                    | 549 ms                                                             | 621 ms: 1.13x slower                                                     |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 270 ms: 1.14x slower                                                     |
| django_template                  | 30.5 ms                                                            | 34.8 ms: 1.14x slower                                                    |
| coverage                         | 54.5 ms                                                            | 62.5 ms: 1.15x slower                                                    |
| regex_effbot                     | 1.98 ms                                                            | 2.28 ms: 1.15x slower                                                    |
| async_tree_io_tg                 | 545 ms                                                             | 636 ms: 1.17x slower                                                     |
| deepcopy_reduce                  | 2.02 us                                                            | 2.42 us: 1.20x slower                                                    |
| base16_small                     | 265 us                                                             | 354 us: 1.34x slower                                                     |
| mypy2                            | 780 ms                                                             | 1.16 sec: 1.48x slower                                                   |
| base16_large                     | 6.35 ms                                                            | 10.1 ms: 1.59x slower                                                    |
| unpack_sequence                  | 35.6 ns                                                            | 78.7 ns: 2.21x slower                                                    |
| Geometric mean                   | (ref)                                                              | 1.27x faster                                                             |

Benchmark hidden because not significant (6): xdsl_constant_fold, unpickle_list, docutils, pidigits, async_tree_none, tornado_http
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.278x faster

# HPT report

- Reliability score: 98.05% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.07x