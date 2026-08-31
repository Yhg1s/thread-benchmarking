# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.054x slower
- HPT reliability: 99.96%
- HPT 99th percentile: 1.00x slower
- Memory change: 0.98x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.1 ms: 1.08x slower                                              |
| docutils       | 1.98 sec                                                           | 1.99 sec: 1.01x slower                                             |
| fastapi_http   | 222 ms                                                             | 219 ms: 1.01x faster                                               |
| html5lib       | 45.3 ms                                                            | 50.9 ms: 1.12x slower                                              |
| Geometric mean | (ref)                                                              | 1.04x slower                                                       |

Benchmark hidden because not significant (1): tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                             | 58.4 ms: 3.12x faster                                              |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 176 ms: 1.34x faster                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 305 ms: 1.23x faster                                               |
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.07x faster                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 349 ms: 1.07x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 96.3 ms: 1.16x slower                                              |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 498 ms: 1.16x slower                                               |
| async_generators                 | 231 ms                                                             | 272 ms: 1.18x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 509 ms: 1.19x slower                                               |
| coroutines                       | 15.1 ms                                                            | 18.2 ms: 1.20x slower                                              |
| async_tree_eager_memoization     | 183 ms                                                             | 228 ms: 1.25x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 726 ms: 1.29x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 290 ms: 1.29x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 758 ms: 1.34x slower                                               |
| async_tree_none                  | 233 ms                                                             | 313 ms: 1.34x slower                                               |
| async_tree_io                    | 549 ms                                                             | 749 ms: 1.36x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 393 ms: 1.38x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 782 ms: 1.43x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 419 ms: 1.50x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.09x slower                                                       |

Benchmark hidden because not significant (2): asyncio_websockets, asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 20.3 ns: 1.06x slower                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_pi        | 209 ms                                                             | 213 ms: 1.02x slower                                               |
| decimal_factorial | 174 ms                                                             | 177 ms: 1.02x slower                                               |
| Geometric mean    | (ref)                                                              | 1.02x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| nbody          | 74.2 ms                                                            | 61.7 ms: 1.20x faster                                              |
| quadtree_nbody | 654 ms                                                             | 554 ms: 1.18x faster                                               |
| pidigits       | 216 ms                                                             | 213 ms: 1.01x faster                                               |
| float          | 51.2 ms                                                            | 53.4 ms: 1.04x slower                                              |
| Geometric mean | (ref)                                                              | 1.08x faster                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                            | 14.7 ms: 1.02x faster                                              |
| regex_dna      | 147 ms                                                             | 155 ms: 1.05x slower                                               |
| regex_compile  | 97.0 ms                                                            | 103 ms: 1.06x slower                                               |
| regex_effbot   | 1.98 ms                                                            | 2.32 ms: 1.18x slower                                              |
| Geometric mean | (ref)                                                              | 1.07x slower                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| ascii85_large        | 681 ms                                                             | 563 ms: 1.21x faster                                               |
| ascii85_small        | 13.0 ms                                                            | 11.3 ms: 1.16x faster                                              |
| pickle_pure_python   | 251 us                                                             | 222 us: 1.13x faster                                               |
| unpickle_pure_python | 163 us                                                             | 147 us: 1.11x faster                                               |
| pickle               | 8.04 us                                                            | 7.33 us: 1.10x faster                                              |
| pickle_list          | 3.03 us                                                            | 2.78 us: 1.09x faster                                              |
| xml_etree_process    | 50.0 ms                                                            | 46.1 ms: 1.09x faster                                              |
| json_dumps           | 7.52 ms                                                            | 6.97 ms: 1.08x faster                                              |
| xml_etree_generate   | 68.1 ms                                                            | 63.8 ms: 1.07x faster                                              |
| base85_small         | 4.66 ms                                                            | 4.46 ms: 1.05x faster                                              |
| json_loads           | 18.6 us                                                            | 18.1 us: 1.03x faster                                              |
| urlsafe_base64_small | 340 us                                                             | 331 us: 1.03x faster                                               |
| base64_small         | 227 us                                                             | 222 us: 1.03x faster                                               |
| pickle_dict          | 20.0 us                                                            | 19.6 us: 1.02x faster                                              |
| base85_large         | 249 ms                                                             | 246 ms: 1.01x faster                                               |
| xml_etree_iterparse  | 85.5 ms                                                            | 85.0 ms: 1.01x faster                                              |
| unpickle_list        | 3.03 us                                                            | 3.09 us: 1.02x slower                                              |
| xml_etree_parse      | 118 ms                                                             | 120 ms: 1.02x slower                                               |
| tomli_loads          | 1.49 sec                                                           | 1.52 sec: 1.02x slower                                             |
| base32_small         | 5.71 ms                                                            | 6.11 ms: 1.07x slower                                              |
| base32_large         | 289 ms                                                             | 310 ms: 1.07x slower                                               |
| base16_small         | 265 us                                                             | 839 us: 3.17x slower                                               |
| base16_large         | 6.35 ms                                                            | 42.6 ms: 6.71x slower                                              |
| Geometric mean       | (ref)                                                              | 1.09x slower                                                       |

