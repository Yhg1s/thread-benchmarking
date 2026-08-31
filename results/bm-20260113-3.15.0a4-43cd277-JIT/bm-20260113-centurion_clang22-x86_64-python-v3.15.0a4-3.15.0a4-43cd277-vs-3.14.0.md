# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.077x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.03x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 10.6 ms: 1.03x slower                                                  |
| docutils       | 1.98 sec                                                           | 2.09 sec: 1.06x slower                                                 |
| fastapi_http   | 222 ms                                                             | 212 ms: 1.04x faster                                                   |
| html5lib       | 45.3 ms                                                            | 44.6 ms: 1.02x faster                                                  |
| tornado_http   | 101 ms                                                             | 102 ms: 1.01x slower                                                   |
| Geometric mean | (ref)                                                              | 1.01x slower                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io              | 568 ms                                                             | 488 ms: 1.16x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 280 ms: 1.16x faster                                                   |
| async_tree_eager_io_tg           | 565 ms                                                             | 496 ms: 1.14x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 498 ms: 1.10x faster                                                   |
| async_tree_none                  | 233 ms                                                             | 212 ms: 1.10x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 496 ms: 1.10x faster                                                   |
| async_tree_memoization           | 285 ms                                                             | 260 ms: 1.09x faster                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 259 ms: 1.08x faster                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 399 ms: 1.07x faster                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 172 ms: 1.06x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 405 ms: 1.06x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 213 ms: 1.05x faster                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 175 ms: 1.04x faster                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 79.9 ms: 1.04x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 324 ms: 1.01x faster                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 382 ms: 1.02x slower                                                   |
| coroutines                       | 15.1 ms                                                            | 15.5 ms: 1.03x slower                                                  |
| asyncio_websockets               | 305 ms                                                             | 315 ms: 1.03x slower                                                   |
| async_generators                 | 231 ms                                                             | 239 ms: 1.03x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.05x faster                                                           |

Benchmark hidden because not significant (1): async_tree_eager_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 16.8 ns: 1.14x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 209 ms                                                             | 203 ms: 1.03x faster                                                   |
| decimal_factorial | 174 ms                                                             | 173 ms: 1.01x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.02x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| nbody          | 74.2 ms                                                            | 49.3 ms: 1.51x faster                                                  |
| float          | 51.2 ms                                                            | 38.5 ms: 1.33x faster                                                  |
| quadtree_nbody | 654 ms                                                             | 549 ms: 1.19x faster                                                   |
| pidigits       | 216 ms                                                             | 215 ms: 1.00x faster                                                   |
| Geometric mean | (ref)                                                              | 1.24x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_compile  | 97.0 ms                                                            | 87.8 ms: 1.10x faster                                                  |
| regex_v8       | 15.0 ms                                                            | 14.4 ms: 1.04x faster                                                  |
| regex_dna      | 147 ms                                                             | 144 ms: 1.02x faster                                                   |
| regex_effbot   | 1.98 ms                                                            | 2.07 ms: 1.05x slower                                                  |
| Geometric mean | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| unpickle_pure_python | 163 us                                                             | 119 us: 1.36x faster                                                   |
| urlsafe_base64_small | 340 us                                                             | 256 us: 1.33x faster                                                   |
| json_dumps           | 7.52 ms                                                            | 5.86 ms: 1.29x faster                                                  |
| base64_small         | 227 us                                                             | 181 us: 1.25x faster                                                   |
| base16_small         | 265 us                                                             | 213 us: 1.24x faster                                                   |
| ascii85_large        | 681 ms                                                             | 550 ms: 1.24x faster                                                   |
| ascii85_small        | 13.0 ms                                                            | 10.8 ms: 1.21x faster                                                  |
| xml_etree_process    | 50.0 ms                                                            | 42.5 ms: 1.18x faster                                                  |
| pickle_pure_python   | 251 us                                                             | 216 us: 1.16x faster                                                   |
| xml_etree_iterparse  | 85.5 ms                                                            | 73.6 ms: 1.16x faster                                                  |
| xml_etree_generate   | 68.1 ms                                                            | 58.8 ms: 1.16x faster                                                  |
| base85_small         | 4.66 ms                                                            | 4.32 ms: 1.08x faster                                                  |
| json_loads           | 18.6 us                                                            | 17.5 us: 1.07x faster                                                  |
| base85_large         | 249 ms                                                             | 236 ms: 1.06x faster                                                   |
| pickle_dict          | 20.0 us                                                            | 19.2 us: 1.04x faster                                                  |
| base16_large         | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| xml_etree_parse      | 118 ms                                                             | 113 ms: 1.04x faster                                                   |
| pickle_list          | 3.03 us                                                            | 2.92 us: 1.04x faster                                                  |
| unpickle_list        | 3.03 us                                                            | 2.93 us: 1.03x faster                                                  |
| unpickle             | 10.5 us                                                            | 10.2 us: 1.02x faster                                                  |
| base32_small         | 5.71 ms                                                            | 5.65 ms: 1.01x faster                                                  |
| pickle               | 8.04 us                                                            | 7.98 us: 1.01x faster                                                  |
| base64_large         | 5.70 ms                                                            | 5.74 ms: 1.01x slower                                                  |
| tomli_loads          | 1.49 sec                                                           | 1.63 sec: 1.09x slower                                                 |
| Geometric mean       | (ref)                                                              | 1.11x faster                                                           |

