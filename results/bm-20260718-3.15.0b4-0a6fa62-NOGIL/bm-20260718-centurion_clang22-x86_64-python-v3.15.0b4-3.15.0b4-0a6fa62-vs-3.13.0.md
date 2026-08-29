# Results vs. 3.13.0

- fork: python
- ref: v3.15.0b4
- machine: linux-x86_64
- commit hash: 0a6fa62
- commit date: 2026-07-18
- overall geometric mean: 1.357x faster
- HPT reliability: 99.90%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.61x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 11.3 ms: 1.02x slower                                                  |
| docutils       | 1.89 sec                                                           | 2.16 sec: 1.14x slower                                                 |
| fastapi_http   | 215 ms                                                             | 187 ms: 1.15x faster                                                   |
| html5lib       | 50.9 ms                                                            | 46.8 ms: 1.09x faster                                                  |
| tornado_http   | 98.9 ms                                                            | 93.5 ms: 1.06x faster                                                  |
| Geometric mean | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 534 ms: 1.46x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 536 ms: 1.36x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 567 ms: 1.33x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 562 ms: 1.32x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 322 ms: 1.30x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 15.4 ms: 1.18x faster                                                  |
| async_tree_none_tg               | 290 ms                                                             | 251 ms: 1.16x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 272 ms: 1.15x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 349 ms: 1.12x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 285 ms: 1.11x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 463 ms: 1.09x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 205 ms: 1.08x faster                                                   |
| asyncio_websockets               | 313 ms                                                             | 296 ms: 1.06x faster                                                   |
| async_generators                 | 251 ms                                                             | 247 ms: 1.02x faster                                                   |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 347 ms: 1.01x slower                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.33 sec: 1.04x slower                                                 |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 459 ms: 1.53x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 309 ms: 1.77x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 224 ms: 3.95x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.00x faster                                                           |

Benchmark hidden because not significant (2): async_tree_eager, async_tree_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 20.6 ns: 1.04x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 243 ms: 1.06x slower                                                   |
| decimal_factorial | 177 ms                                                             | 189 ms: 1.07x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.07x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| quadtree_nbody | 675 ms                                                             | 629 ms: 1.07x faster                                                   |
| pidigits       | 216 ms                                                             | 215 ms: 1.00x faster                                                   |
| nbody          | 75.8 ms                                                            | 79.4 ms: 1.05x slower                                                  |
| float          | 59.2 ms                                                            | 63.3 ms: 1.07x slower                                                  |
| Geometric mean | (ref)                                                              | 1.01x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_dna      | 159 ms                                                             | 152 ms: 1.05x faster                                                   |
| regex_compile  | 102 ms                                                             | 102 ms: 1.00x faster                                                   |
| regex_v8       | 15.0 ms                                                            | 15.8 ms: 1.05x slower                                                  |
| Geometric mean | (ref)                                                              | 1.01x slower                                                           |

Benchmark hidden because not significant (1): regex_effbot

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 325 ms                                                             | 1.90 ms: 171.03x faster                                                |
| ascii85_large        | 824 ms                                                             | 13.8 ms: 59.79x faster                                                 |
| base85_large         | 267 ms                                                             | 5.17 ms: 51.58x faster                                                 |
| base32_small         | 6.46 ms                                                            | 184 us: 35.04x faster                                                  |
| ascii85_small        | 15.7 ms                                                            | 511 us: 30.78x faster                                                  |
| base85_small         | 4.85 ms                                                            | 188 us: 25.75x faster                                                  |
| base16_large         | 42.7 ms                                                            | 6.27 ms: 6.81x faster                                                  |
| base64_large         | 5.69 ms                                                            | 1.60 ms: 3.55x faster                                                  |
| base16_small         | 836 us                                                             | 330 us: 2.54x faster                                                   |
| urlsafe_base64_small | 328 us                                                             | 230 us: 1.42x faster                                                   |
| tomli_loads          | 1.77 sec                                                           | 1.37 sec: 1.30x faster                                                 |
| xml_etree_iterparse  | 86.8 ms                                                            | 73.1 ms: 1.19x faster                                                  |
| json_dumps           | 7.26 ms                                                            | 6.73 ms: 1.08x faster                                                  |
| xml_etree_generate   | 70.6 ms                                                            | 67.4 ms: 1.05x faster                                                  |
| xml_etree_parse      | 121 ms                                                             | 116 ms: 1.05x faster                                                   |
| base64_small         | 222 us                                                             | 213 us: 1.04x faster                                                   |
| pickle_pure_python   | 245 us                                                             | 249 us: 1.01x slower                                                   |
| xml_etree_process    | 49.9 ms                                                            | 51.0 ms: 1.02x slower                                                  |
| pickle_dict          | 19.0 us                                                            | 20.1 us: 1.05x slower                                                  |
| unpickle             | 10.8 us                                                            | 11.7 us: 1.08x slower                                                  |
| json_loads           | 18.2 us                                                            | 20.2 us: 1.11x slower                                                  |
| pickle               | 7.21 us                                                            | 8.09 us: 1.12x slower                                                  |
| pickle_list          | 2.66 us                                                            | 3.36 us: 1.26x slower                                                  |
| Geometric mean       | (ref)                                                              | 3.05x faster                                                           |

