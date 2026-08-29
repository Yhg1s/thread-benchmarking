# Results vs. 3.14.0

- fork: python
- ref: v3.15.0b4
- machine: linux-x86_64
- commit hash: 0a6fa62
- commit date: 2026-07-18
- overall geometric mean: 1.276x faster
- HPT reliability: 95.80%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.48x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.3 ms: 1.10x slower                                                  |
| docutils       | 1.98 sec                                                           | 2.16 sec: 1.09x slower                                                 |
| fastapi_http   | 222 ms                                                             | 187 ms: 1.18x faster                                                   |
| html5lib       | 45.3 ms                                                            | 46.8 ms: 1.03x slower                                                  |
| tornado_http   | 101 ms                                                             | 93.5 ms: 1.08x faster                                                  |
| Geometric mean | (ref)                                                              | 1.01x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 285 ms: 1.14x faster                                                   |
| async_tree_eager_io_tg           | 565 ms                                                             | 536 ms: 1.05x faster                                                   |
| asyncio_websockets               | 305 ms                                                             | 296 ms: 1.03x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 534 ms: 1.02x faster                                                   |
| coroutines                       | 15.1 ms                                                            | 15.4 ms: 1.01x slower                                                  |
| async_tree_io                    | 549 ms                                                             | 562 ms: 1.02x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.33 sec: 1.03x slower                                                 |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 347 ms: 1.06x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 88.3 ms: 1.06x slower                                                  |
| async_generators                 | 231 ms                                                             | 247 ms: 1.07x slower                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 463 ms: 1.08x slower                                                   |
| async_tree_none_tg               | 224 ms                                                             | 251 ms: 1.12x slower                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 205 ms: 1.12x slower                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 495 ms: 1.15x slower                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 322 ms: 1.15x slower                                                   |
| async_tree_none                  | 233 ms                                                             | 272 ms: 1.17x slower                                                   |
| async_tree_memoization           | 285 ms                                                             | 349 ms: 1.23x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 459 ms: 1.23x slower                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 224 ms: 1.23x slower                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 309 ms: 1.31x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.08x slower                                                           |

