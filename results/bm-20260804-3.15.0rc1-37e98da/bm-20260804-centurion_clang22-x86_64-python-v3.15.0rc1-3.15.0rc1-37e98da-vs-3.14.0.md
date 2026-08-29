# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.204x faster
- HPT reliability: 52.10%
- HPT 99th percentile: 1.00x faster
- Memory change: 0.95x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 10.6 ms: 1.03x slower                                                    |
| docutils       | 1.98 sec                                                           | 1.88 sec: 1.05x faster                                                   |
| fastapi_http   | 222 ms                                                             | 221 ms: 1.00x faster                                                     |
| html5lib       | 45.3 ms                                                            | 47.9 ms: 1.06x slower                                                    |
| tornado_http   | 101 ms                                                             | 98.7 ms: 1.02x faster                                                    |
| Geometric mean | (ref)                                                              | 1.00x slower                                                             |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 287 ms: 1.13x faster                                                     |
| async_tree_eager                 | 83.0 ms                                                            | 77.9 ms: 1.07x faster                                                    |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                   |
| async_generators                 | 231 ms                                                             | 228 ms: 1.01x faster                                                     |
| asyncio_websockets               | 305 ms                                                             | 310 ms: 1.02x slower                                                     |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 334 ms: 1.02x slower                                                     |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 467 ms: 1.09x slower                                                     |
| async_tree_none                  | 233 ms                                                             | 255 ms: 1.09x slower                                                     |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 416 ms: 1.11x slower                                                     |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 480 ms: 1.12x slower                                                     |
| async_tree_eager_tg              | 182 ms                                                             | 205 ms: 1.13x slower                                                     |
| async_tree_eager_io              | 568 ms                                                             | 644 ms: 1.13x slower                                                     |
| async_tree_none_tg               | 224 ms                                                             | 260 ms: 1.16x slower                                                     |
| async_tree_memoization_tg        | 279 ms                                                             | 327 ms: 1.17x slower                                                     |
| async_tree_io                    | 549 ms                                                             | 648 ms: 1.18x slower                                                     |
| async_tree_memoization           | 285 ms                                                             | 337 ms: 1.18x slower                                                     |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 283 ms: 1.20x slower                                                     |
| async_tree_eager_io_tg           | 565 ms                                                             | 680 ms: 1.20x slower                                                     |
| async_tree_io_tg                 | 545 ms                                                             | 679 ms: 1.25x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.08x slower                                                             |

