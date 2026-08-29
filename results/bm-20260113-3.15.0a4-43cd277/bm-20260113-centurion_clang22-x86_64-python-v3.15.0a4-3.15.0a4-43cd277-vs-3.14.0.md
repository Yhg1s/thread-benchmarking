# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.055x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.02x faster
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 10.1 ms: 1.02x faster                                                  |
| fastapi_http   | 222 ms                                                             | 215 ms: 1.03x faster                                                   |
| html5lib       | 45.3 ms                                                            | 43.7 ms: 1.04x faster                                                  |
| tornado_http   | 101 ms                                                             | 99.6 ms: 1.01x faster                                                  |
| Geometric mean | (ref)                                                              | 1.02x faster                                                           |

Benchmark hidden because not significant (1): docutils

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 565 ms                                                             | 473 ms: 1.19x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 272 ms: 1.19x faster                                                   |
| async_tree_eager_io              | 568 ms                                                             | 487 ms: 1.17x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 484 ms: 1.13x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 200 ms: 1.12x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 491 ms: 1.12x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 402 ms: 1.06x faster                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 263 ms: 1.06x faster                                                   |
| async_tree_memoization           | 285 ms                                                             | 269 ms: 1.06x faster                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 405 ms: 1.06x faster                                                   |
| async_tree_none                  | 233 ms                                                             | 222 ms: 1.05x faster                                                   |
| async_generators                 | 231 ms                                                             | 220 ms: 1.05x faster                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 175 ms: 1.04x faster                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 175 ms: 1.04x faster                                                   |
| coroutines                       | 15.1 ms                                                            | 14.6 ms: 1.04x faster                                                  |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 228 ms: 1.04x faster                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 80.5 ms: 1.03x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 367 ms: 1.02x faster                                                   |
| asyncio_websockets               | 305 ms                                                             | 312 ms: 1.02x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.07x faster                                                           |

Benchmark hidden because not significant (1): async_tree_eager_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 17.9 ns: 1.07x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 173 ms: 1.01x faster                                                   |
| decimal_pi        | 209 ms                                                             | 207 ms: 1.01x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.01x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| nbody          | 74.2 ms                                                            | 64.4 ms: 1.15x faster                                                  |
| quadtree_nbody | 654 ms                                                             | 572 ms: 1.14x faster                                                   |
| float          | 51.2 ms                                                            | 47.0 ms: 1.09x faster                                                  |
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| Geometric mean | (ref)                                                              | 1.09x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_dna      | 147 ms                                                             | 143 ms: 1.03x faster                                                   |
| regex_compile  | 97.0 ms                                                            | 96.1 ms: 1.01x faster                                                  |
| regex_effbot   | 1.98 ms                                                            | 2.06 ms: 1.04x slower                                                  |
| Geometric mean | (ref)                                                              | 1.00x slower                                                           |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| json_dumps           | 7.52 ms                                                            | 6.55 ms: 1.15x faster                                                  |
| xml_etree_iterparse  | 85.5 ms                                                            | 76.7 ms: 1.11x faster                                                  |
| json_loads           | 18.6 us                                                            | 17.4 us: 1.07x faster                                                  |
| unpickle_pure_python | 163 us                                                             | 154 us: 1.06x faster                                                   |
| urlsafe_base64_small | 340 us                                                             | 322 us: 1.06x faster                                                   |
| base64_small         | 227 us                                                             | 216 us: 1.05x faster                                                   |
| xml_etree_process    | 50.0 ms                                                            | 47.7 ms: 1.05x faster                                                  |
| pickle_pure_python   | 251 us                                                             | 240 us: 1.05x faster                                                   |
| pickle_dict          | 20.0 us                                                            | 19.1 us: 1.05x faster                                                  |
| base32_large         | 289 ms                                                             | 277 ms: 1.05x faster                                                   |
| base85_small         | 4.66 ms                                                            | 4.48 ms: 1.04x faster                                                  |
| base16_large         | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| xml_etree_generate   | 68.1 ms                                                            | 65.7 ms: 1.04x faster                                                  |
| base16_small         | 265 us                                                             | 256 us: 1.03x faster                                                   |
| base85_large         | 249 ms                                                             | 242 ms: 1.03x faster                                                   |
| base32_small         | 5.71 ms                                                            | 5.53 ms: 1.03x faster                                                  |
| pickle_list          | 3.03 us                                                            | 2.98 us: 1.02x faster                                                  |
| pickle               | 8.04 us                                                            | 7.91 us: 1.02x faster                                                  |
| xml_etree_parse      | 118 ms                                                             | 116 ms: 1.02x faster                                                   |
| unpickle_list        | 3.03 us                                                            | 3.00 us: 1.01x faster                                                  |
| ascii85_small        | 13.0 ms                                                            | 12.9 ms: 1.01x faster                                                  |
| base64_large         | 5.70 ms                                                            | 5.73 ms: 1.01x slower                                                  |
| ascii85_large        | 681 ms                                                             | 687 ms: 1.01x slower                                                   |
| tomli_loads          | 1.49 sec                                                           | 1.60 sec: 1.07x slower                                                 |
| Geometric mean       | (ref)                                                              | 1.03x faster                                                           |

