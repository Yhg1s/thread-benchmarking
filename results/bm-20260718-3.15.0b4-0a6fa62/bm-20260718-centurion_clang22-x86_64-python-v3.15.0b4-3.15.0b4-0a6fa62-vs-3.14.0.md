# Results vs. 3.14.0

- fork: python
- ref: v3.15.0b4
- machine: linux-x86_64
- commit hash: 0a6fa62
- commit date: 2026-07-18
- overall geometric mean: 1.170x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x slower
- Memory change: 0.96x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 10.9 ms: 1.06x slower                                                  |
| docutils       | 1.98 sec                                                           | 1.91 sec: 1.04x faster                                                 |
| fastapi_http   | 222 ms                                                             | 227 ms: 1.02x slower                                                   |
| html5lib       | 45.3 ms                                                            | 49.3 ms: 1.09x slower                                                  |
| tornado_http   | 101 ms                                                             | 100 ms: 1.01x faster                                                   |
| Geometric mean | (ref)                                                              | 1.02x slower                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 273 ms: 1.19x faster                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| async_tree_eager                 | 83.0 ms                                                            | 83.5 ms: 1.01x slower                                                  |
| async_generators                 | 231 ms                                                             | 234 ms: 1.01x slower                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 188 ms: 1.03x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 339 ms: 1.04x slower                                                   |
| asyncio_websockets               | 305 ms                                                             | 321 ms: 1.05x slower                                                   |
| coroutines                       | 15.1 ms                                                            | 16.4 ms: 1.09x slower                                                  |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 474 ms: 1.11x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 425 ms: 1.14x slower                                                   |
| async_tree_none                  | 233 ms                                                             | 264 ms: 1.14x slower                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 491 ms: 1.15x slower                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 212 ms: 1.17x slower                                                   |
| async_tree_eager_io              | 568 ms                                                             | 663 ms: 1.17x slower                                                   |
| async_tree_none_tg               | 224 ms                                                             | 270 ms: 1.20x slower                                                   |
| async_tree_memoization           | 285 ms                                                             | 346 ms: 1.21x slower                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 340 ms: 1.22x slower                                                   |
| async_tree_io                    | 549 ms                                                             | 672 ms: 1.22x slower                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 290 ms: 1.23x slower                                                   |
| async_tree_eager_io_tg           | 565 ms                                                             | 699 ms: 1.24x slower                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 705 ms: 1.29x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.11x slower                                                           |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 19.8 ns: 1.03x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 179 ms: 1.03x slower                                                   |
| decimal_pi        | 209 ms                                                             | 216 ms: 1.03x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.03x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| quadtree_nbody | 654 ms                                                             | 666 ms: 1.02x slower                                                   |
| float          | 51.2 ms                                                            | 59.8 ms: 1.17x slower                                                  |
| Geometric mean | (ref)                                                              | 1.05x slower                                                           |

Benchmark hidden because not significant (1): nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_dna      | 147 ms                                                             | 153 ms: 1.03x slower                                                   |
| regex_compile  | 97.0 ms                                                            | 103 ms: 1.06x slower                                                   |
| regex_v8       | 15.0 ms                                                            | 16.1 ms: 1.08x slower                                                  |
| regex_effbot   | 1.98 ms                                                            | 2.27 ms: 1.15x slower                                                  |
| Geometric mean | (ref)                                                              | 1.08x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 289 ms                                                             | 1.90 ms: 152.40x faster                                                |
| ascii85_large        | 681 ms                                                             | 13.8 ms: 49.39x faster                                                 |
| base85_large         | 249 ms                                                             | 5.11 ms: 48.83x faster                                                 |
| base32_small         | 5.71 ms                                                            | 213 us: 26.85x faster                                                  |
| ascii85_small        | 13.0 ms                                                            | 530 us: 24.63x faster                                                  |
| base85_small         | 4.66 ms                                                            | 207 us: 22.57x faster                                                  |
| base64_large         | 5.70 ms                                                            | 1.59 ms: 3.60x faster                                                  |
| urlsafe_base64_small | 340 us                                                             | 246 us: 1.38x faster                                                   |
| json_dumps           | 7.52 ms                                                            | 6.57 ms: 1.14x faster                                                  |
| unpickle_list        | 3.03 us                                                            | 2.95 us: 1.03x faster                                                  |
| json_loads           | 18.6 us                                                            | 18.1 us: 1.03x faster                                                  |
| pickle_dict          | 20.0 us                                                            | 19.5 us: 1.02x faster                                                  |
| xml_etree_iterparse  | 85.5 ms                                                            | 83.7 ms: 1.02x faster                                                  |
| xml_etree_process    | 50.0 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| tomli_loads          | 1.49 sec                                                           | 1.52 sec: 1.02x slower                                                 |
| xml_etree_generate   | 68.1 ms                                                            | 69.9 ms: 1.03x slower                                                  |
| pickle               | 8.04 us                                                            | 8.26 us: 1.03x slower                                                  |
| base64_small         | 227 us                                                             | 237 us: 1.04x slower                                                   |
| xml_etree_parse      | 118 ms                                                             | 124 ms: 1.06x slower                                                   |
| pickle_pure_python   | 251 us                                                             | 267 us: 1.06x slower                                                   |
| pickle_list          | 3.03 us                                                            | 3.22 us: 1.06x slower                                                  |
| unpickle_pure_python | 163 us                                                             | 174 us: 1.07x slower                                                   |
| base16_large         | 6.35 ms                                                            | 7.41 ms: 1.17x slower                                                  |
| base16_small         | 265 us                                                             | 374 us: 1.41x slower                                                   |
| Geometric mean       | (ref)                                                              | 2.55x faster                                                           |