Benchmark hidden because not significant (2): async_tree_eager_memoization, coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 18.1 ns: 1.06x faster                                                    |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 177 ms: 1.01x slower                                                     |
| decimal_pi        | 209 ms                                                             | 212 ms: 1.02x slower                                                     |
| Geometric mean    | (ref)                                                              | 1.01x slower                                                             |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| nbody          | 74.2 ms                                                            | 68.7 ms: 1.08x faster                                                    |
| quadtree_nbody | 654 ms                                                             | 645 ms: 1.01x faster                                                     |
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                     |
| float          | 51.2 ms                                                            | 53.8 ms: 1.05x slower                                                    |
| Geometric mean | (ref)                                                              | 1.01x faster                                                             |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| regex_compile  | 97.0 ms                                                            | 99.1 ms: 1.02x slower                                                    |
| regex_dna      | 147 ms                                                             | 152 ms: 1.03x slower                                                     |
| regex_v8       | 15.0 ms                                                            | 16.2 ms: 1.08x slower                                                    |
| regex_effbot   | 1.98 ms                                                            | 2.23 ms: 1.13x slower                                                    |
| Geometric mean | (ref)                                                              | 1.07x slower                                                             |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large         | 289 ms                                                             | 1.90 ms: 152.51x faster                                                  |
| ascii85_large        | 681 ms                                                             | 13.8 ms: 49.41x faster                                                   |
| base85_large         | 249 ms                                                             | 5.13 ms: 48.57x faster                                                   |
| base32_small         | 5.71 ms                                                            | 203 us: 28.06x faster                                                    |
| ascii85_small        | 13.0 ms                                                            | 522 us: 24.97x faster                                                    |
| base85_small         | 4.66 ms                                                            | 198 us: 23.60x faster                                                    |
| base64_large         | 5.70 ms                                                            | 1.59 ms: 3.58x faster                                                    |
| urlsafe_base64_small | 340 us                                                             | 246 us: 1.38x faster                                                     |
| json_dumps           | 7.52 ms                                                            | 6.36 ms: 1.18x faster                                                    |
| tomli_loads          | 1.49 sec                                                           | 1.43 sec: 1.05x faster                                                   |
| json_loads           | 18.6 us                                                            | 18.1 us: 1.03x faster                                                    |
| pickle_dict          | 20.0 us                                                            | 19.5 us: 1.03x faster                                                    |
| xml_etree_iterparse  | 85.5 ms                                                            | 83.4 ms: 1.03x faster                                                    |
| unpickle_list        | 3.03 us                                                            | 2.96 us: 1.02x faster                                                    |
| xml_etree_process    | 50.0 ms                                                            | 49.1 ms: 1.02x faster                                                    |
| unpickle             | 10.5 us                                                            | 10.6 us: 1.01x slower                                                    |
| base64_small         | 227 us                                                             | 230 us: 1.01x slower                                                     |
| pickle_pure_python   | 251 us                                                             | 256 us: 1.02x slower                                                     |
| unpickle_pure_python | 163 us                                                             | 166 us: 1.02x slower                                                     |
| pickle               | 8.04 us                                                            | 8.25 us: 1.03x slower                                                    |
| xml_etree_parse      | 118 ms                                                             | 125 ms: 1.06x slower                                                     |
| pickle_list          | 3.03 us                                                            | 3.26 us: 1.08x slower                                                    |
| base16_large         | 6.35 ms                                                            | 7.57 ms: 1.19x slower                                                    |
| base16_small         | 265 us                                                             | 355 us: 1.34x slower                                                     |
| Geometric mean       | (ref)                                                              | 2.59x faster                                                             |

