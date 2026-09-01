# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.018x slower
- HPT reliability: 99.60%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.00x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.0 ms: 1.07x slower                                              |
| html5lib       | 45.3 ms                                                            | 47.9 ms: 1.06x slower                                              |
| tornado_http   | 101 ms                                                             | 103 ms: 1.02x slower                                               |
| Geometric mean | (ref)                                                              | 1.03x slower                                                       |

Benchmark hidden because not significant (2): docutils, fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.07x faster                                               |
| coroutines                       | 15.1 ms                                                            | 15.7 ms: 1.04x slower                                              |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 345 ms: 1.05x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 88.6 ms: 1.07x slower                                              |
| asyncio_websockets               | 305 ms                                                             | 328 ms: 1.07x slower                                               |
| async_tree_eager_memoization     | 183 ms                                                             | 201 ms: 1.10x slower                                               |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 478 ms: 1.11x slower                                               |
| async_generators                 | 231 ms                                                             | 259 ms: 1.12x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 423 ms: 1.13x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 483 ms: 1.13x slower                                               |
| async_tree_eager_tg              | 182 ms                                                             | 211 ms: 1.16x slower                                               |
| async_tree_none                  | 233 ms                                                             | 272 ms: 1.17x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 340 ms: 1.19x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 678 ms: 1.19x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 686 ms: 1.21x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 272 ms: 1.21x slower                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 288 ms: 1.22x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 349 ms: 1.25x slower                                               |
| async_tree_io                    | 549 ms                                                             | 705 ms: 1.28x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 710 ms: 1.30x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.14x slower                                                       |

Benchmark hidden because not significant (1): asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 17.6 ns: 1.09x faster                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_pi     | 209 ms                                                             | 209 ms: 1.00x faster                                               |
| Geometric mean | (ref)                                                              | 1.00x faster                                                       |

Benchmark hidden because not significant (1): decimal_factorial

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 51.2 ms                                                            | 43.9 ms: 1.17x faster                                              |
| quadtree_nbody | 654 ms                                                             | 592 ms: 1.10x faster                                               |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x faster                                               |
| nbody          | 74.2 ms                                                            | 84.0 ms: 1.13x slower                                              |
| Geometric mean | (ref)                                                              | 1.03x faster                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_dna      | 147 ms                                                             | 146 ms: 1.01x faster                                               |
| regex_v8       | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| regex_compile  | 97.0 ms                                                            | 99.9 ms: 1.03x slower                                              |
| regex_effbot   | 1.98 ms                                                            | 2.17 ms: 1.10x slower                                              |
| Geometric mean | (ref)                                                              | 1.03x slower                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| unpickle_pure_python | 163 us                                                             | 137 us: 1.19x faster                                               |
| xml_etree_process    | 50.0 ms                                                            | 45.0 ms: 1.11x faster                                              |
| ascii85_large        | 681 ms                                                             | 617 ms: 1.10x faster                                               |
| xml_etree_generate   | 68.1 ms                                                            | 61.8 ms: 1.10x faster                                              |
| ascii85_small        | 13.0 ms                                                            | 11.9 ms: 1.10x faster                                              |
| base85_large         | 249 ms                                                             | 238 ms: 1.05x faster                                               |
| xml_etree_iterparse  | 85.5 ms                                                            | 82.2 ms: 1.04x faster                                              |
| base85_small         | 4.66 ms                                                            | 4.49 ms: 1.04x faster                                              |
| tomli_loads          | 1.49 sec                                                           | 1.44 sec: 1.04x faster                                             |
| pickle_dict          | 20.0 us                                                            | 19.5 us: 1.02x faster                                              |
| urlsafe_base64_small | 340 us                                                             | 335 us: 1.02x faster                                               |
| base16_large         | 6.35 ms                                                            | 6.26 ms: 1.01x faster                                              |
| base64_large         | 5.70 ms                                                            | 5.68 ms: 1.00x faster                                              |
| base32_large         | 289 ms                                                             | 293 ms: 1.01x slower                                               |
| pickle_pure_python   | 251 us                                                             | 258 us: 1.03x slower                                               |
| json_loads           | 18.6 us                                                            | 19.3 us: 1.03x slower                                              |
| json_dumps           | 7.52 ms                                                            | 7.83 ms: 1.04x slower                                              |
| base32_small         | 5.71 ms                                                            | 5.96 ms: 1.04x slower                                              |
| xml_etree_parse      | 118 ms                                                             | 124 ms: 1.05x slower                                               |
| pickle_list          | 3.03 us                                                            | 3.19 us: 1.05x slower                                              |
| Geometric mean       | (ref)                                                              | 1.02x faster                                                       |

