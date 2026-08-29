# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.265x faster
- HPT reliability: 99.22%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.48x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.2 ms: 1.09x slower                                                    |
| docutils       | 1.98 sec                                                           | 2.17 sec: 1.10x slower                                                   |
| fastapi_http   | 222 ms                                                             | 191 ms: 1.16x faster                                                     |
| html5lib       | 45.3 ms                                                            | 46.8 ms: 1.03x slower                                                    |
| tornado_http   | 101 ms                                                             | 93.9 ms: 1.08x faster                                                    |
| Geometric mean | (ref)                                                              | 1.00x faster                                                             |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 287 ms: 1.13x faster                                                     |
| asyncio_websockets               | 305 ms                                                             | 287 ms: 1.06x faster                                                     |
| async_tree_eager_io_tg           | 565 ms                                                             | 546 ms: 1.04x faster                                                     |
| async_tree_io_tg                 | 545 ms                                                             | 532 ms: 1.03x faster                                                     |
| async_tree_io                    | 549 ms                                                             | 559 ms: 1.02x slower                                                     |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.33 sec: 1.03x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 348 ms: 1.06x slower                                                     |
| async_generators                 | 231 ms                                                             | 248 ms: 1.07x slower                                                     |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 465 ms: 1.09x slower                                                     |
| async_tree_eager                 | 83.0 ms                                                            | 90.4 ms: 1.09x slower                                                    |
| async_tree_eager_memoization     | 183 ms                                                             | 204 ms: 1.12x slower                                                     |
| async_tree_none_tg               | 224 ms                                                             | 252 ms: 1.12x slower                                                     |
| async_tree_memoization_tg        | 279 ms                                                             | 322 ms: 1.15x slower                                                     |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 497 ms: 1.16x slower                                                     |
| async_tree_none                  | 233 ms                                                             | 271 ms: 1.16x slower                                                     |
| async_tree_memoization           | 285 ms                                                             | 347 ms: 1.22x slower                                                     |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 461 ms: 1.23x slower                                                     |
| async_tree_eager_tg              | 182 ms                                                             | 226 ms: 1.24x slower                                                     |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 309 ms: 1.31x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.08x slower                                                             |

Benchmark hidden because not significant (2): async_tree_eager_io, coroutines

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 20.6 ns: 1.08x slower                                                    |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 189 ms: 1.09x slower                                                     |
| decimal_pi        | 209 ms                                                             | 245 ms: 1.17x slower                                                     |
| Geometric mean    | (ref)                                                              | 1.13x slower                                                             |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 215 ms: 1.01x faster                                                     |
| nbody          | 74.2 ms                                                            | 82.4 ms: 1.11x slower                                                    |
| float          | 51.2 ms                                                            | 63.9 ms: 1.25x slower                                                    |
| Geometric mean | (ref)                                                              | 1.08x slower                                                             |