Benchmark hidden because not significant (2): unpickle_list, unpickle_pure_python

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 7.66 ms: 1.18x slower                                                  |
| python_startup         | 9.51 ms                                                            | 11.4 ms: 1.19x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.19x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 28.8 ms                                                            | 31.6 ms: 1.10x slower                                                  |
| mako            | 8.30 ms                                                            | 11.5 ms: 1.39x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.24x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 190 ms                                                             | 50.9 ms: 3.72x faster                                                  |
| thread_mandelbrot_optimized | 189 ms                                                             | 51.2 ms: 3.69x faster                                                  |
| thread_counter_optimized    | 19.7 ms                                                            | 5.59 ms: 3.53x faster                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 6.80 ms: 3.35x faster                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 10.7 ms: 3.29x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 4.45 ms: 3.19x faster                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 11.5 ms: 3.17x faster                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 5.60 ms: 3.01x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 19.6 ms: 2.55x faster                                                  |
| thread_counter_naive        | 23.7 ms                                                            | 12.4 ms: 1.92x faster                                                  |
| thread_memo_naive           | 37.9 ms                                                            | 21.6 ms: 1.75x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 36.4 ms: 2.01x slower                                                  |
| Geometric mean              | (ref)                                                              | 2.53x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 325 ms                                                             | 1.90 ms: 171.03x faster                                                |
| ascii85_large                    | 824 ms                                                             | 13.8 ms: 59.79x faster                                                 |
| base85_large                     | 267 ms                                                             | 5.17 ms: 51.58x faster                                                 |
| base32_small                     | 6.46 ms                                                            | 184 us: 35.04x faster                                                  |
| ascii85_small                    | 15.7 ms                                                            | 511 us: 30.78x faster                                                  |
| base85_small                     | 4.85 ms                                                            | 188 us: 25.75x faster                                                  |
| base16_large                     | 42.7 ms                                                            | 6.27 ms: 6.81x faster                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 50.9 ms: 3.72x faster                                                  |
| thread_mandelbrot_optimized      | 189 ms                                                             | 51.2 ms: 3.69x faster                                                  |
| base64_large                     | 5.69 ms                                                            | 1.60 ms: 3.55x faster                                                  |
| thread_counter_optimized         | 19.7 ms                                                            | 5.59 ms: 3.53x faster                                                  |
| thread_pipeline_optimized        | 22.8 ms                                                            | 6.80 ms: 3.35x faster                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 10.7 ms: 3.29x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 4.45 ms: 3.19x faster                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 11.5 ms: 3.17x faster                                                  |
| thread_memo_optimized            | 16.8 ms                                                            | 5.60 ms: 3.01x faster                                                  |
| thread_pipeline_naive            | 49.8 ms                                                            | 19.6 ms: 2.55x faster                                                  |
| base16_small                     | 836 us                                                             | 330 us: 2.54x faster                                                   |
| pylint                           | 226 ms                                                             | 91.0 ms: 2.48x faster                                                  |
| gc_traversal                     | 3.20 ms                                                            | 1.51 ms: 2.12x faster                                                  |
| mdp                              | 2.05 sec                                                           | 984 ms: 2.09x faster                                                   |
| thread_counter_naive             | 23.7 ms                                                            | 12.4 ms: 1.92x faster                                                  |
| thread_memo_naive                | 37.9 ms                                                            | 21.6 ms: 1.75x faster                                                  |
| argparse_many_optionals          | 12.9 ms                                                            | 8.44 ms: 1.53x faster                                                  |
| create_gc_cycles                 | 1.77 ms                                                            | 1.21 ms: 1.47x faster                                                  |
| async_tree_io_tg                 | 781 ms                                                             | 534 ms: 1.46x faster                                                   |
| deepcopy_memo                    | 27.8 us                                                            | 19.2 us: 1.45x faster                                                  |
| urlsafe_base64_small             | 328 us                                                             | 230 us: 1.42x faster                                                   |
| go                               | 129 ms                                                             | 92.1 ms: 1.41x faster                                                  |
| deepcopy                         | 267 us                                                             | 194 us: 1.38x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 536 ms: 1.36x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 567 ms: 1.33x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 562 ms: 1.32x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 322 ms: 1.30x faster                                                   |
| tomli_loads                      | 1.77 sec                                                           | 1.37 sec: 1.30x faster                                                 |
| scimark_sor                      | 96.2 ms                                                            | 77.8 ms: 1.24x faster                                                  |
| xml_etree_iterparse              | 86.8 ms                                                            | 73.1 ms: 1.19x faster                                                  |
| coroutines                       | 18.2 ms                                                            | 15.4 ms: 1.18x faster                                                  |
| pathlib                          | 12.2 ms                                                            | 10.4 ms: 1.17x faster                                                  |
| pyflate                          | 374 ms                                                             | 321 ms: 1.16x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 251 ms: 1.16x faster                                                   |
| fastapi_http                     | 215 ms                                                             | 187 ms: 1.15x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 272 ms: 1.15x faster                                                   |
| bpe_tokeniser                    | 3.37 sec                                                           | 2.98 sec: 1.13x faster                                                 |
| async_tree_memoization           | 392 ms                                                             | 349 ms: 1.12x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 285 ms: 1.11x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 463 ms: 1.09x faster                                                   |
| html5lib                         | 50.9 ms                                                            | 46.8 ms: 1.09x faster                                                  |
| json_dumps                       | 7.26 ms                                                            | 6.73 ms: 1.08x faster                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 2.19 us: 1.08x faster                                                  |
| async_tree_eager_memoization     | 221 ms                                                             | 205 ms: 1.08x faster                                                   |
| richards                         | 38.2 ms                                                            | 35.4 ms: 1.08x faster                                                  |
| quadtree_nbody                   | 675 ms                                                             | 629 ms: 1.07x faster                                                   |
| richards_super                   | 43.8 ms                                                            | 40.9 ms: 1.07x faster                                                  |
| fannkuch                         | 287 ms                                                             | 270 ms: 1.06x faster                                                   |
| pycparser                        | 901 ms                                                             | 850 ms: 1.06x faster                                                   |
| asyncio_websockets               | 313 ms                                                             | 296 ms: 1.06x faster                                                   |
| tornado_http                     | 98.9 ms                                                            | 93.5 ms: 1.06x faster                                                  |
| thrift                           | 2.07 ms                                                            | 1.97 ms: 1.05x faster                                                  |
| xml_etree_generate               | 70.6 ms                                                            | 67.4 ms: 1.05x faster                                                  |
| regex_dna                        | 159 ms                                                             | 152 ms: 1.05x faster                                                   |
| xml_etree_parse                  | 121 ms                                                             | 116 ms: 1.05x faster                                                   |
| base64_small                     | 222 us                                                             | 213 us: 1.04x faster                                                   |
| noop                             | 21.4 ns                                                            | 20.6 ns: 1.04x faster                                                  |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 40.6 ms: 1.04x faster                                                  |
| spectral_norm                    | 68.6 ms                                                            | 67.0 ms: 1.02x faster                                                  |
| scimark_monte_carlo              | 47.2 ms                                                            | 46.3 ms: 1.02x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 11.2 us: 1.02x faster                                                  |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 82.3 ms: 1.02x faster                                                  |
| scimark_fft                      | 216 ms                                                             | 213 ms: 1.02x faster                                                   |
| logging_silent                   | 60.1 ns                                                            | 59.2 ns: 1.02x faster                                                  |
| async_generators                 | 251 ms                                                             | 247 ms: 1.02x faster                                                   |
| networkx_k_core                  | 2.16 sec                                                           | 2.13 sec: 1.01x faster                                                 |
| hexiom                           | 4.75 ms                                                            | 4.69 ms: 1.01x faster                                                  |
| pidigits                         | 216 ms                                                             | 215 ms: 1.00x faster                                                   |
| regex_compile                    | 102 ms                                                             | 102 ms: 1.00x faster                                                   |
| logging_simple                   | 5.06 us                                                            | 5.08 us: 1.01x slower                                                  |
| pprint_safe_repr                 | 546 ms                                                             | 550 ms: 1.01x slower                                                   |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.23 ms: 1.01x slower                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 347 ms: 1.01x slower                                                   |
| pickle_pure_python               | 245 us                                                             | 249 us: 1.01x slower                                                   |
| chameleon                        | 11.1 ms                                                            | 11.3 ms: 1.02x slower                                                  |
| pprint_pformat                   | 1.13 sec                                                           | 1.15 sec: 1.02x slower                                                 |
| logging_format                   | 5.62 us                                                            | 5.74 us: 1.02x slower                                                  |
| sqlglot_v2_parse                 | 979 us                                                             | 1.00 ms: 1.02x slower                                                  |
| xml_etree_process                | 49.9 ms                                                            | 51.0 ms: 1.02x slower                                                  |
| telco                            | 5.37 ms                                                            | 5.54 ms: 1.03x slower                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.33 sec: 1.04x slower                                                 |
| deltablue                        | 2.59 ms                                                            | 2.70 ms: 1.04x slower                                                  |
| nbody                            | 75.8 ms                                                            | 79.4 ms: 1.05x slower                                                  |
| sympy_integrate                  | 15.4 ms                                                            | 16.2 ms: 1.05x slower                                                  |
| regex_v8                         | 15.0 ms                                                            | 15.8 ms: 1.05x slower                                                  |
| pickle_dict                      | 19.0 us                                                            | 20.1 us: 1.05x slower                                                  |
| decimal_pi                       | 228 ms                                                             | 243 ms: 1.06x slower                                                   |
| float                            | 59.2 ms                                                            | 63.3 ms: 1.07x slower                                                  |
| decimal_factorial                | 177 ms                                                             | 189 ms: 1.07x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 112 ms: 1.07x slower                                                   |
| nqueens                          | 58.3 ms                                                            | 62.6 ms: 1.07x slower                                                  |
| sympy_expand                     | 331 ms                                                             | 357 ms: 1.08x slower                                                   |
| sympy_str                        | 193 ms                                                             | 208 ms: 1.08x slower                                                   |
| unpickle                         | 10.8 us                                                            | 11.7 us: 1.08x slower                                                  |
| raytrace                         | 197 ms                                                             | 214 ms: 1.09x slower                                                   |
| xdsl_constant_fold               | 36.4 ms                                                            | 39.6 ms: 1.09x slower                                                  |
| django_template                  | 28.8 ms                                                            | 31.6 ms: 1.10x slower                                                  |
| crypto_pyaes                     | 55.6 ms                                                            | 61.2 ms: 1.10x slower                                                  |
| meteor_contest                   | 85.7 ms                                                            | 95.1 ms: 1.11x slower                                                  |
| json_loads                       | 18.2 us                                                            | 20.2 us: 1.11x slower                                                  |
| pickle                           | 7.21 us                                                            | 8.09 us: 1.12x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 507 us: 1.13x slower                                                   |
| typing_runtime_protocols         | 112 us                                                             | 127 us: 1.14x slower                                                   |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.8 ms: 1.14x slower                                                  |
| docutils                         | 1.89 sec                                                           | 2.16 sec: 1.14x slower                                                 |
| scimark_lu                       | 70.2 ms                                                            | 80.4 ms: 1.15x slower                                                  |
| networkx_shortest_path           | 454 ms                                                             | 521 ms: 1.15x slower                                                   |
| mypy2                            | 741 ms                                                             | 852 ms: 1.15x slower                                                   |
| networkx_connected_components    | 443 ms                                                             | 510 ms: 1.15x slower                                                   |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 3.35 ms: 1.17x slower                                                  |
| unpack_sequence                  | 26.4 ns                                                            | 31.2 ns: 1.18x slower                                                  |
| python_startup_no_site           | 6.49 ms                                                            | 7.66 ms: 1.18x slower                                                  |
| generators                       | 22.2 ms                                                            | 26.2 ms: 1.18x slower                                                  |
| python_startup                   | 9.51 ms                                                            | 11.4 ms: 1.19x slower                                                  |
| pickle_list                      | 2.66 us                                                            | 3.36 us: 1.26x slower                                                  |
| coverage                         | 55.0 ms                                                            | 73.9 ms: 1.34x slower                                                  |
| mako                             | 8.30 ms                                                            | 11.5 ms: 1.39x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 459 ms: 1.53x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 309 ms: 1.77x slower                                                   |
| thread_montecarlo_naive          | 18.1 ms                                                            | 36.4 ms: 2.01x slower                                                  |
| async_tree_eager_tg              | 56.8 ms                                                            | 224 ms: 3.95x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.36x faster                                                           |

Benchmark hidden because not significant (7): unpickle_list, unpickle_pure_python, json, async_tree_eager, async_tree_cpu_io_mixed, chaos, regex_effbot
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.357x faster

# HPT report

- Reliability score: 99.90% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.02x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.61x