Benchmark hidden because not significant (1): xml_etree_generate

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| python_startup_no_site | 6.52 ms                                                            | 6.00 ms: 1.09x faster                                                    |
| python_startup         | 9.93 ms                                                            | 9.64 ms: 1.03x faster                                                    |
| Geometric mean         | (ref)                                                              | 1.06x faster                                                             |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 30.7 ms: 1.01x slower                                                    |
| mako            | 8.69 ms                                                            | 9.25 ms: 1.06x slower                                                    |
| Geometric mean  | (ref)                                                              | 1.04x slower                                                             |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| thread_memo_naive           | 12.4 ms                                                            | 10.1 ms: 1.23x faster                                                    |
| thread_mandelbrot_optimized | 205 ms                                                             | 193 ms: 1.06x faster                                                     |
| thread_mandelbrot_naive     | 207 ms                                                             | 195 ms: 1.06x faster                                                     |
| thread_montecarlo_optimized | 12.9 ms                                                            | 12.2 ms: 1.05x faster                                                    |
| thread_montecarlo_naive     | 14.3 ms                                                            | 13.8 ms: 1.04x faster                                                    |
| thread_pipeline_naive       | 34.9 ms                                                            | 36.2 ms: 1.04x slower                                                    |
| thread_memo_optimized       | 17.5 ms                                                            | 18.6 ms: 1.06x slower                                                    |
| thread_accumulate_naive     | 40.4 ms                                                            | 43.6 ms: 1.08x slower                                                    |
| thread_accumulate_optimized | 39.5 ms                                                            | 42.9 ms: 1.09x slower                                                    |
| thread_pipeline_optimized   | 25.8 ms                                                            | 28.2 ms: 1.09x slower                                                    |
| thread_counter_naive        | 21.2 ms                                                            | 24.0 ms: 1.13x slower                                                    |
| thread_counter_optimized    | 18.3 ms                                                            | 21.7 ms: 1.19x slower                                                    |
| Geometric mean              | (ref)                                                              | 1.02x slower                                                             |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large                     | 289 ms                                                             | 1.90 ms: 152.51x faster                                                  |
| ascii85_large                    | 681 ms                                                             | 13.8 ms: 49.41x faster                                                   |
| base85_large                     | 249 ms                                                             | 5.13 ms: 48.57x faster                                                   |
| base32_small                     | 5.71 ms                                                            | 203 us: 28.06x faster                                                    |
| ascii85_small                    | 13.0 ms                                                            | 522 us: 24.97x faster                                                    |
| base85_small                     | 4.66 ms                                                            | 198 us: 23.60x faster                                                    |
| argparse_many_optionals          | 34.5 ms                                                            | 8.18 ms: 4.22x faster                                                    |
| base64_large                     | 5.70 ms                                                            | 1.59 ms: 3.58x faster                                                    |
| pylint                           | 222 ms                                                             | 101 ms: 2.19x faster                                                     |
| argparse_subparsers              | 687 us                                                             | 458 us: 1.50x faster                                                     |
| urlsafe_base64_small             | 340 us                                                             | 246 us: 1.38x faster                                                     |
| thread_memo_naive                | 12.4 ms                                                            | 10.1 ms: 1.23x faster                                                    |
| create_gc_cycles                 | 2.02 ms                                                            | 1.69 ms: 1.19x faster                                                    |
| json_dumps                       | 7.52 ms                                                            | 6.36 ms: 1.18x faster                                                    |
| pathlib                          | 12.7 ms                                                            | 10.7 ms: 1.18x faster                                                    |
| asyncio_tcp                      | 324 ms                                                             | 287 ms: 1.13x faster                                                     |
| gc_traversal                     | 3.36 ms                                                            | 3.05 ms: 1.10x faster                                                    |
| python_startup_no_site           | 6.52 ms                                                            | 6.00 ms: 1.09x faster                                                    |
| logging_format                   | 6.00 us                                                            | 5.55 us: 1.08x faster                                                    |
| nbody                            | 74.2 ms                                                            | 68.7 ms: 1.08x faster                                                    |
| deepcopy                         | 198 us                                                             | 186 us: 1.07x faster                                                     |
| async_tree_eager                 | 83.0 ms                                                            | 77.9 ms: 1.07x faster                                                    |
| thread_mandelbrot_optimized      | 205 ms                                                             | 193 ms: 1.06x faster                                                     |
| scimark_sor                      | 78.2 ms                                                            | 73.6 ms: 1.06x faster                                                    |
| thread_mandelbrot_naive          | 207 ms                                                             | 195 ms: 1.06x faster                                                     |
| noop                             | 19.2 ns                                                            | 18.1 ns: 1.06x faster                                                    |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 12.2 ms: 1.05x faster                                                    |
| nqueens                          | 59.8 ms                                                            | 56.8 ms: 1.05x faster                                                    |
| unpack_sequence                  | 35.6 ns                                                            | 33.8 ns: 1.05x faster                                                    |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.15 ms: 1.05x faster                                                    |
| sqlglot_v2_parse                 | 954 us                                                             | 907 us: 1.05x faster                                                     |
| docutils                         | 1.98 sec                                                           | 1.88 sec: 1.05x faster                                                   |
| comprehensions                   | 11.4 us                                                            | 10.9 us: 1.05x faster                                                    |
| deepcopy_reduce                  | 2.02 us                                                            | 1.93 us: 1.05x faster                                                    |
| tomli_loads                      | 1.49 sec                                                           | 1.43 sec: 1.05x faster                                                   |
| mypy2                            | 780 ms                                                             | 747 ms: 1.04x faster                                                     |
| spectral_norm                    | 64.1 ms                                                            | 61.7 ms: 1.04x faster                                                    |
| thread_montecarlo_naive          | 14.3 ms                                                            | 13.8 ms: 1.04x faster                                                    |
| logging_silent                   | 59.2 ns                                                            | 57.4 ns: 1.03x faster                                                    |
| deltablue                        | 2.76 ms                                                            | 2.68 ms: 1.03x faster                                                    |
| python_startup                   | 9.93 ms                                                            | 9.64 ms: 1.03x faster                                                    |
| chaos                            | 42.9 ms                                                            | 41.7 ms: 1.03x faster                                                    |
| deepcopy_memo                    | 19.1 us                                                            | 18.6 us: 1.03x faster                                                    |
| json_loads                       | 18.6 us                                                            | 18.1 us: 1.03x faster                                                    |
| pickle_dict                      | 20.0 us                                                            | 19.5 us: 1.03x faster                                                    |
| xml_etree_iterparse              | 85.5 ms                                                            | 83.4 ms: 1.03x faster                                                    |
| unpickle_list                    | 3.03 us                                                            | 2.96 us: 1.02x faster                                                    |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.26 sec: 1.02x faster                                                   |
| tornado_http                     | 101 ms                                                             | 98.7 ms: 1.02x faster                                                    |
| logging_simple                   | 5.02 us                                                            | 4.91 us: 1.02x faster                                                    |
| telco                            | 5.39 ms                                                            | 5.28 ms: 1.02x faster                                                    |
| sqlalchemy_imperative            | 14.8 ms                                                            | 14.5 ms: 1.02x faster                                                    |
| scimark_monte_carlo              | 42.3 ms                                                            | 41.5 ms: 1.02x faster                                                    |
| xml_etree_process                | 50.0 ms                                                            | 49.1 ms: 1.02x faster                                                    |
| json                             | 3.46 ms                                                            | 3.42 ms: 1.01x faster                                                    |
| quadtree_nbody                   | 654 ms                                                             | 645 ms: 1.01x faster                                                     |
| richards_super                   | 40.3 ms                                                            | 39.8 ms: 1.01x faster                                                    |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 41.2 ms: 1.01x faster                                                    |
| scimark_fft                      | 211 ms                                                             | 209 ms: 1.01x faster                                                     |
| async_generators                 | 231 ms                                                             | 228 ms: 1.01x faster                                                     |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 83.9 ms: 1.01x faster                                                    |
| mdp                              | 971 ms                                                             | 961 ms: 1.01x faster                                                     |
| raytrace                         | 201 ms                                                             | 199 ms: 1.01x faster                                                     |
| networkx_shortest_path           | 447 ms                                                             | 443 ms: 1.01x faster                                                     |
| pyflate                          | 309 ms                                                             | 307 ms: 1.01x faster                                                     |
| fastapi_http                     | 222 ms                                                             | 221 ms: 1.00x faster                                                     |
| sympy_str                        | 200 ms                                                             | 199 ms: 1.00x faster                                                     |
| sympy_expand                     | 344 ms                                                             | 343 ms: 1.00x faster                                                     |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                     |
| networkx_connected_components    | 425 ms                                                             | 427 ms: 1.01x slower                                                     |
| sympy_sum                        | 109 ms                                                             | 109 ms: 1.01x slower                                                     |
| sympy_integrate                  | 15.1 ms                                                            | 15.2 ms: 1.01x slower                                                    |
| django_template                  | 30.5 ms                                                            | 30.7 ms: 1.01x slower                                                    |
| unpickle                         | 10.5 us                                                            | 10.6 us: 1.01x slower                                                    |
| go                               | 91.1 ms                                                            | 92.1 ms: 1.01x slower                                                    |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.14 sec: 1.01x slower                                                   |
| base64_small                     | 227 us                                                             | 230 us: 1.01x slower                                                     |
| decimal_factorial                | 174 ms                                                             | 177 ms: 1.01x slower                                                     |
| typing_runtime_protocols         | 115 us                                                             | 117 us: 1.01x slower                                                     |
| meteor_contest                   | 85.4 ms                                                            | 86.7 ms: 1.02x slower                                                    |
| decimal_pi                       | 209 ms                                                             | 212 ms: 1.02x slower                                                     |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.94 ms: 1.02x slower                                                    |
| asyncio_websockets               | 305 ms                                                             | 310 ms: 1.02x slower                                                     |
| hexiom                           | 4.50 ms                                                            | 4.58 ms: 1.02x slower                                                    |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 334 ms: 1.02x slower                                                     |
| pickle_pure_python               | 251 us                                                             | 256 us: 1.02x slower                                                     |
| regex_compile                    | 97.0 ms                                                            | 99.1 ms: 1.02x slower                                                    |
| unpickle_pure_python             | 163 us                                                             | 166 us: 1.02x slower                                                     |
| pickle                           | 8.04 us                                                            | 8.25 us: 1.03x slower                                                    |
| regex_dna                        | 147 ms                                                             | 152 ms: 1.03x slower                                                     |
| thrift                           | 2.00 ms                                                            | 2.06 ms: 1.03x slower                                                    |
| chameleon                        | 10.3 ms                                                            | 10.6 ms: 1.03x slower                                                    |
| thread_pipeline_naive            | 34.9 ms                                                            | 36.2 ms: 1.04x slower                                                    |
| scimark_lu                       | 74.7 ms                                                            | 77.6 ms: 1.04x slower                                                    |
| float                            | 51.2 ms                                                            | 53.8 ms: 1.05x slower                                                    |
| html5lib                         | 45.3 ms                                                            | 47.9 ms: 1.06x slower                                                    |
| xml_etree_parse                  | 118 ms                                                             | 125 ms: 1.06x slower                                                     |
| networkx_k_core                  | 2.05 sec                                                           | 2.18 sec: 1.06x slower                                                   |
| thread_memo_optimized            | 17.5 ms                                                            | 18.6 ms: 1.06x slower                                                    |
| mako                             | 8.69 ms                                                            | 9.25 ms: 1.06x slower                                                    |
| pprint_pformat                   | 1.10 sec                                                           | 1.17 sec: 1.07x slower                                                   |
| pycparser                        | 878 ms                                                             | 942 ms: 1.07x slower                                                     |
| pprint_safe_repr                 | 534 ms                                                             | 574 ms: 1.07x slower                                                     |
| xdsl_constant_fold               | 36.0 ms                                                            | 38.6 ms: 1.07x slower                                                    |
| pickle_list                      | 3.03 us                                                            | 3.26 us: 1.08x slower                                                    |
| thread_accumulate_naive          | 40.4 ms                                                            | 43.6 ms: 1.08x slower                                                    |
| regex_v8                         | 15.0 ms                                                            | 16.2 ms: 1.08x slower                                                    |
| thread_accumulate_optimized      | 39.5 ms                                                            | 42.9 ms: 1.09x slower                                                    |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 467 ms: 1.09x slower                                                     |
| thread_pipeline_optimized        | 25.8 ms                                                            | 28.2 ms: 1.09x slower                                                    |
| async_tree_none                  | 233 ms                                                             | 255 ms: 1.09x slower                                                     |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 416 ms: 1.11x slower                                                     |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 480 ms: 1.12x slower                                                     |
| async_tree_eager_tg              | 182 ms                                                             | 205 ms: 1.13x slower                                                     |
| regex_effbot                     | 1.98 ms                                                            | 2.23 ms: 1.13x slower                                                    |
| thread_counter_naive             | 21.2 ms                                                            | 24.0 ms: 1.13x slower                                                    |
| coverage                         | 54.5 ms                                                            | 61.7 ms: 1.13x slower                                                    |
| async_tree_eager_io              | 568 ms                                                             | 644 ms: 1.13x slower                                                     |
| async_tree_none_tg               | 224 ms                                                             | 260 ms: 1.16x slower                                                     |
| async_tree_memoization_tg        | 279 ms                                                             | 327 ms: 1.17x slower                                                     |
| async_tree_io                    | 549 ms                                                             | 648 ms: 1.18x slower                                                     |
| async_tree_memoization           | 285 ms                                                             | 337 ms: 1.18x slower                                                     |
| thread_counter_optimized         | 18.3 ms                                                            | 21.7 ms: 1.19x slower                                                    |
| base16_large                     | 6.35 ms                                                            | 7.57 ms: 1.19x slower                                                    |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 283 ms: 1.20x slower                                                     |
| async_tree_eager_io_tg           | 565 ms                                                             | 680 ms: 1.20x slower                                                     |
| async_tree_io_tg                 | 545 ms                                                             | 679 ms: 1.25x slower                                                     |
| base16_small                     | 265 us                                                             | 355 us: 1.34x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.20x faster                                                             |

Benchmark hidden because not significant (7): crypto_pyaes, xml_etree_generate, richards, async_tree_eager_memoization, fannkuch, coroutines, generators
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.204x faster

# HPT report

- Reliability score: 52.10% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 0.95x