Benchmark hidden because not significant (1): base32_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 9.64 ms: 1.03x faster                                                  |
| python_startup_no_site | 6.52 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| Geometric mean         | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| mako           | 8.69 ms                                                            | 7.28 ms: 1.19x faster                                                  |
| genshi_text    | 18.0 ms                                                            | 17.0 ms: 1.06x faster                                                  |
| genshi_xml     | 43.2 ms                                                            | 47.1 ms: 1.09x slower                                                  |
| Geometric mean | (ref)                                                              | 1.04x faster                                                           |

Benchmark hidden because not significant (1): django_template

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 8.81 ms: 1.41x faster                                                  |
| thread_mandelbrot_naive     | 207 ms                                                             | 173 ms: 1.19x faster                                                   |
| thread_mandelbrot_optimized | 205 ms                                                             | 174 ms: 1.18x faster                                                   |
| thread_pipeline_naive       | 34.9 ms                                                            | 31.5 ms: 1.11x faster                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 16.6 ms: 1.06x faster                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 24.5 ms: 1.05x faster                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 38.3 ms: 1.05x faster                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 38.0 ms: 1.04x faster                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 20.5 ms: 1.03x faster                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 18.9 ms: 1.03x slower                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 14.9 ms: 1.04x slower                                                  |
| thread_montecarlo_optimized | 12.9 ms                                                            | 13.9 ms: 1.08x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.07x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| argparse_many_optionals          | 34.5 ms                                                            | 8.17 ms: 4.22x faster                                                  |
| richards                         | 34.7 ms                                                            | 15.8 ms: 2.19x faster                                                  |
| richards_super                   | 40.3 ms                                                            | 19.4 ms: 2.08x faster                                                  |
| nbody                            | 74.2 ms                                                            | 49.3 ms: 1.51x faster                                                  |
| thread_memo_naive                | 12.4 ms                                                            | 8.81 ms: 1.41x faster                                                  |
| unpickle_pure_python             | 163 us                                                             | 119 us: 1.36x faster                                                   |
| argparse_subparsers              | 687 us                                                             | 505 us: 1.36x faster                                                   |
| float                            | 51.2 ms                                                            | 38.5 ms: 1.33x faster                                                  |
| urlsafe_base64_small             | 340 us                                                             | 256 us: 1.33x faster                                                   |
| deltablue                        | 2.76 ms                                                            | 2.08 ms: 1.33x faster                                                  |
| scimark_fft                      | 211 ms                                                             | 161 ms: 1.31x faster                                                   |
| scimark_monte_carlo              | 42.3 ms                                                            | 32.4 ms: 1.31x faster                                                  |
| json_dumps                       | 7.52 ms                                                            | 5.86 ms: 1.29x faster                                                  |
| base64_small                     | 227 us                                                             | 181 us: 1.25x faster                                                   |
| logging_silent                   | 59.2 ns                                                            | 47.5 ns: 1.25x faster                                                  |
| base16_small                     | 265 us                                                             | 213 us: 1.24x faster                                                   |
| go                               | 91.1 ms                                                            | 73.4 ms: 1.24x faster                                                  |
| ascii85_large                    | 681 ms                                                             | 550 ms: 1.24x faster                                                   |
| pyflate                          | 309 ms                                                             | 253 ms: 1.22x faster                                                   |
| ascii85_small                    | 13.0 ms                                                            | 10.8 ms: 1.21x faster                                                  |
| mako                             | 8.69 ms                                                            | 7.28 ms: 1.19x faster                                                  |
| thread_mandelbrot_naive          | 207 ms                                                             | 173 ms: 1.19x faster                                                   |
| quadtree_nbody                   | 654 ms                                                             | 549 ms: 1.19x faster                                                   |
| deepcopy_memo                    | 19.1 us                                                            | 16.1 us: 1.19x faster                                                  |
| telco                            | 5.39 ms                                                            | 4.56 ms: 1.18x faster                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 174 ms: 1.18x faster                                                   |
| xml_etree_process                | 50.0 ms                                                            | 42.5 ms: 1.18x faster                                                  |
| pathlib                          | 12.7 ms                                                            | 10.8 ms: 1.17x faster                                                  |
| scimark_lu                       | 74.7 ms                                                            | 63.8 ms: 1.17x faster                                                  |
| fannkuch                         | 246 ms                                                             | 211 ms: 1.17x faster                                                   |
| scimark_sor                      | 78.2 ms                                                            | 66.9 ms: 1.17x faster                                                  |
| pickle_pure_python               | 251 us                                                             | 216 us: 1.16x faster                                                   |
| async_tree_eager_io              | 568 ms                                                             | 488 ms: 1.16x faster                                                   |
| xml_etree_iterparse              | 85.5 ms                                                            | 73.6 ms: 1.16x faster                                                  |
| xml_etree_generate               | 68.1 ms                                                            | 58.8 ms: 1.16x faster                                                  |
| asyncio_tcp                      | 324 ms                                                             | 280 ms: 1.16x faster                                                   |
| spectral_norm                    | 64.1 ms                                                            | 55.8 ms: 1.15x faster                                                  |
| noop                             | 19.2 ns                                                            | 16.8 ns: 1.14x faster                                                  |
| async_tree_eager_io_tg           | 565 ms                                                             | 496 ms: 1.14x faster                                                   |
| crypto_pyaes                     | 56.7 ms                                                            | 50.3 ms: 1.13x faster                                                  |
| thread_pipeline_naive            | 34.9 ms                                                            | 31.5 ms: 1.11x faster                                                  |
| regex_compile                    | 97.0 ms                                                            | 87.8 ms: 1.10x faster                                                  |
| async_tree_io                    | 549 ms                                                             | 498 ms: 1.10x faster                                                   |
| logging_format                   | 6.00 us                                                            | 5.45 us: 1.10x faster                                                  |
| async_tree_none                  | 233 ms                                                             | 212 ms: 1.10x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 496 ms: 1.10x faster                                                   |
| async_tree_memoization           | 285 ms                                                             | 260 ms: 1.09x faster                                                   |
| bpe_tokeniser                    | 3.11 sec                                                           | 2.86 sec: 1.09x faster                                                 |
| base85_small                     | 4.66 ms                                                            | 4.32 ms: 1.08x faster                                                  |
| json                             | 3.46 ms                                                            | 3.21 ms: 1.08x faster                                                  |
| async_tree_memoization_tg        | 279 ms                                                             | 259 ms: 1.08x faster                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 399 ms: 1.07x faster                                                   |
| meteor_contest                   | 85.4 ms                                                            | 79.5 ms: 1.07x faster                                                  |
| json_loads                       | 18.6 us                                                            | 17.5 us: 1.07x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 10.7 us: 1.07x faster                                                  |
| async_tree_eager_tg              | 182 ms                                                             | 172 ms: 1.06x faster                                                   |
| genshi_text                      | 18.0 ms                                                            | 17.0 ms: 1.06x faster                                                  |
| base85_large                     | 249 ms                                                             | 236 ms: 1.06x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 405 ms: 1.06x faster                                                   |
| thread_memo_optimized            | 17.5 ms                                                            | 16.6 ms: 1.06x faster                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 24.5 ms: 1.05x faster                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 38.3 ms: 1.05x faster                                                  |
| async_tree_none_tg               | 224 ms                                                             | 213 ms: 1.05x faster                                                   |
| networkx_k_core                  | 2.05 sec                                                           | 1.96 sec: 1.05x faster                                                 |
| thrift                           | 2.00 ms                                                            | 1.91 ms: 1.04x faster                                                  |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.77 ms: 1.04x faster                                                  |
| fastapi_http                     | 222 ms                                                             | 212 ms: 1.04x faster                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 175 ms: 1.04x faster                                                   |
| pickle_dict                      | 20.0 us                                                            | 19.2 us: 1.04x faster                                                  |
| async_tree_eager                 | 83.0 ms                                                            | 79.9 ms: 1.04x faster                                                  |
| regex_v8                         | 15.0 ms                                                            | 14.4 ms: 1.04x faster                                                  |
| thread_accumulate_optimized      | 39.5 ms                                                            | 38.0 ms: 1.04x faster                                                  |
| base16_large                     | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| xml_etree_parse                  | 118 ms                                                             | 113 ms: 1.04x faster                                                   |
| pickle_list                      | 3.03 us                                                            | 2.92 us: 1.04x faster                                                  |
| unpickle_list                    | 3.03 us                                                            | 2.93 us: 1.03x faster                                                  |
| thread_counter_naive             | 21.2 ms                                                            | 20.5 ms: 1.03x faster                                                  |
| decimal_pi                       | 209 ms                                                             | 203 ms: 1.03x faster                                                   |
| nqueens                          | 59.8 ms                                                            | 58.0 ms: 1.03x faster                                                  |
| logging_simple                   | 5.02 us                                                            | 4.87 us: 1.03x faster                                                  |
| python_startup                   | 9.93 ms                                                            | 9.64 ms: 1.03x faster                                                  |
| raytrace                         | 201 ms                                                             | 195 ms: 1.03x faster                                                   |
| chaos                            | 42.9 ms                                                            | 41.8 ms: 1.03x faster                                                  |
| unpickle                         | 10.5 us                                                            | 10.2 us: 1.02x faster                                                  |
| sqlglot_v2_parse                 | 954 us                                                             | 933 us: 1.02x faster                                                   |
| python_startup_no_site           | 6.52 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| regex_dna                        | 147 ms                                                             | 144 ms: 1.02x faster                                                   |
| html5lib                         | 45.3 ms                                                            | 44.6 ms: 1.02x faster                                                  |
| base32_small                     | 5.71 ms                                                            | 5.65 ms: 1.01x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 324 ms: 1.01x faster                                                   |
| pickle                           | 8.04 us                                                            | 7.98 us: 1.01x faster                                                  |
| decimal_factorial                | 174 ms                                                             | 173 ms: 1.01x faster                                                   |
| pidigits                         | 216 ms                                                             | 215 ms: 1.00x faster                                                   |
| base64_large                     | 5.70 ms                                                            | 5.74 ms: 1.01x slower                                                  |
| networkx_shortest_path           | 447 ms                                                             | 451 ms: 1.01x slower                                                   |
| tornado_http                     | 101 ms                                                             | 102 ms: 1.01x slower                                                   |
| pprint_safe_repr                 | 534 ms                                                             | 544 ms: 1.02x slower                                                   |
| coverage                         | 54.5 ms                                                            | 55.6 ms: 1.02x slower                                                  |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.24 ms: 1.02x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 382 ms: 1.02x slower                                                   |
| pprint_pformat                   | 1.10 sec                                                           | 1.13 sec: 1.03x slower                                                 |
| coroutines                       | 15.1 ms                                                            | 15.5 ms: 1.03x slower                                                  |
| thread_counter_optimized         | 18.3 ms                                                            | 18.9 ms: 1.03x slower                                                  |
| asyncio_websockets               | 305 ms                                                             | 315 ms: 1.03x slower                                                   |
| async_generators                 | 231 ms                                                             | 239 ms: 1.03x slower                                                   |
| chameleon                        | 10.3 ms                                                            | 10.6 ms: 1.03x slower                                                  |
| hexiom                           | 4.50 ms                                                            | 4.65 ms: 1.03x slower                                                  |
| networkx_connected_components    | 425 ms                                                             | 440 ms: 1.04x slower                                                   |
| thread_montecarlo_naive          | 14.3 ms                                                            | 14.9 ms: 1.04x slower                                                  |
| typing_runtime_protocols         | 115 us                                                             | 120 us: 1.04x slower                                                   |
| pycparser                        | 878 ms                                                             | 915 ms: 1.04x slower                                                   |
| regex_effbot                     | 1.98 ms                                                            | 2.07 ms: 1.05x slower                                                  |
| xdsl_constant_fold               | 36.0 ms                                                            | 37.7 ms: 1.05x slower                                                  |
| docutils                         | 1.98 sec                                                           | 2.09 sec: 1.06x slower                                                 |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.6 ms: 1.06x slower                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 13.9 ms: 1.08x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 373 ms: 1.08x slower                                                   |
| genshi_xml                       | 43.2 ms                                                            | 47.1 ms: 1.09x slower                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.63 sec: 1.09x slower                                                 |
| deepcopy                         | 198 us                                                             | 218 us: 1.10x slower                                                   |
| deepcopy_reduce                  | 2.02 us                                                            | 2.29 us: 1.14x slower                                                  |
| sympy_integrate                  | 15.1 ms                                                            | 17.2 ms: 1.14x slower                                                  |
| sympy_sum                        | 109 ms                                                             | 124 ms: 1.14x slower                                                   |
| mdp                              | 971 ms                                                             | 1.13 sec: 1.17x slower                                                 |
| mypy2                            | 780 ms                                                             | 911 ms: 1.17x slower                                                   |
| sympy_str                        | 200 ms                                                             | 239 ms: 1.19x slower                                                   |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 102 ms: 1.20x slower                                                   |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 50.4 ms: 1.21x slower                                                  |
| pylint                           | 222 ms                                                             | 271 ms: 1.22x slower                                                   |
| unpack_sequence                  | 35.6 ns                                                            | 64.4 ns: 1.81x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.08x faster                                                           |

Benchmark hidden because not significant (6): async_tree_eager_memoization_tg, base32_large, create_gc_cycles, gc_traversal, django_template, generators

- Geometric mean (including insignificant results): 1.077x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.02x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.03x