Benchmark hidden because not significant (5): unpickle_list, pickle, base64_small, base16_small, unpickle

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup_no_site | 6.52 ms                                                            | 6.56 ms: 1.01x slower                                              |
| python_startup         | 9.93 ms                                                            | 10.00 ms: 1.01x slower                                             |
| Geometric mean         | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| mako            | 8.69 ms                                                            | 7.44 ms: 1.17x faster                                              |
| django_template | 30.5 ms                                                            | 31.7 ms: 1.04x slower                                              |
| genshi_xml      | 43.2 ms                                                            | 45.1 ms: 1.04x slower                                              |
| genshi_text     | 18.0 ms                                                            | 18.9 ms: 1.05x slower                                              |
| Geometric mean  | (ref)                                                              | 1.01x faster                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.8 ms                                                            | 23.1 ms: 1.11x faster                                              |
| thread_memo_naive           | 12.4 ms                                                            | 11.2 ms: 1.11x faster                                              |
| thread_accumulate_optimized | 39.5 ms                                                            | 35.9 ms: 1.10x faster                                              |
| thread_accumulate_naive     | 40.4 ms                                                            | 36.8 ms: 1.10x faster                                              |
| thread_memo_optimized       | 17.5 ms                                                            | 16.2 ms: 1.08x faster                                              |
| thread_pipeline_naive       | 34.9 ms                                                            | 33.6 ms: 1.04x faster                                              |
| thread_counter_optimized    | 18.3 ms                                                            | 17.7 ms: 1.03x faster                                              |
| thread_mandelbrot_naive     | 207 ms                                                             | 202 ms: 1.02x faster                                               |
| thread_counter_naive        | 21.2 ms                                                            | 20.8 ms: 1.02x faster                                              |
| thread_mandelbrot_optimized | 205 ms                                                             | 204 ms: 1.01x faster                                               |
| thread_montecarlo_optimized | 12.9 ms                                                            | 14.4 ms: 1.12x slower                                              |
| thread_montecarlo_naive     | 14.3 ms                                                            | 18.5 ms: 1.29x slower                                              |
| Geometric mean              | (ref)                                                              | 1.02x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| argparse_many_optionals          | 34.5 ms                                                            | 8.38 ms: 4.12x faster                                              |
| argparse_subparsers              | 687 us                                                             | 534 us: 1.29x faster                                               |
| deltablue                        | 2.76 ms                                                            | 2.17 ms: 1.27x faster                                              |
| scimark_fft                      | 211 ms                                                             | 177 ms: 1.19x faster                                               |
| unpickle_pure_python             | 163 us                                                             | 137 us: 1.19x faster                                               |
| richards                         | 34.7 ms                                                            | 29.4 ms: 1.18x faster                                              |
| mako                             | 8.69 ms                                                            | 7.44 ms: 1.17x faster                                              |
| float                            | 51.2 ms                                                            | 43.9 ms: 1.17x faster                                              |
| richards_super                   | 40.3 ms                                                            | 34.8 ms: 1.16x faster                                              |
| thread_pipeline_optimized        | 25.8 ms                                                            | 23.1 ms: 1.11x faster                                              |
| xml_etree_process                | 50.0 ms                                                            | 45.0 ms: 1.11x faster                                              |
| thread_memo_naive                | 12.4 ms                                                            | 11.2 ms: 1.11x faster                                              |
| quadtree_nbody                   | 654 ms                                                             | 592 ms: 1.10x faster                                               |
| ascii85_large                    | 681 ms                                                             | 617 ms: 1.10x faster                                               |
| xml_etree_generate               | 68.1 ms                                                            | 61.8 ms: 1.10x faster                                              |
| ascii85_small                    | 13.0 ms                                                            | 11.9 ms: 1.10x faster                                              |
| thread_accumulate_optimized      | 39.5 ms                                                            | 35.9 ms: 1.10x faster                                              |
| thread_accumulate_naive          | 40.4 ms                                                            | 36.8 ms: 1.10x faster                                              |
| noop                             | 19.2 ns                                                            | 17.6 ns: 1.09x faster                                              |
| spectral_norm                    | 64.1 ms                                                            | 59.2 ms: 1.08x faster                                              |
| thread_memo_optimized            | 17.5 ms                                                            | 16.2 ms: 1.08x faster                                              |
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.07x faster                                               |
| create_gc_cycles                 | 2.02 ms                                                            | 1.90 ms: 1.06x faster                                              |
| base85_large                     | 249 ms                                                             | 238 ms: 1.05x faster                                               |
| xml_etree_iterparse              | 85.5 ms                                                            | 82.2 ms: 1.04x faster                                              |
| thread_pipeline_naive            | 34.9 ms                                                            | 33.6 ms: 1.04x faster                                              |
| base85_small                     | 4.66 ms                                                            | 4.49 ms: 1.04x faster                                              |
| tomli_loads                      | 1.49 sec                                                           | 1.44 sec: 1.04x faster                                             |
| thread_counter_optimized         | 18.3 ms                                                            | 17.7 ms: 1.03x faster                                              |
| logging_format                   | 6.00 us                                                            | 5.80 us: 1.03x faster                                              |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.80 ms: 1.03x faster                                              |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.03 sec: 1.02x faster                                             |
| pickle_dict                      | 20.0 us                                                            | 19.5 us: 1.02x faster                                              |
| generators                       | 24.2 ms                                                            | 23.6 ms: 1.02x faster                                              |
| thread_mandelbrot_naive          | 207 ms                                                             | 202 ms: 1.02x faster                                               |
| scimark_sor                      | 78.2 ms                                                            | 76.8 ms: 1.02x faster                                              |
| gc_traversal                     | 3.36 ms                                                            | 3.30 ms: 1.02x faster                                              |
| thread_counter_naive             | 21.2 ms                                                            | 20.8 ms: 1.02x faster                                              |
| urlsafe_base64_small             | 340 us                                                             | 335 us: 1.02x faster                                               |
| base16_large                     | 6.35 ms                                                            | 6.26 ms: 1.01x faster                                              |
| regex_dna                        | 147 ms                                                             | 146 ms: 1.01x faster                                               |
| pyflate                          | 309 ms                                                             | 307 ms: 1.01x faster                                               |
| thread_mandelbrot_optimized      | 205 ms                                                             | 204 ms: 1.01x faster                                               |
| pathlib                          | 12.7 ms                                                            | 12.6 ms: 1.00x faster                                              |
| decimal_pi                       | 209 ms                                                             | 209 ms: 1.00x faster                                               |
| base64_large                     | 5.70 ms                                                            | 5.68 ms: 1.00x faster                                              |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x faster                                               |
| python_startup_no_site           | 6.52 ms                                                            | 6.56 ms: 1.01x slower                                              |
| python_startup                   | 9.93 ms                                                            | 10.00 ms: 1.01x slower                                             |
| networkx_shortest_path           | 447 ms                                                             | 451 ms: 1.01x slower                                               |
| base32_large                     | 289 ms                                                             | 293 ms: 1.01x slower                                               |
| logging_silent                   | 59.2 ns                                                            | 60.0 ns: 1.01x slower                                              |
| nqueens                          | 59.8 ms                                                            | 60.8 ms: 1.02x slower                                              |
| meteor_contest                   | 85.4 ms                                                            | 86.8 ms: 1.02x slower                                              |
| telco                            | 5.39 ms                                                            | 5.49 ms: 1.02x slower                                              |
| deepcopy_memo                    | 19.1 us                                                            | 19.5 us: 1.02x slower                                              |
| mdp                              | 971 ms                                                             | 991 ms: 1.02x slower                                               |
| networkx_connected_components    | 425 ms                                                             | 434 ms: 1.02x slower                                               |
| tornado_http                     | 101 ms                                                             | 103 ms: 1.02x slower                                               |
| crypto_pyaes                     | 56.7 ms                                                            | 58.0 ms: 1.02x slower                                              |
| deepcopy_reduce                  | 2.02 us                                                            | 2.07 us: 1.03x slower                                              |
| regex_v8                         | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 43.0 ms: 1.03x slower                                              |
| pickle_pure_python               | 251 us                                                             | 258 us: 1.03x slower                                               |
| typing_runtime_protocols         | 115 us                                                             | 118 us: 1.03x slower                                               |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 87.4 ms: 1.03x slower                                              |
| regex_compile                    | 97.0 ms                                                            | 99.9 ms: 1.03x slower                                              |
| json                             | 3.46 ms                                                            | 3.57 ms: 1.03x slower                                              |
| json_loads                       | 18.6 us                                                            | 19.3 us: 1.03x slower                                              |
| sympy_sum                        | 109 ms                                                             | 113 ms: 1.04x slower                                               |
| raytrace                         | 201 ms                                                             | 208 ms: 1.04x slower                                               |
| logging_simple                   | 5.02 us                                                            | 5.21 us: 1.04x slower                                              |
| django_template                  | 30.5 ms                                                            | 31.7 ms: 1.04x slower                                              |
| fannkuch                         | 246 ms                                                             | 256 ms: 1.04x slower                                               |
| coroutines                       | 15.1 ms                                                            | 15.7 ms: 1.04x slower                                              |
| json_dumps                       | 7.52 ms                                                            | 7.83 ms: 1.04x slower                                              |
| genshi_xml                       | 43.2 ms                                                            | 45.1 ms: 1.04x slower                                              |
| sympy_expand                     | 344 ms                                                             | 359 ms: 1.04x slower                                               |
| base32_small                     | 5.71 ms                                                            | 5.96 ms: 1.04x slower                                              |
| sympy_str                        | 200 ms                                                             | 209 ms: 1.05x slower                                               |
| deepcopy                         | 198 us                                                             | 207 us: 1.05x slower                                               |
| genshi_text                      | 18.0 ms                                                            | 18.9 ms: 1.05x slower                                              |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.27 ms: 1.05x slower                                              |
| sympy_integrate                  | 15.1 ms                                                            | 15.9 ms: 1.05x slower                                              |
| xml_etree_parse                  | 118 ms                                                             | 124 ms: 1.05x slower                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 345 ms: 1.05x slower                                               |
| pickle_list                      | 3.03 us                                                            | 3.19 us: 1.05x slower                                              |
| thrift                           | 2.00 ms                                                            | 2.11 ms: 1.05x slower                                              |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.6 ms: 1.06x slower                                              |
| html5lib                         | 45.3 ms                                                            | 47.9 ms: 1.06x slower                                              |
| networkx_k_core                  | 2.05 sec                                                           | 2.18 sec: 1.06x slower                                             |
| sqlglot_v2_parse                 | 954 us                                                             | 1.01 ms: 1.06x slower                                              |
| comprehensions                   | 11.4 us                                                            | 12.2 us: 1.07x slower                                              |
| async_tree_eager                 | 83.0 ms                                                            | 88.6 ms: 1.07x slower                                              |
| xdsl_constant_fold               | 36.0 ms                                                            | 38.4 ms: 1.07x slower                                              |
| chameleon                        | 10.3 ms                                                            | 11.0 ms: 1.07x slower                                              |
| pylint                           | 222 ms                                                             | 237 ms: 1.07x slower                                               |
| hexiom                           | 4.50 ms                                                            | 4.81 ms: 1.07x slower                                              |
| asyncio_websockets               | 305 ms                                                             | 328 ms: 1.07x slower                                               |
| regex_effbot                     | 1.98 ms                                                            | 2.17 ms: 1.10x slower                                              |
| async_tree_eager_memoization     | 183 ms                                                             | 201 ms: 1.10x slower                                               |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 478 ms: 1.11x slower                                               |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 14.4 ms: 1.12x slower                                              |
| async_generators                 | 231 ms                                                             | 259 ms: 1.12x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 423 ms: 1.13x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 483 ms: 1.13x slower                                               |
| nbody                            | 74.2 ms                                                            | 84.0 ms: 1.13x slower                                              |
| pycparser                        | 878 ms                                                             | 997 ms: 1.14x slower                                               |
| go                               | 91.1 ms                                                            | 105 ms: 1.15x slower                                               |
| async_tree_eager_tg              | 182 ms                                                             | 211 ms: 1.16x slower                                               |
| async_tree_none                  | 233 ms                                                             | 272 ms: 1.17x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 340 ms: 1.19x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 678 ms: 1.19x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 686 ms: 1.21x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 272 ms: 1.21x slower                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 288 ms: 1.22x slower                                               |
| scimark_monte_carlo              | 42.3 ms                                                            | 52.3 ms: 1.23x slower                                              |
| pprint_safe_repr                 | 534 ms                                                             | 667 ms: 1.25x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 349 ms: 1.25x slower                                               |
| pprint_pformat                   | 1.10 sec                                                           | 1.39 sec: 1.26x slower                                             |
| async_tree_io                    | 549 ms                                                             | 705 ms: 1.28x slower                                               |
| thread_montecarlo_naive          | 14.3 ms                                                            | 18.5 ms: 1.29x slower                                              |
| async_tree_io_tg                 | 545 ms                                                             | 710 ms: 1.30x slower                                               |
| mypy2                            | 780 ms                                                             | 1.09 sec: 1.40x slower                                             |
| unpack_sequence                  | 35.6 ns                                                            | 107 ns: 3.00x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.02x slower                                                       |

Benchmark hidden because not significant (12): fastapi_http, unpickle_list, docutils, chaos, asyncio_tcp_ssl, coverage, pickle, base64_small, decimal_factorial, scimark_lu, base16_small, unpickle

- Geometric mean (including insignificant results): 1.018x slower

# HPT report

- Reliability score: 99.60% likely to be slow
- 90% likely to have a slowdown of 1.01x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.00x