Benchmark hidden because not significant (2): base64_large, unpickle

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 10.3 ms: 1.04x slower                                              |
| python_startup_no_site | 6.52 ms                                                            | 7.29 ms: 1.12x slower                                              |
| Geometric mean         | (ref)                                                              | 1.08x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| mako            | 8.69 ms                                                            | 6.61 ms: 1.31x faster                                              |
| django_template | 30.5 ms                                                            | 33.4 ms: 1.10x slower                                              |
| genshi_text     | 18.0 ms                                                            | 21.1 ms: 1.17x slower                                              |
| genshi_xml      | 43.2 ms                                                            | 51.9 ms: 1.20x slower                                              |
| Geometric mean  | (ref)                                                              | 1.04x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 207 ms                                                             | 175 ms: 1.18x faster                                               |
| thread_accumulate_optimized | 39.5 ms                                                            | 33.6 ms: 1.17x faster                                              |
| thread_mandelbrot_optimized | 205 ms                                                             | 175 ms: 1.17x faster                                               |
| thread_pipeline_optimized   | 25.8 ms                                                            | 22.2 ms: 1.16x faster                                              |
| thread_accumulate_naive     | 40.4 ms                                                            | 34.7 ms: 1.16x faster                                              |
| thread_memo_optimized       | 17.5 ms                                                            | 15.2 ms: 1.15x faster                                              |
| thread_counter_optimized    | 18.3 ms                                                            | 17.7 ms: 1.04x faster                                              |
| thread_counter_naive        | 21.2 ms                                                            | 21.6 ms: 1.02x slower                                              |
| thread_montecarlo_optimized | 12.9 ms                                                            | 13.5 ms: 1.04x slower                                              |
| thread_pipeline_naive       | 34.9 ms                                                            | 48.5 ms: 1.39x slower                                              |
| thread_montecarlo_naive     | 14.3 ms                                                            | 19.9 ms: 1.40x slower                                              |
| thread_memo_naive           | 12.4 ms                                                            | 38.0 ms: 3.07x slower                                              |
| Geometric mean              | (ref)                                                              | 1.08x slower                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                             | 58.4 ms: 3.12x faster                                              |
| argparse_many_optionals          | 34.5 ms                                                            | 13.3 ms: 2.59x faster                                              |
| argparse_subparsers              | 687 us                                                             | 468 us: 1.47x faster                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 176 ms: 1.34x faster                                               |
| mako                             | 8.69 ms                                                            | 6.61 ms: 1.31x faster                                              |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 305 ms: 1.23x faster                                               |
| ascii85_large                    | 681 ms                                                             | 563 ms: 1.21x faster                                               |
| nbody                            | 74.2 ms                                                            | 61.7 ms: 1.20x faster                                              |
| scimark_fft                      | 211 ms                                                             | 178 ms: 1.18x faster                                               |
| quadtree_nbody                   | 654 ms                                                             | 554 ms: 1.18x faster                                               |
| thread_mandelbrot_naive          | 207 ms                                                             | 175 ms: 1.18x faster                                               |
| thread_accumulate_optimized      | 39.5 ms                                                            | 33.6 ms: 1.17x faster                                              |
| thread_mandelbrot_optimized      | 205 ms                                                             | 175 ms: 1.17x faster                                               |
| thread_pipeline_optimized        | 25.8 ms                                                            | 22.2 ms: 1.16x faster                                              |
| thread_accumulate_naive          | 40.4 ms                                                            | 34.7 ms: 1.16x faster                                              |
| ascii85_small                    | 13.0 ms                                                            | 11.3 ms: 1.16x faster                                              |
| thread_memo_optimized            | 17.5 ms                                                            | 15.2 ms: 1.15x faster                                              |
| create_gc_cycles                 | 2.02 ms                                                            | 1.77 ms: 1.14x faster                                              |
| fannkuch                         | 246 ms                                                             | 216 ms: 1.14x faster                                               |
| pickle_pure_python               | 251 us                                                             | 222 us: 1.13x faster                                               |
| crypto_pyaes                     | 56.7 ms                                                            | 50.3 ms: 1.13x faster                                              |
| unpickle_pure_python             | 163 us                                                             | 147 us: 1.11x faster                                               |
| pickle                           | 8.04 us                                                            | 7.33 us: 1.10x faster                                              |
| pickle_list                      | 3.03 us                                                            | 2.78 us: 1.09x faster                                              |
| xml_etree_process                | 50.0 ms                                                            | 46.1 ms: 1.09x faster                                              |
| json_dumps                       | 7.52 ms                                                            | 6.97 ms: 1.08x faster                                              |
| richards_super                   | 40.3 ms                                                            | 37.4 ms: 1.08x faster                                              |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.68 ms: 1.08x faster                                              |
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.07x faster                                               |
| xml_etree_generate               | 68.1 ms                                                            | 63.8 ms: 1.07x faster                                              |
| richards                         | 34.7 ms                                                            | 32.5 ms: 1.07x faster                                              |
| gc_traversal                     | 3.36 ms                                                            | 3.19 ms: 1.05x faster                                              |
| logging_format                   | 6.00 us                                                            | 5.70 us: 1.05x faster                                              |
| base85_small                     | 4.66 ms                                                            | 4.46 ms: 1.05x faster                                              |
| generators                       | 24.2 ms                                                            | 23.2 ms: 1.04x faster                                              |
| thread_counter_optimized         | 18.3 ms                                                            | 17.7 ms: 1.04x faster                                              |
| spectral_norm                    | 64.1 ms                                                            | 62.0 ms: 1.03x faster                                              |
| scimark_monte_carlo              | 42.3 ms                                                            | 41.0 ms: 1.03x faster                                              |
| json_loads                       | 18.6 us                                                            | 18.1 us: 1.03x faster                                              |
| sqlalchemy_imperative            | 14.8 ms                                                            | 14.3 ms: 1.03x faster                                              |
| urlsafe_base64_small             | 340 us                                                             | 331 us: 1.03x faster                                               |
| base64_small                     | 227 us                                                             | 222 us: 1.03x faster                                               |
| regex_v8                         | 15.0 ms                                                            | 14.7 ms: 1.02x faster                                              |
| pickle_dict                      | 20.0 us                                                            | 19.6 us: 1.02x faster                                              |
| pidigits                         | 216 ms                                                             | 213 ms: 1.01x faster                                               |
| fastapi_http                     | 222 ms                                                             | 219 ms: 1.01x faster                                               |
| base85_large                     | 249 ms                                                             | 246 ms: 1.01x faster                                               |
| json                             | 3.46 ms                                                            | 3.42 ms: 1.01x faster                                              |
| pathlib                          | 12.7 ms                                                            | 12.6 ms: 1.01x faster                                              |
| xml_etree_iterparse              | 85.5 ms                                                            | 85.0 ms: 1.01x faster                                              |
| docutils                         | 1.98 sec                                                           | 1.99 sec: 1.01x slower                                             |
| sqlglot_v2_parse                 | 954 us                                                             | 965 us: 1.01x slower                                               |
| meteor_contest                   | 85.4 ms                                                            | 86.4 ms: 1.01x slower                                              |
| coverage                         | 54.5 ms                                                            | 55.2 ms: 1.01x slower                                              |
| raytrace                         | 201 ms                                                             | 204 ms: 1.01x slower                                               |
| decimal_pi                       | 209 ms                                                             | 213 ms: 1.02x slower                                               |
| decimal_factorial                | 174 ms                                                             | 177 ms: 1.02x slower                                               |
| thread_counter_naive             | 21.2 ms                                                            | 21.6 ms: 1.02x slower                                              |
| unpickle_list                    | 3.03 us                                                            | 3.09 us: 1.02x slower                                              |
| networkx_connected_components    | 425 ms                                                             | 433 ms: 1.02x slower                                               |
| comprehensions                   | 11.4 us                                                            | 11.6 us: 1.02x slower                                              |
| xml_etree_parse                  | 118 ms                                                             | 120 ms: 1.02x slower                                               |
| tomli_loads                      | 1.49 sec                                                           | 1.52 sec: 1.02x slower                                             |
| logging_silent                   | 59.2 ns                                                            | 60.6 ns: 1.02x slower                                              |
| deltablue                        | 2.76 ms                                                            | 2.83 ms: 1.02x slower                                              |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.24 ms: 1.03x slower                                              |
| logging_simple                   | 5.02 us                                                            | 5.15 us: 1.03x slower                                              |
| nqueens                          | 59.8 ms                                                            | 61.4 ms: 1.03x slower                                              |
| networkx_k_core                  | 2.05 sec                                                           | 2.11 sec: 1.03x slower                                             |
| mypy2                            | 780 ms                                                             | 803 ms: 1.03x slower                                               |
| telco                            | 5.39 ms                                                            | 5.58 ms: 1.04x slower                                              |
| typing_runtime_protocols         | 115 us                                                             | 119 us: 1.04x slower                                               |
| python_startup                   | 9.93 ms                                                            | 10.3 ms: 1.04x slower                                              |
| pyflate                          | 309 ms                                                             | 322 ms: 1.04x slower                                               |
| float                            | 51.2 ms                                                            | 53.4 ms: 1.04x slower                                              |
| sympy_str                        | 200 ms                                                             | 209 ms: 1.04x slower                                               |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 13.5 ms: 1.04x slower                                              |
| sympy_sum                        | 109 ms                                                             | 114 ms: 1.05x slower                                               |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 43.7 ms: 1.05x slower                                              |
| hexiom                           | 4.50 ms                                                            | 4.72 ms: 1.05x slower                                              |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.27 sec: 1.05x slower                                             |
| regex_dna                        | 147 ms                                                             | 155 ms: 1.05x slower                                               |
| sympy_expand                     | 344 ms                                                             | 363 ms: 1.06x slower                                               |
| noop                             | 19.2 ns                                                            | 20.3 ns: 1.06x slower                                              |
| xdsl_constant_fold               | 36.0 ms                                                            | 38.1 ms: 1.06x slower                                              |
| pycparser                        | 878 ms                                                             | 933 ms: 1.06x slower                                               |
| regex_compile                    | 97.0 ms                                                            | 103 ms: 1.06x slower                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 349 ms: 1.07x slower                                               |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 90.7 ms: 1.07x slower                                              |
| chaos                            | 42.9 ms                                                            | 45.9 ms: 1.07x slower                                              |
| base32_small                     | 5.71 ms                                                            | 6.11 ms: 1.07x slower                                              |
| base32_large                     | 289 ms                                                             | 310 ms: 1.07x slower                                               |
| chameleon                        | 10.3 ms                                                            | 11.1 ms: 1.08x slower                                              |
| django_template                  | 30.5 ms                                                            | 33.4 ms: 1.10x slower                                              |
| python_startup_no_site           | 6.52 ms                                                            | 7.29 ms: 1.12x slower                                              |
| pprint_safe_repr                 | 534 ms                                                             | 600 ms: 1.12x slower                                               |
| html5lib                         | 45.3 ms                                                            | 50.9 ms: 1.12x slower                                              |
| sympy_integrate                  | 15.1 ms                                                            | 17.1 ms: 1.13x slower                                              |
| thrift                           | 2.00 ms                                                            | 2.26 ms: 1.13x slower                                              |
| pprint_pformat                   | 1.10 sec                                                           | 1.24 sec: 1.13x slower                                             |
| pylint                           | 222 ms                                                             | 255 ms: 1.15x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 96.3 ms: 1.16x slower                                              |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 498 ms: 1.16x slower                                               |
| deepcopy_reduce                  | 2.02 us                                                            | 2.36 us: 1.17x slower                                              |
| genshi_text                      | 18.0 ms                                                            | 21.1 ms: 1.17x slower                                              |
| regex_effbot                     | 1.98 ms                                                            | 2.32 ms: 1.18x slower                                              |
| async_generators                 | 231 ms                                                             | 272 ms: 1.18x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 509 ms: 1.19x slower                                               |
| genshi_xml                       | 43.2 ms                                                            | 51.9 ms: 1.20x slower                                              |
| coroutines                       | 15.1 ms                                                            | 18.2 ms: 1.20x slower                                              |
| scimark_sor                      | 78.2 ms                                                            | 95.3 ms: 1.22x slower                                              |
| deepcopy_memo                    | 19.1 us                                                            | 23.4 us: 1.22x slower                                              |
| async_tree_eager_memoization     | 183 ms                                                             | 228 ms: 1.25x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 726 ms: 1.29x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 290 ms: 1.29x slower                                               |
| deepcopy                         | 198 us                                                             | 259 us: 1.31x slower                                               |
| scimark_lu                       | 74.7 ms                                                            | 99.8 ms: 1.34x slower                                              |
| async_tree_eager_io              | 568 ms                                                             | 758 ms: 1.34x slower                                               |
| async_tree_none                  | 233 ms                                                             | 313 ms: 1.34x slower                                               |
| async_tree_io                    | 549 ms                                                             | 749 ms: 1.36x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 393 ms: 1.38x slower                                               |
| go                               | 91.1 ms                                                            | 126 ms: 1.38x slower                                               |
| thread_pipeline_naive            | 34.9 ms                                                            | 48.5 ms: 1.39x slower                                              |
| thread_montecarlo_naive          | 14.3 ms                                                            | 19.9 ms: 1.40x slower                                              |
| async_tree_io_tg                 | 545 ms                                                             | 782 ms: 1.43x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 419 ms: 1.50x slower                                               |
| mdp                              | 971 ms                                                             | 2.08 sec: 2.14x slower                                             |
| unpack_sequence                  | 35.6 ns                                                            | 82.2 ns: 2.31x slower                                              |
| thread_memo_naive                | 12.4 ms                                                            | 38.0 ms: 3.07x slower                                              |
| base16_small                     | 265 us                                                             | 839 us: 3.17x slower                                               |
| base16_large                     | 6.35 ms                                                            | 42.6 ms: 6.71x slower                                              |
| Geometric mean                   | (ref)                                                              | 1.06x slower                                                       |

Benchmark hidden because not significant (6): asyncio_websockets, base64_large, networkx_shortest_path, asyncio_tcp_ssl, unpickle, tornado_http

- Geometric mean (including insignificant results): 1.054x slower

# HPT report

- Reliability score: 99.96% likely to be slow
- 90% likely to have a slowdown of 1.01x
- 95% likely to have a slowdown of 1.01x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 0.98x