Benchmark hidden because not significant (1): unpickle

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 9.46 ms: 1.05x faster                                                  |
| python_startup_no_site | 6.52 ms                                                            | 6.24 ms: 1.04x faster                                                  |
| Geometric mean         | (ref)                                                              | 1.05x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| mako            | 8.69 ms                                                            | 8.36 ms: 1.04x faster                                                  |
| genshi_xml      | 43.2 ms                                                            | 43.0 ms: 1.01x faster                                                  |
| django_template | 30.5 ms                                                            | 31.1 ms: 1.02x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.01x faster                                                           |

Benchmark hidden because not significant (1): genshi_text

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 9.47 ms: 1.31x faster                                                  |
| thread_mandelbrot_naive     | 207 ms                                                             | 182 ms: 1.13x faster                                                   |
| thread_mandelbrot_optimized | 205 ms                                                             | 183 ms: 1.12x faster                                                   |
| thread_montecarlo_optimized | 12.9 ms                                                            | 11.6 ms: 1.11x faster                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 13.4 ms: 1.07x faster                                                  |
| thread_pipeline_naive       | 34.9 ms                                                            | 35.2 ms: 1.01x slower                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 17.8 ms: 1.02x slower                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 41.9 ms: 1.04x slower                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 26.9 ms: 1.04x slower                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 41.4 ms: 1.05x slower                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 22.5 ms: 1.06x slower                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 20.1 ms: 1.09x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.03x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| argparse_many_optionals          | 34.5 ms                                                            | 8.23 ms: 4.19x faster                                                  |
| argparse_subparsers              | 687 us                                                             | 498 us: 1.38x faster                                                   |
| thread_memo_naive                | 12.4 ms                                                            | 9.47 ms: 1.31x faster                                                  |
| async_tree_eager_io_tg           | 565 ms                                                             | 473 ms: 1.19x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 272 ms: 1.19x faster                                                   |
| pathlib                          | 12.7 ms                                                            | 10.7 ms: 1.18x faster                                                  |
| async_tree_eager_io              | 568 ms                                                             | 487 ms: 1.17x faster                                                   |
| nbody                            | 74.2 ms                                                            | 64.4 ms: 1.15x faster                                                  |
| json_dumps                       | 7.52 ms                                                            | 6.55 ms: 1.15x faster                                                  |
| deepcopy_memo                    | 19.1 us                                                            | 16.7 us: 1.14x faster                                                  |
| quadtree_nbody                   | 654 ms                                                             | 572 ms: 1.14x faster                                                   |
| scimark_fft                      | 211 ms                                                             | 185 ms: 1.14x faster                                                   |
| thread_mandelbrot_naive          | 207 ms                                                             | 182 ms: 1.13x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 484 ms: 1.13x faster                                                   |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.58 ms: 1.12x faster                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 183 ms: 1.12x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 200 ms: 1.12x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 491 ms: 1.12x faster                                                   |
| xml_etree_iterparse              | 85.5 ms                                                            | 76.7 ms: 1.11x faster                                                  |
| richards_super                   | 40.3 ms                                                            | 36.2 ms: 1.11x faster                                                  |
| richards                         | 34.7 ms                                                            | 31.2 ms: 1.11x faster                                                  |
| telco                            | 5.39 ms                                                            | 4.85 ms: 1.11x faster                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 11.6 ms: 1.11x faster                                                  |
| scimark_monte_carlo              | 42.3 ms                                                            | 38.2 ms: 1.11x faster                                                  |
| chaos                            | 42.9 ms                                                            | 39.0 ms: 1.10x faster                                                  |
| spectral_norm                    | 64.1 ms                                                            | 58.8 ms: 1.09x faster                                                  |
| float                            | 51.2 ms                                                            | 47.0 ms: 1.09x faster                                                  |
| raytrace                         | 201 ms                                                             | 186 ms: 1.08x faster                                                   |
| networkx_k_core                  | 2.05 sec                                                           | 1.90 sec: 1.08x faster                                                 |
| deltablue                        | 2.76 ms                                                            | 2.56 ms: 1.08x faster                                                  |
| nqueens                          | 59.8 ms                                                            | 55.6 ms: 1.08x faster                                                  |
| go                               | 91.1 ms                                                            | 85.1 ms: 1.07x faster                                                  |
| noop                             | 19.2 ns                                                            | 17.9 ns: 1.07x faster                                                  |
| json_loads                       | 18.6 us                                                            | 17.4 us: 1.07x faster                                                  |
| logging_format                   | 6.00 us                                                            | 5.62 us: 1.07x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 10.7 us: 1.07x faster                                                  |
| thread_montecarlo_naive          | 14.3 ms                                                            | 13.4 ms: 1.07x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 402 ms: 1.06x faster                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 263 ms: 1.06x faster                                                   |
| logging_silent                   | 59.2 ns                                                            | 55.8 ns: 1.06x faster                                                  |
| fannkuch                         | 246 ms                                                             | 232 ms: 1.06x faster                                                   |
| scimark_lu                       | 74.7 ms                                                            | 70.5 ms: 1.06x faster                                                  |
| unpickle_pure_python             | 163 us                                                             | 154 us: 1.06x faster                                                   |
| async_tree_memoization           | 285 ms                                                             | 269 ms: 1.06x faster                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 405 ms: 1.06x faster                                                   |
| urlsafe_base64_small             | 340 us                                                             | 322 us: 1.06x faster                                                   |
| pyflate                          | 309 ms                                                             | 293 ms: 1.06x faster                                                   |
| scimark_sor                      | 78.2 ms                                                            | 74.2 ms: 1.05x faster                                                  |
| async_tree_none                  | 233 ms                                                             | 222 ms: 1.05x faster                                                   |
| base64_small                     | 227 us                                                             | 216 us: 1.05x faster                                                   |
| python_startup                   | 9.93 ms                                                            | 9.46 ms: 1.05x faster                                                  |
| async_generators                 | 231 ms                                                             | 220 ms: 1.05x faster                                                   |
| typing_runtime_protocols         | 115 us                                                             | 110 us: 1.05x faster                                                   |
| crypto_pyaes                     | 56.7 ms                                                            | 54.0 ms: 1.05x faster                                                  |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.15 ms: 1.05x faster                                                  |
| mdp                              | 971 ms                                                             | 927 ms: 1.05x faster                                                   |
| xml_etree_process                | 50.0 ms                                                            | 47.7 ms: 1.05x faster                                                  |
| pickle_pure_python               | 251 us                                                             | 240 us: 1.05x faster                                                   |
| pickle_dict                      | 20.0 us                                                            | 19.1 us: 1.05x faster                                                  |
| base32_large                     | 289 ms                                                             | 277 ms: 1.05x faster                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 175 ms: 1.04x faster                                                   |
| python_startup_no_site           | 6.52 ms                                                            | 6.24 ms: 1.04x faster                                                  |
| async_tree_eager_tg              | 182 ms                                                             | 175 ms: 1.04x faster                                                   |
| base85_small                     | 4.66 ms                                                            | 4.48 ms: 1.04x faster                                                  |
| mako                             | 8.69 ms                                                            | 8.36 ms: 1.04x faster                                                  |
| meteor_contest                   | 85.4 ms                                                            | 82.1 ms: 1.04x faster                                                  |
| base16_large                     | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| coroutines                       | 15.1 ms                                                            | 14.6 ms: 1.04x faster                                                  |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 228 ms: 1.04x faster                                                   |
| hexiom                           | 4.50 ms                                                            | 4.33 ms: 1.04x faster                                                  |
| json                             | 3.46 ms                                                            | 3.34 ms: 1.04x faster                                                  |
| xml_etree_generate               | 68.1 ms                                                            | 65.7 ms: 1.04x faster                                                  |
| html5lib                         | 45.3 ms                                                            | 43.7 ms: 1.04x faster                                                  |
| base16_small                     | 265 us                                                             | 256 us: 1.03x faster                                                   |
| pprint_pformat                   | 1.10 sec                                                           | 1.06 sec: 1.03x faster                                                 |
| fastapi_http                     | 222 ms                                                             | 215 ms: 1.03x faster                                                   |
| deepcopy                         | 198 us                                                             | 192 us: 1.03x faster                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 80.5 ms: 1.03x faster                                                  |
| base85_large                     | 249 ms                                                             | 242 ms: 1.03x faster                                                   |
| deepcopy_reduce                  | 2.02 us                                                            | 1.96 us: 1.03x faster                                                  |
| base32_small                     | 5.71 ms                                                            | 5.53 ms: 1.03x faster                                                  |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.01 sec: 1.03x faster                                                 |
| thrift                           | 2.00 ms                                                            | 1.94 ms: 1.03x faster                                                  |
| pprint_safe_repr                 | 534 ms                                                             | 519 ms: 1.03x faster                                                   |
| regex_dna                        | 147 ms                                                             | 143 ms: 1.03x faster                                                   |
| pylint                           | 222 ms                                                             | 216 ms: 1.03x faster                                                   |
| sqlglot_v2_parse                 | 954 us                                                             | 928 us: 1.03x faster                                                   |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 82.7 ms: 1.03x faster                                                  |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 40.8 ms: 1.02x faster                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| chameleon                        | 10.3 ms                                                            | 10.1 ms: 1.02x faster                                                  |
| mypy2                            | 780 ms                                                             | 765 ms: 1.02x faster                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 367 ms: 1.02x faster                                                   |
| pickle_list                      | 3.03 us                                                            | 2.98 us: 1.02x faster                                                  |
| logging_simple                   | 5.02 us                                                            | 4.94 us: 1.02x faster                                                  |
| pickle                           | 8.04 us                                                            | 7.91 us: 1.02x faster                                                  |
| xml_etree_parse                  | 118 ms                                                             | 116 ms: 1.02x faster                                                   |
| pycparser                        | 878 ms                                                             | 865 ms: 1.01x faster                                                   |
| tornado_http                     | 101 ms                                                             | 99.6 ms: 1.01x faster                                                  |
| networkx_shortest_path           | 447 ms                                                             | 441 ms: 1.01x faster                                                   |
| unpickle_list                    | 3.03 us                                                            | 3.00 us: 1.01x faster                                                  |
| decimal_factorial                | 174 ms                                                             | 173 ms: 1.01x faster                                                   |
| decimal_pi                       | 209 ms                                                             | 207 ms: 1.01x faster                                                   |
| regex_compile                    | 97.0 ms                                                            | 96.1 ms: 1.01x faster                                                  |
| ascii85_small                    | 13.0 ms                                                            | 12.9 ms: 1.01x faster                                                  |
| gc_traversal                     | 3.36 ms                                                            | 3.33 ms: 1.01x faster                                                  |
| genshi_xml                       | 43.2 ms                                                            | 43.0 ms: 1.01x faster                                                  |
| create_gc_cycles                 | 2.02 ms                                                            | 2.01 ms: 1.00x faster                                                  |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| base64_large                     | 5.70 ms                                                            | 5.73 ms: 1.01x slower                                                  |
| sqlalchemy_imperative            | 14.8 ms                                                            | 14.9 ms: 1.01x slower                                                  |
| sympy_integrate                  | 15.1 ms                                                            | 15.3 ms: 1.01x slower                                                  |
| thread_pipeline_naive            | 34.9 ms                                                            | 35.2 ms: 1.01x slower                                                  |
| ascii85_large                    | 681 ms                                                             | 687 ms: 1.01x slower                                                   |
| networkx_connected_components    | 425 ms                                                             | 429 ms: 1.01x slower                                                   |
| thread_memo_optimized            | 17.5 ms                                                            | 17.8 ms: 1.02x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 350 ms: 1.02x slower                                                   |
| sympy_sum                        | 109 ms                                                             | 111 ms: 1.02x slower                                                   |
| django_template                  | 30.5 ms                                                            | 31.1 ms: 1.02x slower                                                  |
| sympy_str                        | 200 ms                                                             | 204 ms: 1.02x slower                                                   |
| asyncio_websockets               | 305 ms                                                             | 312 ms: 1.02x slower                                                   |
| coverage                         | 54.5 ms                                                            | 56.2 ms: 1.03x slower                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 41.9 ms: 1.04x slower                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 26.9 ms: 1.04x slower                                                  |
| regex_effbot                     | 1.98 ms                                                            | 2.06 ms: 1.04x slower                                                  |
| thread_accumulate_optimized      | 39.5 ms                                                            | 41.4 ms: 1.05x slower                                                  |
| thread_counter_naive             | 21.2 ms                                                            | 22.5 ms: 1.06x slower                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.60 sec: 1.07x slower                                                 |
| thread_counter_optimized         | 18.3 ms                                                            | 20.1 ms: 1.09x slower                                                  |
| unpack_sequence                  | 35.6 ns                                                            | 43.4 ns: 1.22x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.05x faster                                                           |

Benchmark hidden because not significant (7): xdsl_constant_fold, generators, docutils, genshi_text, async_tree_eager_cpu_io_mixed, regex_v8, unpickle

- Geometric mean (including insignificant results): 1.055x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.03x
- 99% likely to have a speedup of 1.02x

# Memory
- memory change: 1.01x