Benchmark hidden because not significant (1): async_tree_eager_io

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 20.6 ns: 1.07x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 189 ms: 1.09x slower                                                   |
| decimal_pi        | 209 ms                                                             | 243 ms: 1.16x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.12x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| quadtree_nbody | 654 ms                                                             | 629 ms: 1.04x faster                                                   |
| pidigits       | 216 ms                                                             | 215 ms: 1.01x faster                                                   |
| nbody          | 74.2 ms                                                            | 79.4 ms: 1.07x slower                                                  |
| float          | 51.2 ms                                                            | 63.3 ms: 1.24x slower                                                  |
| Geometric mean | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_dna      | 147 ms                                                             | 152 ms: 1.03x slower                                                   |
| regex_v8       | 15.0 ms                                                            | 15.8 ms: 1.05x slower                                                  |
| regex_compile  | 97.0 ms                                                            | 102 ms: 1.05x slower                                                   |
| regex_effbot   | 1.98 ms                                                            | 2.39 ms: 1.21x slower                                                  |
| Geometric mean | (ref)                                                              | 1.08x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 289 ms                                                             | 1.90 ms: 152.34x faster                                                |
| ascii85_large        | 681 ms                                                             | 13.8 ms: 49.41x faster                                                 |
| base85_large         | 249 ms                                                             | 5.17 ms: 48.19x faster                                                 |
| base32_small         | 5.71 ms                                                            | 184 us: 30.96x faster                                                  |
| ascii85_small        | 13.0 ms                                                            | 511 us: 25.51x faster                                                  |
| base85_small         | 4.66 ms                                                            | 188 us: 24.78x faster                                                  |
| base64_large         | 5.70 ms                                                            | 1.60 ms: 3.55x faster                                                  |
| urlsafe_base64_small | 340 us                                                             | 230 us: 1.48x faster                                                   |
| xml_etree_iterparse  | 85.5 ms                                                            | 73.1 ms: 1.17x faster                                                  |
| json_dumps           | 7.52 ms                                                            | 6.73 ms: 1.12x faster                                                  |
| tomli_loads          | 1.49 sec                                                           | 1.37 sec: 1.09x faster                                                 |
| base64_small         | 227 us                                                             | 213 us: 1.07x faster                                                   |
| xml_etree_parse      | 118 ms                                                             | 116 ms: 1.02x faster                                                   |
| unpickle_pure_python | 163 us                                                             | 160 us: 1.01x faster                                                   |
| base16_large         | 6.35 ms                                                            | 6.27 ms: 1.01x faster                                                  |
| xml_etree_generate   | 68.1 ms                                                            | 67.4 ms: 1.01x faster                                                  |
| pickle_pure_python   | 251 us                                                             | 249 us: 1.01x faster                                                   |
| pickle_dict          | 20.0 us                                                            | 20.1 us: 1.01x slower                                                  |
| pickle               | 8.04 us                                                            | 8.09 us: 1.01x slower                                                  |
| xml_etree_process    | 50.0 ms                                                            | 51.0 ms: 1.02x slower                                                  |
| json_loads           | 18.6 us                                                            | 20.2 us: 1.09x slower                                                  |
| pickle_list          | 3.03 us                                                            | 3.36 us: 1.11x slower                                                  |
| unpickle_list        | 3.03 us                                                            | 3.38 us: 1.11x slower                                                  |
| unpickle             | 10.5 us                                                            | 11.7 us: 1.12x slower                                                  |
| base16_small         | 265 us                                                             | 330 us: 1.25x slower                                                   |
| Geometric mean       | (ref)                                                              | 2.63x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 11.4 ms: 1.14x slower                                                  |
| python_startup_no_site | 6.52 ms                                                            | 7.66 ms: 1.18x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.16x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 31.6 ms: 1.04x slower                                                  |
| mako            | 8.69 ms                                                            | 11.5 ms: 1.33x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.17x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 207 ms                                                             | 50.9 ms: 4.06x faster                                                  |
| thread_mandelbrot_optimized | 205 ms                                                             | 51.2 ms: 4.01x faster                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 6.80 ms: 3.79x faster                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 10.7 ms: 3.67x faster                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 11.5 ms: 3.51x faster                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 5.59 ms: 3.28x faster                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 5.60 ms: 3.13x faster                                                  |
| thread_montecarlo_optimized | 12.9 ms                                                            | 4.45 ms: 2.90x faster                                                  |
| thread_pipeline_naive       | 34.9 ms                                                            | 19.6 ms: 1.78x faster                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 12.4 ms: 1.71x faster                                                  |
| thread_memo_naive           | 12.4 ms                                                            | 21.6 ms: 1.75x slower                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 36.4 ms: 2.55x slower                                                  |
| Geometric mean              | (ref)                                                              | 2.24x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 289 ms                                                             | 1.90 ms: 152.34x faster                                                |
| ascii85_large                    | 681 ms                                                             | 13.8 ms: 49.41x faster                                                 |
| base85_large                     | 249 ms                                                             | 5.17 ms: 48.19x faster                                                 |
| base32_small                     | 5.71 ms                                                            | 184 us: 30.96x faster                                                  |
| ascii85_small                    | 13.0 ms                                                            | 511 us: 25.51x faster                                                  |
| base85_small                     | 4.66 ms                                                            | 188 us: 24.78x faster                                                  |
| argparse_many_optionals          | 34.5 ms                                                            | 8.44 ms: 4.09x faster                                                  |
| thread_mandelbrot_naive          | 207 ms                                                             | 50.9 ms: 4.06x faster                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 51.2 ms: 4.01x faster                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 6.80 ms: 3.79x faster                                                  |
| thread_accumulate_optimized      | 39.5 ms                                                            | 10.7 ms: 3.67x faster                                                  |
| base64_large                     | 5.70 ms                                                            | 1.60 ms: 3.55x faster                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 11.5 ms: 3.51x faster                                                  |
| thread_counter_optimized         | 18.3 ms                                                            | 5.59 ms: 3.28x faster                                                  |
| thread_memo_optimized            | 17.5 ms                                                            | 5.60 ms: 3.13x faster                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 4.45 ms: 2.90x faster                                                  |
| pylint                           | 222 ms                                                             | 91.0 ms: 2.44x faster                                                  |
| gc_traversal                     | 3.36 ms                                                            | 1.51 ms: 2.23x faster                                                  |
| thread_pipeline_naive            | 34.9 ms                                                            | 19.6 ms: 1.78x faster                                                  |
| thread_counter_naive             | 21.2 ms                                                            | 12.4 ms: 1.71x faster                                                  |
| create_gc_cycles                 | 2.02 ms                                                            | 1.21 ms: 1.67x faster                                                  |
| urlsafe_base64_small             | 340 us                                                             | 230 us: 1.48x faster                                                   |
| argparse_subparsers              | 687 us                                                             | 507 us: 1.35x faster                                                   |
| pathlib                          | 12.7 ms                                                            | 10.4 ms: 1.22x faster                                                  |
| fastapi_http                     | 222 ms                                                             | 187 ms: 1.18x faster                                                   |
| xml_etree_iterparse              | 85.5 ms                                                            | 73.1 ms: 1.17x faster                                                  |
| unpack_sequence                  | 35.6 ns                                                            | 31.2 ns: 1.14x faster                                                  |
| asyncio_tcp                      | 324 ms                                                             | 285 ms: 1.14x faster                                                   |
| json_dumps                       | 7.52 ms                                                            | 6.73 ms: 1.12x faster                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.37 sec: 1.09x faster                                                 |
| tornado_http                     | 101 ms                                                             | 93.5 ms: 1.08x faster                                                  |
| base64_small                     | 227 us                                                             | 213 us: 1.07x faster                                                   |
| async_tree_eager_io_tg           | 565 ms                                                             | 536 ms: 1.05x faster                                                   |
| logging_format                   | 6.00 us                                                            | 5.74 us: 1.05x faster                                                  |
| bpe_tokeniser                    | 3.11 sec                                                           | 2.98 sec: 1.04x faster                                                 |
| quadtree_nbody                   | 654 ms                                                             | 629 ms: 1.04x faster                                                   |
| pycparser                        | 878 ms                                                             | 850 ms: 1.03x faster                                                   |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 82.3 ms: 1.03x faster                                                  |
| asyncio_websockets               | 305 ms                                                             | 296 ms: 1.03x faster                                                   |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 40.6 ms: 1.03x faster                                                  |
| deepcopy                         | 198 us                                                             | 194 us: 1.02x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 534 ms: 1.02x faster                                                   |
| deltablue                        | 2.76 ms                                                            | 2.70 ms: 1.02x faster                                                  |
| xml_etree_parse                  | 118 ms                                                             | 116 ms: 1.02x faster                                                   |
| unpickle_pure_python             | 163 us                                                             | 160 us: 1.01x faster                                                   |
| comprehensions                   | 11.4 us                                                            | 11.2 us: 1.01x faster                                                  |
| thrift                           | 2.00 ms                                                            | 1.97 ms: 1.01x faster                                                  |
| base16_large                     | 6.35 ms                                                            | 6.27 ms: 1.01x faster                                                  |
| xml_etree_generate               | 68.1 ms                                                            | 67.4 ms: 1.01x faster                                                  |
| pickle_pure_python               | 251 us                                                             | 249 us: 1.01x faster                                                   |
| pidigits                         | 216 ms                                                             | 215 ms: 1.01x faster                                                   |
| pickle_dict                      | 20.0 us                                                            | 20.1 us: 1.01x slower                                                  |
| pickle                           | 8.04 us                                                            | 8.09 us: 1.01x slower                                                  |
| json                             | 3.46 ms                                                            | 3.49 ms: 1.01x slower                                                  |
| scimark_fft                      | 211 ms                                                             | 213 ms: 1.01x slower                                                   |
| go                               | 91.1 ms                                                            | 92.1 ms: 1.01x slower                                                  |
| richards_super                   | 40.3 ms                                                            | 40.9 ms: 1.01x slower                                                  |
| logging_simple                   | 5.02 us                                                            | 5.08 us: 1.01x slower                                                  |
| mdp                              | 971 ms                                                             | 984 ms: 1.01x slower                                                   |
| coroutines                       | 15.1 ms                                                            | 15.4 ms: 1.01x slower                                                  |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.23 ms: 1.02x slower                                                  |
| richards                         | 34.7 ms                                                            | 35.4 ms: 1.02x slower                                                  |
| xml_etree_process                | 50.0 ms                                                            | 51.0 ms: 1.02x slower                                                  |
| chaos                            | 42.9 ms                                                            | 43.8 ms: 1.02x slower                                                  |
| async_tree_io                    | 549 ms                                                             | 562 ms: 1.02x slower                                                   |
| telco                            | 5.39 ms                                                            | 5.54 ms: 1.03x slower                                                  |
| regex_dna                        | 147 ms                                                             | 152 ms: 1.03x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.33 sec: 1.03x slower                                                 |
| pprint_safe_repr                 | 534 ms                                                             | 550 ms: 1.03x slower                                                   |
| sympy_sum                        | 109 ms                                                             | 112 ms: 1.03x slower                                                   |
| html5lib                         | 45.3 ms                                                            | 46.8 ms: 1.03x slower                                                  |
| django_template                  | 30.5 ms                                                            | 31.6 ms: 1.04x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 357 ms: 1.04x slower                                                   |
| networkx_k_core                  | 2.05 sec                                                           | 2.13 sec: 1.04x slower                                                 |
| pyflate                          | 309 ms                                                             | 321 ms: 1.04x slower                                                   |
| sympy_str                        | 200 ms                                                             | 208 ms: 1.04x slower                                                   |
| hexiom                           | 4.50 ms                                                            | 4.69 ms: 1.04x slower                                                  |
| spectral_norm                    | 64.1 ms                                                            | 67.0 ms: 1.05x slower                                                  |
| pprint_pformat                   | 1.10 sec                                                           | 1.15 sec: 1.05x slower                                                 |
| nqueens                          | 59.8 ms                                                            | 62.6 ms: 1.05x slower                                                  |
| sqlglot_v2_parse                 | 954 us                                                             | 1.00 ms: 1.05x slower                                                  |
| regex_v8                         | 15.0 ms                                                            | 15.8 ms: 1.05x slower                                                  |
| regex_compile                    | 97.0 ms                                                            | 102 ms: 1.05x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 347 ms: 1.06x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 88.3 ms: 1.06x slower                                                  |
| raytrace                         | 201 ms                                                             | 214 ms: 1.07x slower                                                   |
| sympy_integrate                  | 15.1 ms                                                            | 16.2 ms: 1.07x slower                                                  |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.8 ms: 1.07x slower                                                  |
| nbody                            | 74.2 ms                                                            | 79.4 ms: 1.07x slower                                                  |
| async_generators                 | 231 ms                                                             | 247 ms: 1.07x slower                                                   |
| noop                             | 19.2 ns                                                            | 20.6 ns: 1.07x slower                                                  |
| scimark_lu                       | 74.7 ms                                                            | 80.4 ms: 1.08x slower                                                  |
| crypto_pyaes                     | 56.7 ms                                                            | 61.2 ms: 1.08x slower                                                  |
| deepcopy_reduce                  | 2.02 us                                                            | 2.19 us: 1.08x slower                                                  |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 463 ms: 1.08x slower                                                   |
| generators                       | 24.2 ms                                                            | 26.2 ms: 1.09x slower                                                  |
| decimal_factorial                | 174 ms                                                             | 189 ms: 1.09x slower                                                   |
| json_loads                       | 18.6 us                                                            | 20.2 us: 1.09x slower                                                  |
| docutils                         | 1.98 sec                                                           | 2.16 sec: 1.09x slower                                                 |
| mypy2                            | 780 ms                                                             | 852 ms: 1.09x slower                                                   |
| scimark_monte_carlo              | 42.3 ms                                                            | 46.3 ms: 1.09x slower                                                  |
| fannkuch                         | 246 ms                                                             | 270 ms: 1.10x slower                                                   |
| chameleon                        | 10.3 ms                                                            | 11.3 ms: 1.10x slower                                                  |
| xdsl_constant_fold               | 36.0 ms                                                            | 39.6 ms: 1.10x slower                                                  |
| typing_runtime_protocols         | 115 us                                                             | 127 us: 1.11x slower                                                   |
| pickle_list                      | 3.03 us                                                            | 3.36 us: 1.11x slower                                                  |
| meteor_contest                   | 85.4 ms                                                            | 95.1 ms: 1.11x slower                                                  |
| unpickle_list                    | 3.03 us                                                            | 3.38 us: 1.11x slower                                                  |
| unpickle                         | 10.5 us                                                            | 11.7 us: 1.12x slower                                                  |
| async_tree_none_tg               | 224 ms                                                             | 251 ms: 1.12x slower                                                   |
| async_tree_eager_memoization     | 183 ms                                                             | 205 ms: 1.12x slower                                                   |
| python_startup                   | 9.93 ms                                                            | 11.4 ms: 1.14x slower                                                  |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 495 ms: 1.15x slower                                                   |
| async_tree_memoization_tg        | 279 ms                                                             | 322 ms: 1.15x slower                                                   |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 3.35 ms: 1.16x slower                                                  |
| decimal_pi                       | 209 ms                                                             | 243 ms: 1.16x slower                                                   |
| networkx_shortest_path           | 447 ms                                                             | 521 ms: 1.17x slower                                                   |
| async_tree_none                  | 233 ms                                                             | 272 ms: 1.17x slower                                                   |
| python_startup_no_site           | 6.52 ms                                                            | 7.66 ms: 1.18x slower                                                  |
| networkx_connected_components    | 425 ms                                                             | 510 ms: 1.20x slower                                                   |
| regex_effbot                     | 1.98 ms                                                            | 2.39 ms: 1.21x slower                                                  |
| async_tree_memoization           | 285 ms                                                             | 349 ms: 1.23x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 459 ms: 1.23x slower                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 224 ms: 1.23x slower                                                   |
| float                            | 51.2 ms                                                            | 63.3 ms: 1.24x slower                                                  |
| base16_small                     | 265 us                                                             | 330 us: 1.25x slower                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 309 ms: 1.31x slower                                                   |
| mako                             | 8.69 ms                                                            | 11.5 ms: 1.33x slower                                                  |
| coverage                         | 54.5 ms                                                            | 73.9 ms: 1.36x slower                                                  |
| thread_memo_naive                | 12.4 ms                                                            | 21.6 ms: 1.75x slower                                                  |
| thread_montecarlo_naive          | 14.3 ms                                                            | 36.4 ms: 2.55x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.27x faster                                                           |

Benchmark hidden because not significant (4): scimark_sor, async_tree_eager_io, logging_silent, deepcopy_memo
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.276x faster

# HPT report

- Reliability score: 95.80% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.48x