# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a2
- machine: linux-x86_64
- commit hash: a625628
- commit date: 2025-11-18
- overall geometric mean: 1.008x slower
- HPT reliability: 98.54%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.01x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.2 ms: 1.09x slower                                                  |
| docutils       | 1.98 sec                                                           | 1.99 sec: 1.01x slower                                                 |
| html5lib       | 45.3 ms                                                            | 46.5 ms: 1.03x slower                                                  |
| tornado_http   | 101 ms                                                             | 99.2 ms: 1.02x faster                                                  |
| Geometric mean | (ref)                                                              | 1.02x slower                                                           |

Benchmark hidden because not significant (1): fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 565 ms                                                             | 482 ms: 1.17x faster                                                   |
| async_tree_eager_io              | 568 ms                                                             | 513 ms: 1.11x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 510 ms: 1.08x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 208 ms: 1.08x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.07x faster                                                   |
| async_tree_none                  | 233 ms                                                             | 217 ms: 1.07x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 509 ms: 1.07x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 401 ms: 1.07x faster                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 412 ms: 1.04x faster                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 178 ms: 1.03x faster                                                   |
| async_generators                 | 231 ms                                                             | 225 ms: 1.02x faster                                                   |
| async_tree_memoization           | 285 ms                                                             | 279 ms: 1.02x faster                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 274 ms: 1.02x faster                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 181 ms: 1.01x faster                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 379 ms: 1.01x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 333 ms: 1.02x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 85.0 ms: 1.02x slower                                                  |
| asyncio_websockets               | 305 ms                                                             | 314 ms: 1.03x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.04x faster                                                           |

Benchmark hidden because not significant (3): asyncio_tcp_ssl, async_tree_eager_memoization_tg, coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 20.2 ns: 1.05x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 172 ms: 1.01x faster                                                   |
| decimal_pi        | 209 ms                                                             | 207 ms: 1.01x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.01x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| quadtree_nbody | 654 ms                                                             | 630 ms: 1.04x faster                                                   |
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| nbody          | 74.2 ms                                                            | 76.9 ms: 1.04x slower                                                  |
| float          | 51.2 ms                                                            | 54.9 ms: 1.07x slower                                                  |
| Geometric mean | (ref)                                                              | 1.02x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_dna      | 147 ms                                                             | 146 ms: 1.01x faster                                                   |
| regex_compile  | 97.0 ms                                                            | 104 ms: 1.07x slower                                                   |
| Geometric mean | (ref)                                                              | 1.01x slower                                                           |

Benchmark hidden because not significant (2): regex_effbot, regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| json_dumps           | 7.52 ms                                                            | 6.58 ms: 1.14x faster                                                  |
| xml_etree_iterparse  | 85.5 ms                                                            | 77.2 ms: 1.11x faster                                                  |
| json_loads           | 18.6 us                                                            | 17.4 us: 1.07x faster                                                  |
| pickle_dict          | 20.0 us                                                            | 19.2 us: 1.04x faster                                                  |
| base16_large         | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| pickle_list          | 3.03 us                                                            | 2.92 us: 1.04x faster                                                  |
| unpickle             | 10.5 us                                                            | 10.4 us: 1.01x faster                                                  |
| xml_etree_parse      | 118 ms                                                             | 116 ms: 1.01x faster                                                   |
| pickle               | 8.04 us                                                            | 8.00 us: 1.01x faster                                                  |
| base64_large         | 5.70 ms                                                            | 5.75 ms: 1.01x slower                                                  |
| xml_etree_process    | 50.0 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| base64_small         | 227 us                                                             | 230 us: 1.01x slower                                                   |
| xml_etree_generate   | 68.1 ms                                                            | 69.0 ms: 1.01x slower                                                  |
| base16_small         | 265 us                                                             | 270 us: 1.02x slower                                                   |
| base32_large         | 289 ms                                                             | 295 ms: 1.02x slower                                                   |
| urlsafe_base64_small | 340 us                                                             | 350 us: 1.03x slower                                                   |
| base32_small         | 5.71 ms                                                            | 5.94 ms: 1.04x slower                                                  |
| pickle_pure_python   | 251 us                                                             | 263 us: 1.05x slower                                                   |
| base85_small         | 4.66 ms                                                            | 4.94 ms: 1.06x slower                                                  |
| unpickle_pure_python | 163 us                                                             | 174 us: 1.07x slower                                                   |
| base85_large         | 249 ms                                                             | 268 ms: 1.07x slower                                                   |
| tomli_loads          | 1.49 sec                                                           | 1.67 sec: 1.12x slower                                                 |
| ascii85_small        | 13.0 ms                                                            | 14.7 ms: 1.13x slower                                                  |
| ascii85_large        | 681 ms                                                             | 768 ms: 1.13x slower                                                   |
| Geometric mean       | (ref)                                                              | 1.01x slower                                                           |