Benchmark hidden because not significant (1): unpickle

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.52 ms                                                            | 6.01 ms: 1.08x faster                                                  |
| python_startup         | 9.93 ms                                                            | 9.67 ms: 1.03x faster                                                  |
| Geometric mean         | (ref)                                                              | 1.05x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 31.2 ms: 1.02x slower                                                  |
| mako            | 8.69 ms                                                            | 9.51 ms: 1.09x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 10.7 ms: 1.16x faster                                                  |
| thread_mandelbrot_naive     | 207 ms                                                             | 208 ms: 1.01x slower                                                   |
| thread_mandelbrot_optimized | 205 ms                                                             | 208 ms: 1.01x slower                                                   |
| thread_montecarlo_optimized | 12.9 ms                                                            | 13.3 ms: 1.03x slower                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 14.7 ms: 1.03x slower                                                  |
| thread_pipeline_naive       | 34.9 ms                                                            | 36.4 ms: 1.04x slower                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 18.4 ms: 1.05x slower                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 27.5 ms: 1.07x slower                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 43.2 ms: 1.07x slower                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 42.4 ms: 1.07x slower                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 24.3 ms: 1.15x slower                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 21.6 ms: 1.18x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.05x slower                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 289 ms                                                             | 1.90 ms: 152.40x faster                                                |
| ascii85_large                    | 681 ms                                                             | 13.8 ms: 49.39x faster                                                 |
| base85_large                     | 249 ms                                                             | 5.11 ms: 48.83x faster                                                 |
| base32_small                     | 5.71 ms                                                            | 213 us: 26.85x faster                                                  |
| ascii85_small                    | 13.0 ms                                                            | 530 us: 24.63x faster                                                  |
| base85_small                     | 4.66 ms                                                            | 207 us: 22.57x faster                                                  |
| argparse_many_optionals          | 34.5 ms                                                            | 8.43 ms: 4.09x faster                                                  |
| base64_large                     | 5.70 ms                                                            | 1.59 ms: 3.60x faster                                                  |
| pylint                           | 222 ms                                                             | 103 ms: 2.15x faster                                                   |
| argparse_subparsers              | 687 us                                                             | 476 us: 1.44x faster                                                   |
| urlsafe_base64_small             | 340 us                                                             | 246 us: 1.38x faster                                                   |
| create_gc_cycles                 | 2.02 ms                                                            | 1.68 ms: 1.20x faster                                                  |
| asyncio_tcp                      | 324 ms                                                             | 273 ms: 1.19x faster                                                   |
| thread_memo_naive                | 12.4 ms                                                            | 10.7 ms: 1.16x faster                                                  |
| pathlib                          | 12.7 ms                                                            | 11.0 ms: 1.16x faster                                                  |
| json_dumps                       | 7.52 ms                                                            | 6.57 ms: 1.14x faster                                                  |
| gc_traversal                     | 3.36 ms                                                            | 3.07 ms: 1.09x faster                                                  |
| python_startup_no_site           | 6.52 ms                                                            | 6.01 ms: 1.08x faster                                                  |
| deepcopy                         | 198 us                                                             | 190 us: 1.04x faster                                                   |
| docutils                         | 1.98 sec                                                           | 1.91 sec: 1.04x faster                                                 |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.17 ms: 1.03x faster                                                  |
| mypy2                            | 780 ms                                                             | 756 ms: 1.03x faster                                                   |
| unpickle_list                    | 3.03 us                                                            | 2.95 us: 1.03x faster                                                  |
| json_loads                       | 18.6 us                                                            | 18.1 us: 1.03x faster                                                  |
| python_startup                   | 9.93 ms                                                            | 9.67 ms: 1.03x faster                                                  |
| logging_format                   | 6.00 us                                                            | 5.86 us: 1.02x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| pickle_dict                      | 20.0 us                                                            | 19.5 us: 1.02x faster                                                  |
| xml_etree_iterparse              | 85.5 ms                                                            | 83.7 ms: 1.02x faster                                                  |
| telco                            | 5.39 ms                                                            | 5.30 ms: 1.02x faster                                                  |
| raytrace                         | 201 ms                                                             | 198 ms: 1.01x faster                                                   |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 84.1 ms: 1.01x faster                                                  |
| sqlglot_v2_parse                 | 954 us                                                             | 945 us: 1.01x faster                                                   |
| tornado_http                     | 101 ms                                                             | 100 ms: 1.01x faster                                                   |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 83.5 ms: 1.01x slower                                                  |
| thread_mandelbrot_naive          | 207 ms                                                             | 208 ms: 1.01x slower                                                   |
| xml_etree_process                | 50.0 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 42.2 ms: 1.01x slower                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 208 ms: 1.01x slower                                                   |
| typing_runtime_protocols         | 115 us                                                             | 117 us: 1.01x slower                                                   |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.0 ms: 1.01x slower                                                  |
| async_generators                 | 231 ms                                                             | 234 ms: 1.01x slower                                                   |
| logging_simple                   | 5.02 us                                                            | 5.10 us: 1.02x slower                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.52 sec: 1.02x slower                                                 |
| quadtree_nbody                   | 654 ms                                                             | 666 ms: 1.02x slower                                                   |
| nqueens                          | 59.8 ms                                                            | 61.1 ms: 1.02x slower                                                  |
| django_template                  | 30.5 ms                                                            | 31.2 ms: 1.02x slower                                                  |
| fastapi_http                     | 222 ms                                                             | 227 ms: 1.02x slower                                                   |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.96 ms: 1.03x slower                                                  |
| mdp                              | 971 ms                                                             | 996 ms: 1.03x slower                                                   |
| xml_etree_generate               | 68.1 ms                                                            | 69.9 ms: 1.03x slower                                                  |
| async_tree_eager_memoization     | 183 ms                                                             | 188 ms: 1.03x slower                                                   |
| scimark_fft                      | 211 ms                                                             | 217 ms: 1.03x slower                                                   |
| sympy_integrate                  | 15.1 ms                                                            | 15.5 ms: 1.03x slower                                                  |
| pickle                           | 8.04 us                                                            | 8.26 us: 1.03x slower                                                  |
| deltablue                        | 2.76 ms                                                            | 2.83 ms: 1.03x slower                                                  |
| decimal_factorial                | 174 ms                                                             | 179 ms: 1.03x slower                                                   |
| meteor_contest                   | 85.4 ms                                                            | 87.8 ms: 1.03x slower                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 13.3 ms: 1.03x slower                                                  |
| thread_montecarlo_naive          | 14.3 ms                                                            | 14.7 ms: 1.03x slower                                                  |
| noop                             | 19.2 ns                                                            | 19.8 ns: 1.03x slower                                                  |
| decimal_pi                       | 209 ms                                                             | 216 ms: 1.03x slower                                                   |
| thrift                           | 2.00 ms                                                            | 2.07 ms: 1.03x slower                                                  |
| networkx_connected_components    | 425 ms                                                             | 439 ms: 1.03x slower                                                   |
| sympy_sum                        | 109 ms                                                             | 112 ms: 1.03x slower                                                   |
| regex_dna                        | 147 ms                                                             | 153 ms: 1.03x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 339 ms: 1.04x slower                                                   |
| sympy_str                        | 200 ms                                                             | 208 ms: 1.04x slower                                                   |
| richards                         | 34.7 ms                                                            | 36.1 ms: 1.04x slower                                                  |
| crypto_pyaes                     | 56.7 ms                                                            | 58.9 ms: 1.04x slower                                                  |
| spectral_norm                    | 64.1 ms                                                            | 66.8 ms: 1.04x slower                                                  |
| richards_super                   | 40.3 ms                                                            | 42.1 ms: 1.04x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 358 ms: 1.04x slower                                                   |
| generators                       | 24.2 ms                                                            | 25.2 ms: 1.04x slower                                                  |
| scimark_lu                       | 74.7 ms                                                            | 78.0 ms: 1.04x slower                                                  |
| thread_pipeline_naive            | 34.9 ms                                                            | 36.4 ms: 1.04x slower                                                  |
| base64_small                     | 227 us                                                             | 237 us: 1.04x slower                                                   |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.26 sec: 1.05x slower                                                 |
| thread_memo_optimized            | 17.5 ms                                                            | 18.4 ms: 1.05x slower                                                  |
| asyncio_websockets               | 305 ms                                                             | 321 ms: 1.05x slower                                                   |
| xml_etree_parse                  | 118 ms                                                             | 124 ms: 1.06x slower                                                   |
| pyflate                          | 309 ms                                                             | 326 ms: 1.06x slower                                                   |
| chameleon                        | 10.3 ms                                                            | 10.9 ms: 1.06x slower                                                  |
| go                               | 91.1 ms                                                            | 96.3 ms: 1.06x slower                                                  |
| networkx_k_core                  | 2.05 sec                                                           | 2.17 sec: 1.06x slower                                                 |
| regex_compile                    | 97.0 ms                                                            | 103 ms: 1.06x slower                                                   |
| pickle_pure_python               | 251 us                                                             | 267 us: 1.06x slower                                                   |
| pickle_list                      | 3.03 us                                                            | 3.22 us: 1.06x slower                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 27.5 ms: 1.07x slower                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 43.2 ms: 1.07x slower                                                  |
| unpickle_pure_python             | 163 us                                                             | 174 us: 1.07x slower                                                   |
| thread_accumulate_optimized      | 39.5 ms                                                            | 42.4 ms: 1.07x slower                                                  |
| regex_v8                         | 15.0 ms                                                            | 16.1 ms: 1.08x slower                                                  |
| fannkuch                         | 246 ms                                                             | 265 ms: 1.08x slower                                                   |
| pprint_pformat                   | 1.10 sec                                                           | 1.18 sec: 1.08x slower                                                 |
| coroutines                       | 15.1 ms                                                            | 16.4 ms: 1.09x slower                                                  |
| html5lib                         | 45.3 ms                                                            | 49.3 ms: 1.09x slower                                                  |
| xdsl_constant_fold               | 36.0 ms                                                            | 39.2 ms: 1.09x slower                                                  |
| mako                             | 8.69 ms                                                            | 9.51 ms: 1.09x slower                                                  |
| pprint_safe_repr                 | 534 ms                                                             | 586 ms: 1.10x slower                                                   |
| comprehensions                   | 11.4 us                                                            | 12.5 us: 1.10x slower                                                  |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 474 ms: 1.11x slower                                                   |
| pycparser                        | 878 ms                                                             | 976 ms: 1.11x slower                                                   |
| coverage                         | 54.5 ms                                                            | 60.7 ms: 1.11x slower                                                  |
| hexiom                           | 4.50 ms                                                            | 5.02 ms: 1.12x slower                                                  |
| scimark_monte_carlo              | 42.3 ms                                                            | 47.6 ms: 1.12x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 425 ms: 1.14x slower                                                   |
| async_tree_none                  | 233 ms                                                             | 264 ms: 1.14x slower                                                   |
| regex_effbot                     | 1.98 ms                                                            | 2.27 ms: 1.15x slower                                                  |
| thread_counter_naive             | 21.2 ms                                                            | 24.3 ms: 1.15x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 491 ms: 1.15x slower                                                   |
| scimark_sor                      | 78.2 ms                                                            | 91.0 ms: 1.16x slower                                                  |
| async_tree_eager_tg              | 182 ms                                                             | 212 ms: 1.17x slower                                                   |
| base16_large                     | 6.35 ms                                                            | 7.41 ms: 1.17x slower                                                  |
| async_tree_eager_io              | 568 ms                                                             | 663 ms: 1.17x slower                                                   |
| float                            | 51.2 ms                                                            | 59.8 ms: 1.17x slower                                                  |
| thread_counter_optimized         | 18.3 ms                                                            | 21.6 ms: 1.18x slower                                                  |
| logging_silent                   | 59.2 ns                                                            | 70.1 ns: 1.18x slower                                                  |
| async_tree_none_tg               | 224 ms                                                             | 270 ms: 1.20x slower                                                   |
| async_tree_memoization           | 285 ms                                                             | 346 ms: 1.21x slower                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 340 ms: 1.22x slower                                                   |
| async_tree_io                    | 549 ms                                                             | 672 ms: 1.22x slower                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 290 ms: 1.23x slower                                                   |
| async_tree_eager_io_tg           | 565 ms                                                             | 699 ms: 1.24x slower                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 705 ms: 1.29x slower                                                   |
| base16_small                     | 265 us                                                             | 374 us: 1.41x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.17x faster                                                           |

Benchmark hidden because not significant (8): json, nbody, unpickle, networkx_shortest_path, deepcopy_reduce, chaos, deepcopy_memo, unpack_sequence
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.170x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.02x

# Memory
- memory change: 0.96x