Benchmark hidden because not significant (1): quadtree_nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| regex_dna      | 147 ms                                                             | 154 ms: 1.04x slower                                                     |
| regex_v8       | 15.0 ms                                                            | 15.7 ms: 1.05x slower                                                    |
| regex_compile  | 97.0 ms                                                            | 103 ms: 1.06x slower                                                     |
| regex_effbot   | 1.98 ms                                                            | 2.31 ms: 1.17x slower                                                    |
| Geometric mean | (ref)                                                              | 1.08x slower                                                             |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large         | 289 ms                                                             | 1.91 ms: 151.19x faster                                                  |
| ascii85_large        | 681 ms                                                             | 13.8 ms: 49.39x faster                                                   |
| base85_large         | 249 ms                                                             | 5.17 ms: 48.21x faster                                                   |
| base32_small         | 5.71 ms                                                            | 185 us: 30.76x faster                                                    |
| ascii85_small        | 13.0 ms                                                            | 512 us: 25.48x faster                                                    |
| base85_small         | 4.66 ms                                                            | 192 us: 24.34x faster                                                    |
| base64_large         | 5.70 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| urlsafe_base64_small | 340 us                                                             | 224 us: 1.52x faster                                                     |
| xml_etree_iterparse  | 85.5 ms                                                            | 73.8 ms: 1.16x faster                                                    |
| base64_small         | 227 us                                                             | 208 us: 1.10x faster                                                     |
| tomli_loads          | 1.49 sec                                                           | 1.39 sec: 1.07x faster                                                   |
| json_dumps           | 7.52 ms                                                            | 7.02 ms: 1.07x faster                                                    |
| xml_etree_parse      | 118 ms                                                             | 116 ms: 1.02x faster                                                     |
| base16_large         | 6.35 ms                                                            | 6.27 ms: 1.01x faster                                                    |
| xml_etree_generate   | 68.1 ms                                                            | 67.9 ms: 1.00x faster                                                    |
| pickle               | 8.04 us                                                            | 8.16 us: 1.01x slower                                                    |
| unpickle_pure_python | 163 us                                                             | 165 us: 1.02x slower                                                     |
| pickle_dict          | 20.0 us                                                            | 20.3 us: 1.02x slower                                                    |
| pickle_pure_python   | 251 us                                                             | 256 us: 1.02x slower                                                     |
| xml_etree_process    | 50.0 ms                                                            | 51.2 ms: 1.03x slower                                                    |
| json_loads           | 18.6 us                                                            | 20.5 us: 1.10x slower                                                    |
| pickle_list          | 3.03 us                                                            | 3.38 us: 1.12x slower                                                    |
| unpickle_list        | 3.03 us                                                            | 3.39 us: 1.12x slower                                                    |
| unpickle             | 10.5 us                                                            | 11.9 us: 1.14x slower                                                    |
| base16_small         | 265 us                                                             | 330 us: 1.25x slower                                                     |
| Geometric mean       | (ref)                                                              | 2.61x faster                                                             |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 11.4 ms: 1.15x slower                                                    |
| python_startup_no_site | 6.52 ms                                                            | 7.73 ms: 1.19x slower                                                    |
| Geometric mean         | (ref)                                                              | 1.17x slower                                                             |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 32.4 ms: 1.06x slower                                                    |
| mako            | 8.69 ms                                                            | 11.5 ms: 1.32x slower                                                    |
| Geometric mean  | (ref)                                                              | 1.18x slower                                                             |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 207 ms                                                             | 51.3 ms: 4.02x faster                                                    |
| thread_mandelbrot_optimized | 205 ms                                                             | 51.7 ms: 3.97x faster                                                    |
| thread_pipeline_optimized   | 25.8 ms                                                            | 6.99 ms: 3.69x faster                                                    |
| thread_accumulate_optimized | 39.5 ms                                                            | 10.9 ms: 3.60x faster                                                    |
| thread_accumulate_naive     | 40.4 ms                                                            | 11.7 ms: 3.45x faster                                                    |
| thread_counter_optimized    | 18.3 ms                                                            | 5.65 ms: 3.24x faster                                                    |
| thread_memo_optimized       | 17.5 ms                                                            | 5.70 ms: 3.07x faster                                                    |
| thread_montecarlo_optimized | 12.9 ms                                                            | 4.34 ms: 2.97x faster                                                    |
| thread_pipeline_naive       | 34.9 ms                                                            | 19.5 ms: 1.79x faster                                                    |
| thread_counter_naive        | 21.2 ms                                                            | 12.5 ms: 1.70x faster                                                    |
| thread_memo_naive           | 12.4 ms                                                            | 21.7 ms: 1.75x slower                                                    |
| thread_montecarlo_naive     | 14.3 ms                                                            | 35.5 ms: 2.49x slower                                                    |
| Geometric mean              | (ref)                                                              | 2.23x faster                                                             |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large                     | 289 ms                                                             | 1.91 ms: 151.19x faster                                                  |
| ascii85_large                    | 681 ms                                                             | 13.8 ms: 49.39x faster                                                   |
| base85_large                     | 249 ms                                                             | 5.17 ms: 48.21x faster                                                   |
| base32_small                     | 5.71 ms                                                            | 185 us: 30.76x faster                                                    |
| ascii85_small                    | 13.0 ms                                                            | 512 us: 25.48x faster                                                    |
| base85_small                     | 4.66 ms                                                            | 192 us: 24.34x faster                                                    |
| argparse_many_optionals          | 34.5 ms                                                            | 8.53 ms: 4.04x faster                                                    |
| thread_mandelbrot_naive          | 207 ms                                                             | 51.3 ms: 4.02x faster                                                    |
| thread_mandelbrot_optimized      | 205 ms                                                             | 51.7 ms: 3.97x faster                                                    |
| thread_pipeline_optimized        | 25.8 ms                                                            | 6.99 ms: 3.69x faster                                                    |
| thread_accumulate_optimized      | 39.5 ms                                                            | 10.9 ms: 3.60x faster                                                    |
| base64_large                     | 5.70 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| thread_accumulate_naive          | 40.4 ms                                                            | 11.7 ms: 3.45x faster                                                    |
| thread_counter_optimized         | 18.3 ms                                                            | 5.65 ms: 3.24x faster                                                    |
| thread_memo_optimized            | 17.5 ms                                                            | 5.70 ms: 3.07x faster                                                    |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 4.34 ms: 2.97x faster                                                    |
| pylint                           | 222 ms                                                             | 91.3 ms: 2.43x faster                                                    |
| gc_traversal                     | 3.36 ms                                                            | 1.52 ms: 2.22x faster                                                    |
| thread_pipeline_naive            | 34.9 ms                                                            | 19.5 ms: 1.79x faster                                                    |
| thread_counter_naive             | 21.2 ms                                                            | 12.5 ms: 1.70x faster                                                    |
| create_gc_cycles                 | 2.02 ms                                                            | 1.20 ms: 1.68x faster                                                    |
| urlsafe_base64_small             | 340 us                                                             | 224 us: 1.52x faster                                                     |
| argparse_subparsers              | 687 us                                                             | 506 us: 1.36x faster                                                     |
| pathlib                          | 12.7 ms                                                            | 10.6 ms: 1.20x faster                                                    |
| fastapi_http                     | 222 ms                                                             | 191 ms: 1.16x faster                                                     |
| xml_etree_iterparse              | 85.5 ms                                                            | 73.8 ms: 1.16x faster                                                    |
| asyncio_tcp                      | 324 ms                                                             | 287 ms: 1.13x faster                                                     |
| unpack_sequence                  | 35.6 ns                                                            | 32.4 ns: 1.10x faster                                                    |
| base64_small                     | 227 us                                                             | 208 us: 1.10x faster                                                     |
| tornado_http                     | 101 ms                                                             | 93.9 ms: 1.08x faster                                                    |
| tomli_loads                      | 1.49 sec                                                           | 1.39 sec: 1.07x faster                                                   |
| json_dumps                       | 7.52 ms                                                            | 7.02 ms: 1.07x faster                                                    |
| asyncio_websockets               | 305 ms                                                             | 287 ms: 1.06x faster                                                     |
| async_tree_eager_io_tg           | 565 ms                                                             | 546 ms: 1.04x faster                                                     |
| logging_format                   | 6.00 us                                                            | 5.81 us: 1.03x faster                                                    |
| async_tree_io_tg                 | 545 ms                                                             | 532 ms: 1.03x faster                                                     |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 82.8 ms: 1.02x faster                                                    |
| deepcopy                         | 198 us                                                             | 194 us: 1.02x faster                                                     |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.05 sec: 1.02x faster                                                   |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 41.1 ms: 1.02x faster                                                    |
| thrift                           | 2.00 ms                                                            | 1.97 ms: 1.02x faster                                                    |
| xml_etree_parse                  | 118 ms                                                             | 116 ms: 1.02x faster                                                     |
| base16_large                     | 6.35 ms                                                            | 6.27 ms: 1.01x faster                                                    |
| pidigits                         | 216 ms                                                             | 215 ms: 1.01x faster                                                     |
| xml_etree_generate               | 68.1 ms                                                            | 67.9 ms: 1.00x faster                                                    |
| comprehensions                   | 11.4 us                                                            | 11.5 us: 1.01x slower                                                    |
| pickle                           | 8.04 us                                                            | 8.16 us: 1.01x slower                                                    |
| telco                            | 5.39 ms                                                            | 5.48 ms: 1.02x slower                                                    |
| nqueens                          | 59.8 ms                                                            | 60.8 ms: 1.02x slower                                                    |
| unpickle_pure_python             | 163 us                                                             | 165 us: 1.02x slower                                                     |
| async_tree_io                    | 549 ms                                                             | 559 ms: 1.02x slower                                                     |
| pickle_dict                      | 20.0 us                                                            | 20.3 us: 1.02x slower                                                    |
| pickle_pure_python               | 251 us                                                             | 256 us: 1.02x slower                                                     |
| mdp                              | 971 ms                                                             | 993 ms: 1.02x slower                                                     |
| json                             | 3.46 ms                                                            | 3.54 ms: 1.02x slower                                                    |
| scimark_fft                      | 211 ms                                                             | 216 ms: 1.03x slower                                                     |
| xml_etree_process                | 50.0 ms                                                            | 51.2 ms: 1.03x slower                                                    |
| logging_simple                   | 5.02 us                                                            | 5.15 us: 1.03x slower                                                    |
| logging_silent                   | 59.2 ns                                                            | 60.9 ns: 1.03x slower                                                    |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.33 sec: 1.03x slower                                                   |
| richards_super                   | 40.3 ms                                                            | 41.7 ms: 1.03x slower                                                    |
| html5lib                         | 45.3 ms                                                            | 46.8 ms: 1.03x slower                                                    |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.25 ms: 1.04x slower                                                    |
| richards                         | 34.7 ms                                                            | 36.0 ms: 1.04x slower                                                    |
| pyflate                          | 309 ms                                                             | 321 ms: 1.04x slower                                                     |
| go                               | 91.1 ms                                                            | 94.9 ms: 1.04x slower                                                    |
| deepcopy_memo                    | 19.1 us                                                            | 19.9 us: 1.04x slower                                                    |
| regex_dna                        | 147 ms                                                             | 154 ms: 1.04x slower                                                     |
| regex_v8                         | 15.0 ms                                                            | 15.7 ms: 1.05x slower                                                    |
| generators                       | 24.2 ms                                                            | 25.3 ms: 1.05x slower                                                    |
| chaos                            | 42.9 ms                                                            | 45.1 ms: 1.05x slower                                                    |
| networkx_k_core                  | 2.05 sec                                                           | 2.16 sec: 1.05x slower                                                   |
| sympy_sum                        | 109 ms                                                             | 115 ms: 1.06x slower                                                     |
| pprint_safe_repr                 | 534 ms                                                             | 566 ms: 1.06x slower                                                     |
| raytrace                         | 201 ms                                                             | 213 ms: 1.06x slower                                                     |
| django_template                  | 30.5 ms                                                            | 32.4 ms: 1.06x slower                                                    |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 348 ms: 1.06x slower                                                     |
| sympy_str                        | 200 ms                                                             | 213 ms: 1.06x slower                                                     |
| regex_compile                    | 97.0 ms                                                            | 103 ms: 1.06x slower                                                     |
| hexiom                           | 4.50 ms                                                            | 4.79 ms: 1.06x slower                                                    |
| sqlglot_v2_parse                 | 954 us                                                             | 1.02 ms: 1.06x slower                                                    |
| sympy_expand                     | 344 ms                                                             | 366 ms: 1.07x slower                                                     |
| spectral_norm                    | 64.1 ms                                                            | 68.3 ms: 1.07x slower                                                    |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.8 ms: 1.07x slower                                                    |
| deepcopy_reduce                  | 2.02 us                                                            | 2.17 us: 1.07x slower                                                    |
| async_generators                 | 231 ms                                                             | 248 ms: 1.07x slower                                                     |
| noop                             | 19.2 ns                                                            | 20.6 ns: 1.08x slower                                                    |
| sympy_integrate                  | 15.1 ms                                                            | 16.3 ms: 1.08x slower                                                    |
| pprint_pformat                   | 1.10 sec                                                           | 1.19 sec: 1.09x slower                                                   |
| decimal_factorial                | 174 ms                                                             | 189 ms: 1.09x slower                                                     |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 465 ms: 1.09x slower                                                     |
| async_tree_eager                 | 83.0 ms                                                            | 90.4 ms: 1.09x slower                                                    |
| chameleon                        | 10.3 ms                                                            | 11.2 ms: 1.09x slower                                                    |
| deltablue                        | 2.76 ms                                                            | 3.01 ms: 1.09x slower                                                    |
| scimark_lu                       | 74.7 ms                                                            | 82.0 ms: 1.10x slower                                                    |
| docutils                         | 1.98 sec                                                           | 2.17 sec: 1.10x slower                                                   |
| json_loads                       | 18.6 us                                                            | 20.5 us: 1.10x slower                                                    |
| mypy2                            | 780 ms                                                             | 859 ms: 1.10x slower                                                     |
| scimark_monte_carlo              | 42.3 ms                                                            | 46.8 ms: 1.11x slower                                                    |
| fannkuch                         | 246 ms                                                             | 274 ms: 1.11x slower                                                     |
| crypto_pyaes                     | 56.7 ms                                                            | 62.9 ms: 1.11x slower                                                    |
| nbody                            | 74.2 ms                                                            | 82.4 ms: 1.11x slower                                                    |
| typing_runtime_protocols         | 115 us                                                             | 128 us: 1.11x slower                                                     |
| pickle_list                      | 3.03 us                                                            | 3.38 us: 1.12x slower                                                    |
| async_tree_eager_memoization     | 183 ms                                                             | 204 ms: 1.12x slower                                                     |
| meteor_contest                   | 85.4 ms                                                            | 95.5 ms: 1.12x slower                                                    |
| unpickle_list                    | 3.03 us                                                            | 3.39 us: 1.12x slower                                                    |
| async_tree_none_tg               | 224 ms                                                             | 252 ms: 1.12x slower                                                     |
| xdsl_constant_fold               | 36.0 ms                                                            | 40.4 ms: 1.12x slower                                                    |
| unpickle                         | 10.5 us                                                            | 11.9 us: 1.14x slower                                                    |
| python_startup                   | 9.93 ms                                                            | 11.4 ms: 1.15x slower                                                    |
| async_tree_memoization_tg        | 279 ms                                                             | 322 ms: 1.15x slower                                                     |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 497 ms: 1.16x slower                                                     |
| async_tree_none                  | 233 ms                                                             | 271 ms: 1.16x slower                                                     |
| regex_effbot                     | 1.98 ms                                                            | 2.31 ms: 1.17x slower                                                    |
| decimal_pi                       | 209 ms                                                             | 245 ms: 1.17x slower                                                     |
| networkx_shortest_path           | 447 ms                                                             | 525 ms: 1.17x slower                                                     |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 3.41 ms: 1.18x slower                                                    |
| python_startup_no_site           | 6.52 ms                                                            | 7.73 ms: 1.19x slower                                                    |
| networkx_connected_components    | 425 ms                                                             | 512 ms: 1.21x slower                                                     |
| async_tree_memoization           | 285 ms                                                             | 347 ms: 1.22x slower                                                     |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 461 ms: 1.23x slower                                                     |
| async_tree_eager_tg              | 182 ms                                                             | 226 ms: 1.24x slower                                                     |
| base16_small                     | 265 us                                                             | 330 us: 1.25x slower                                                     |
| float                            | 51.2 ms                                                            | 63.9 ms: 1.25x slower                                                    |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 309 ms: 1.31x slower                                                     |
| mako                             | 8.69 ms                                                            | 11.5 ms: 1.32x slower                                                    |
| coverage                         | 54.5 ms                                                            | 73.8 ms: 1.35x slower                                                    |
| thread_memo_naive                | 12.4 ms                                                            | 21.7 ms: 1.75x slower                                                    |
| thread_montecarlo_naive          | 14.3 ms                                                            | 35.5 ms: 2.49x slower                                                    |
| Geometric mean                   | (ref)                                                              | 1.26x faster                                                             |

Benchmark hidden because not significant (5): async_tree_eager_io, pycparser, quadtree_nbody, coroutines, scimark_sor
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.265x faster

# HPT report

- Reliability score: 99.22% likely to be slow
- 90% likely to have a slowdown of 1.01x
- 95% likely to have a slowdown of 1.01x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.48x