Benchmark hidden because not significant (1): unpickle_list

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 9.60 ms: 1.03x faster                                                  |
| python_startup_no_site | 6.52 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| Geometric mean         | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 31.6 ms: 1.03x slower                                                  |
| genshi_text     | 18.0 ms                                                            | 19.2 ms: 1.06x slower                                                  |
| genshi_xml      | 43.2 ms                                                            | 46.4 ms: 1.07x slower                                                  |
| mako            | 8.69 ms                                                            | 9.41 ms: 1.08x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 10.9 ms: 1.13x faster                                                  |
| thread_mandelbrot_naive     | 207 ms                                                             | 189 ms: 1.10x faster                                                   |
| thread_mandelbrot_optimized | 205 ms                                                             | 189 ms: 1.08x faster                                                   |
| thread_montecarlo_optimized | 12.9 ms                                                            | 12.8 ms: 1.00x faster                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 14.6 ms: 1.03x slower                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 41.2 ms: 1.04x slower                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 42.2 ms: 1.04x slower                                                  |
| thread_pipeline_naive       | 34.9 ms                                                            | 36.6 ms: 1.05x slower                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 18.4 ms: 1.05x slower                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 27.3 ms: 1.06x slower                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 23.8 ms: 1.13x slower                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 21.1 ms: 1.15x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.02x slower                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20251118-centurion_clang22-x86_64-python-v3.15.0a2-3.15.0a2-a625628 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 565 ms                                                             | 482 ms: 1.17x faster                                                   |
| pathlib                          | 12.7 ms                                                            | 10.8 ms: 1.17x faster                                                  |
| json_dumps                       | 7.52 ms                                                            | 6.58 ms: 1.14x faster                                                  |
| thread_memo_naive                | 12.4 ms                                                            | 10.9 ms: 1.13x faster                                                  |
| xml_etree_iterparse              | 85.5 ms                                                            | 77.2 ms: 1.11x faster                                                  |
| async_tree_eager_io              | 568 ms                                                             | 513 ms: 1.11x faster                                                   |
| thread_mandelbrot_naive          | 207 ms                                                             | 189 ms: 1.10x faster                                                   |
| telco                            | 5.39 ms                                                            | 4.96 ms: 1.09x faster                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 189 ms: 1.08x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 510 ms: 1.08x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 208 ms: 1.08x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.07x faster                                                   |
| async_tree_none                  | 233 ms                                                             | 217 ms: 1.07x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 509 ms: 1.07x faster                                                   |
| json_loads                       | 18.6 us                                                            | 17.4 us: 1.07x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 401 ms: 1.07x faster                                                   |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.75 ms: 1.05x faster                                                  |
| pickle_dict                      | 20.0 us                                                            | 19.2 us: 1.04x faster                                                  |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 412 ms: 1.04x faster                                                   |
| base16_large                     | 6.35 ms                                                            | 6.11 ms: 1.04x faster                                                  |
| quadtree_nbody                   | 654 ms                                                             | 630 ms: 1.04x faster                                                   |
| pickle_list                      | 3.03 us                                                            | 2.92 us: 1.04x faster                                                  |
| python_startup                   | 9.93 ms                                                            | 9.60 ms: 1.03x faster                                                  |
| json                             | 3.46 ms                                                            | 3.36 ms: 1.03x faster                                                  |
| logging_format                   | 6.00 us                                                            | 5.83 us: 1.03x faster                                                  |
| async_tree_eager_memoization     | 183 ms                                                             | 178 ms: 1.03x faster                                                   |
| scimark_fft                      | 211 ms                                                             | 206 ms: 1.03x faster                                                   |
| async_generators                 | 231 ms                                                             | 225 ms: 1.02x faster                                                   |
| python_startup_no_site           | 6.52 ms                                                            | 6.37 ms: 1.02x faster                                                  |
| async_tree_memoization           | 285 ms                                                             | 279 ms: 1.02x faster                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 274 ms: 1.02x faster                                                   |
| tornado_http                     | 101 ms                                                             | 99.2 ms: 1.02x faster                                                  |
| generators                       | 24.2 ms                                                            | 23.8 ms: 1.02x faster                                                  |
| decimal_factorial                | 174 ms                                                             | 172 ms: 1.01x faster                                                   |
| regex_dna                        | 147 ms                                                             | 146 ms: 1.01x faster                                                   |
| meteor_contest                   | 85.4 ms                                                            | 84.4 ms: 1.01x faster                                                  |
| decimal_pi                       | 209 ms                                                             | 207 ms: 1.01x faster                                                   |
| unpickle                         | 10.5 us                                                            | 10.4 us: 1.01x faster                                                  |
| xml_etree_parse                  | 118 ms                                                             | 116 ms: 1.01x faster                                                   |
| gc_traversal                     | 3.36 ms                                                            | 3.34 ms: 1.01x faster                                                  |
| async_tree_eager_tg              | 182 ms                                                             | 181 ms: 1.01x faster                                                   |
| pickle                           | 8.04 us                                                            | 8.00 us: 1.01x faster                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 12.8 ms: 1.00x faster                                                  |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 42.0 ms: 1.01x slower                                                  |
| crypto_pyaes                     | 56.7 ms                                                            | 57.0 ms: 1.01x slower                                                  |
| docutils                         | 1.98 sec                                                           | 1.99 sec: 1.01x slower                                                 |
| mdp                              | 971 ms                                                             | 978 ms: 1.01x slower                                                   |
| base64_large                     | 5.70 ms                                                            | 5.75 ms: 1.01x slower                                                  |
| xml_etree_process                | 50.0 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.14 sec: 1.01x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 379 ms: 1.01x slower                                                   |
| base64_small                     | 227 us                                                             | 230 us: 1.01x slower                                                   |
| coverage                         | 54.5 ms                                                            | 55.1 ms: 1.01x slower                                                  |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 85.9 ms: 1.01x slower                                                  |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.23 ms: 1.01x slower                                                  |
| xml_etree_generate               | 68.1 ms                                                            | 69.0 ms: 1.01x slower                                                  |
| raytrace                         | 201 ms                                                             | 204 ms: 1.01x slower                                                   |
| typing_runtime_protocols         | 115 us                                                             | 117 us: 1.02x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 333 ms: 1.02x slower                                                   |
| richards                         | 34.7 ms                                                            | 35.3 ms: 1.02x slower                                                  |
| deepcopy_memo                    | 19.1 us                                                            | 19.5 us: 1.02x slower                                                  |
| xdsl_constant_fold               | 36.0 ms                                                            | 36.6 ms: 1.02x slower                                                  |
| base16_small                     | 265 us                                                             | 270 us: 1.02x slower                                                   |
| sympy_integrate                  | 15.1 ms                                                            | 15.4 ms: 1.02x slower                                                  |
| base32_large                     | 289 ms                                                             | 295 ms: 1.02x slower                                                   |
| thrift                           | 2.00 ms                                                            | 2.04 ms: 1.02x slower                                                  |
| scimark_lu                       | 74.7 ms                                                            | 76.4 ms: 1.02x slower                                                  |
| sympy_sum                        | 109 ms                                                             | 111 ms: 1.02x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 85.0 ms: 1.02x slower                                                  |
| html5lib                         | 45.3 ms                                                            | 46.5 ms: 1.03x slower                                                  |
| deepcopy                         | 198 us                                                             | 203 us: 1.03x slower                                                   |
| thread_montecarlo_naive          | 14.3 ms                                                            | 14.6 ms: 1.03x slower                                                  |
| asyncio_websockets               | 305 ms                                                             | 314 ms: 1.03x slower                                                   |
| urlsafe_base64_small             | 340 us                                                             | 350 us: 1.03x slower                                                   |
| chaos                            | 42.9 ms                                                            | 44.2 ms: 1.03x slower                                                  |
| logging_simple                   | 5.02 us                                                            | 5.17 us: 1.03x slower                                                  |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.3 ms: 1.03x slower                                                  |
| sympy_str                        | 200 ms                                                             | 207 ms: 1.03x slower                                                   |
| django_template                  | 30.5 ms                                                            | 31.6 ms: 1.03x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 356 ms: 1.04x slower                                                   |
| nbody                            | 74.2 ms                                                            | 76.9 ms: 1.04x slower                                                  |
| sqlglot_v2_parse                 | 954 us                                                             | 991 us: 1.04x slower                                                   |
| nqueens                          | 59.8 ms                                                            | 62.2 ms: 1.04x slower                                                  |
| argparse_subparsers              | 687 us                                                             | 714 us: 1.04x slower                                                   |
| base32_small                     | 5.71 ms                                                            | 5.94 ms: 1.04x slower                                                  |
| thread_accumulate_optimized      | 39.5 ms                                                            | 41.2 ms: 1.04x slower                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 42.2 ms: 1.04x slower                                                  |
| pprint_pformat                   | 1.10 sec                                                           | 1.15 sec: 1.05x slower                                                 |
| hexiom                           | 4.50 ms                                                            | 4.71 ms: 1.05x slower                                                  |
| pickle_pure_python               | 251 us                                                             | 263 us: 1.05x slower                                                   |
| thread_pipeline_naive            | 34.9 ms                                                            | 36.6 ms: 1.05x slower                                                  |
| pyflate                          | 309 ms                                                             | 324 ms: 1.05x slower                                                   |
| thread_memo_optimized            | 17.5 ms                                                            | 18.4 ms: 1.05x slower                                                  |
| pprint_safe_repr                 | 534 ms                                                             | 561 ms: 1.05x slower                                                   |
| deltablue                        | 2.76 ms                                                            | 2.90 ms: 1.05x slower                                                  |
| noop                             | 19.2 ns                                                            | 20.2 ns: 1.05x slower                                                  |
| fannkuch                         | 246 ms                                                             | 260 ms: 1.05x slower                                                   |
| deepcopy_reduce                  | 2.02 us                                                            | 2.13 us: 1.05x slower                                                  |
| scimark_monte_carlo              | 42.3 ms                                                            | 44.7 ms: 1.06x slower                                                  |
| pycparser                        | 878 ms                                                             | 930 ms: 1.06x slower                                                   |
| base85_small                     | 4.66 ms                                                            | 4.94 ms: 1.06x slower                                                  |
| go                               | 91.1 ms                                                            | 96.5 ms: 1.06x slower                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 27.3 ms: 1.06x slower                                                  |
| genshi_text                      | 18.0 ms                                                            | 19.2 ms: 1.06x slower                                                  |
| argparse_many_optionals          | 34.5 ms                                                            | 36.8 ms: 1.07x slower                                                  |
| unpickle_pure_python             | 163 us                                                             | 174 us: 1.07x slower                                                   |
| genshi_xml                       | 43.2 ms                                                            | 46.4 ms: 1.07x slower                                                  |
| float                            | 51.2 ms                                                            | 54.9 ms: 1.07x slower                                                  |
| regex_compile                    | 97.0 ms                                                            | 104 ms: 1.07x slower                                                   |
| base85_large                     | 249 ms                                                             | 268 ms: 1.07x slower                                                   |
| mako                             | 8.69 ms                                                            | 9.41 ms: 1.08x slower                                                  |
| chameleon                        | 10.3 ms                                                            | 11.2 ms: 1.09x slower                                                  |
| logging_silent                   | 59.2 ns                                                            | 65.5 ns: 1.11x slower                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.67 sec: 1.12x slower                                                 |
| thread_counter_naive             | 21.2 ms                                                            | 23.8 ms: 1.13x slower                                                  |
| ascii85_small                    | 13.0 ms                                                            | 14.7 ms: 1.13x slower                                                  |
| ascii85_large                    | 681 ms                                                             | 768 ms: 1.13x slower                                                   |
| thread_counter_optimized         | 18.3 ms                                                            | 21.1 ms: 1.15x slower                                                  |
| scimark_sor                      | 78.2 ms                                                            | 91.1 ms: 1.16x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.01x slower                                                           |

Benchmark hidden because not significant (14): pylint, spectral_norm, unpickle_list, regex_effbot, comprehensions, asyncio_tcp_ssl, richards_super, async_tree_eager_memoization_tg, create_gc_cycles, fastapi_http, mypy2, regex_v8, coroutines, unpack_sequence
Ignored benchmarks (3) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: networkx_connected_components, networkx_k_core, networkx_shortest_path

- Geometric mean (including insignificant results): 1.008x slower

# HPT report

- Reliability score: 98.54% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.01x