# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.281x faster
- HPT reliability: 99.99%
- HPT 99th percentile: 1.01x faster
- Memory change: 1.05x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.6 ms: 1.05x faster                                                    |
| fastapi_http   | 215 ms                                                             | 221 ms: 1.03x slower                                                     |
| html5lib       | 50.9 ms                                                            | 47.9 ms: 1.06x faster                                                    |
| Geometric mean | (ref)                                                              | 1.02x faster                                                             |

Benchmark hidden because not significant (2): docutils, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 327 ms: 1.29x faster                                                     |
| async_tree_none                  | 312 ms                                                             | 255 ms: 1.23x faster                                                     |
| async_tree_eager_memoization     | 221 ms                                                             | 183 ms: 1.21x faster                                                     |
| coroutines                       | 18.2 ms                                                            | 15.2 ms: 1.19x faster                                                    |
| async_tree_eager_io              | 753 ms                                                             | 644 ms: 1.17x faster                                                     |
| async_tree_memoization           | 392 ms                                                             | 337 ms: 1.16x faster                                                     |
| async_tree_io_tg                 | 781 ms                                                             | 679 ms: 1.15x faster                                                     |
| async_tree_io                    | 743 ms                                                             | 648 ms: 1.15x faster                                                     |
| async_tree_eager                 | 88.3 ms                                                            | 77.9 ms: 1.13x faster                                                    |
| async_tree_none_tg               | 290 ms                                                             | 260 ms: 1.12x faster                                                     |
| asyncio_tcp                      | 316 ms                                                             | 287 ms: 1.10x faster                                                     |
| async_generators                 | 251 ms                                                             | 228 ms: 1.10x faster                                                     |
| async_tree_eager_io_tg           | 731 ms                                                             | 680 ms: 1.07x faster                                                     |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 480 ms: 1.06x faster                                                     |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 467 ms: 1.06x faster                                                     |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 334 ms: 1.03x faster                                                     |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.02x faster                                                   |
| asyncio_websockets               | 313 ms                                                             | 310 ms: 1.01x faster                                                     |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 416 ms: 1.38x slower                                                     |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 283 ms: 1.62x slower                                                     |
| async_tree_eager_tg              | 56.8 ms                                                            | 205 ms: 3.61x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.00x slower                                                             |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 18.1 ns: 1.18x faster                                                    |

Benchmarks with tag 'decimal':
==============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| decimal_pi     | 228 ms                                                             | 212 ms: 1.07x faster                                                     |
| Geometric mean | (ref)                                                              | 1.04x faster                                                             |

Benchmark hidden because not significant (1): decimal_factorial

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| nbody          | 75.8 ms                                                            | 68.7 ms: 1.10x faster                                                    |
| float          | 59.2 ms                                                            | 53.8 ms: 1.10x faster                                                    |
| quadtree_nbody | 675 ms                                                             | 645 ms: 1.05x faster                                                     |
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                     |
| Geometric mean | (ref)                                                              | 1.06x faster                                                             |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| regex_dna      | 159 ms                                                             | 152 ms: 1.05x faster                                                     |
| regex_effbot   | 2.33 ms                                                            | 2.23 ms: 1.04x faster                                                    |
| regex_compile  | 102 ms                                                             | 99.1 ms: 1.03x faster                                                    |
| regex_v8       | 15.0 ms                                                            | 16.2 ms: 1.08x slower                                                    |
| Geometric mean | (ref)                                                              | 1.01x faster                                                             |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large         | 325 ms                                                             | 1.90 ms: 171.22x faster                                                  |
| ascii85_large        | 824 ms                                                             | 13.8 ms: 59.80x faster                                                   |
| base85_large         | 267 ms                                                             | 5.13 ms: 51.99x faster                                                   |
| base32_small         | 6.46 ms                                                            | 203 us: 31.76x faster                                                    |
| ascii85_small        | 15.7 ms                                                            | 522 us: 30.13x faster                                                    |
| base85_small         | 4.85 ms                                                            | 198 us: 24.53x faster                                                    |
| base16_large         | 42.7 ms                                                            | 7.57 ms: 5.64x faster                                                    |
| base64_large         | 5.69 ms                                                            | 1.59 ms: 3.58x faster                                                    |
| base16_small         | 836 us                                                             | 355 us: 2.36x faster                                                     |
| urlsafe_base64_small | 328 us                                                             | 246 us: 1.33x faster                                                     |
| tomli_loads          | 1.77 sec                                                           | 1.43 sec: 1.24x faster                                                   |
| unpickle_list        | 3.42 us                                                            | 2.96 us: 1.16x faster                                                    |
| json_dumps           | 7.26 ms                                                            | 6.36 ms: 1.14x faster                                                    |
| xml_etree_iterparse  | 86.8 ms                                                            | 83.4 ms: 1.04x faster                                                    |
| xml_etree_generate   | 70.6 ms                                                            | 68.0 ms: 1.04x faster                                                    |
| unpickle             | 10.8 us                                                            | 10.6 us: 1.02x faster                                                    |
| xml_etree_process    | 49.9 ms                                                            | 49.1 ms: 1.02x faster                                                    |
| json_loads           | 18.2 us                                                            | 18.1 us: 1.00x faster                                                    |
| pickle_dict          | 19.0 us                                                            | 19.5 us: 1.02x slower                                                    |
| unpickle_pure_python | 161 us                                                             | 166 us: 1.03x slower                                                     |
| xml_etree_parse      | 121 ms                                                             | 125 ms: 1.03x slower                                                     |
| base64_small         | 222 us                                                             | 230 us: 1.04x slower                                                     |
| pickle_pure_python   | 245 us                                                             | 256 us: 1.04x slower                                                     |
| pickle               | 7.21 us                                                            | 8.25 us: 1.14x slower                                                    |
| pickle_list          | 2.66 us                                                            | 3.26 us: 1.23x slower                                                    |
| Geometric mean       | (ref)                                                              | 3.01x faster                                                             |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.00 ms: 1.08x faster                                                    |
| python_startup         | 9.51 ms                                                            | 9.64 ms: 1.01x slower                                                    |
| Geometric mean         | (ref)                                                              | 1.03x faster                                                             |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| django_template | 28.8 ms                                                            | 30.7 ms: 1.07x slower                                                    |
| mako            | 8.30 ms                                                            | 9.25 ms: 1.11x slower                                                    |
| Geometric mean  | (ref)                                                              | 1.09x slower                                                             |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 10.1 ms: 3.74x faster                                                    |
| thread_pipeline_naive       | 49.8 ms                                                            | 36.2 ms: 1.38x faster                                                    |
| thread_montecarlo_naive     | 18.1 ms                                                            | 13.8 ms: 1.32x faster                                                    |
| thread_montecarlo_optimized | 14.2 ms                                                            | 12.2 ms: 1.16x faster                                                    |
| thread_counter_naive        | 23.7 ms                                                            | 24.0 ms: 1.01x slower                                                    |
| thread_mandelbrot_optimized | 189 ms                                                             | 193 ms: 1.02x slower                                                     |
| thread_mandelbrot_naive     | 190 ms                                                             | 195 ms: 1.03x slower                                                     |
| thread_counter_optimized    | 19.7 ms                                                            | 21.7 ms: 1.10x slower                                                    |
| thread_memo_optimized       | 16.8 ms                                                            | 18.6 ms: 1.11x slower                                                    |
| thread_accumulate_naive     | 36.5 ms                                                            | 43.6 ms: 1.19x slower                                                    |
| thread_accumulate_optimized | 35.3 ms                                                            | 42.9 ms: 1.21x slower                                                    |
| thread_pipeline_optimized   | 22.8 ms                                                            | 28.2 ms: 1.24x slower                                                    |
| Geometric mean              | (ref)                                                              | 1.11x faster                                                             |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large                     | 325 ms                                                             | 1.90 ms: 171.22x faster                                                  |
| ascii85_large                    | 824 ms                                                             | 13.8 ms: 59.80x faster                                                   |
| base85_large                     | 267 ms                                                             | 5.13 ms: 51.99x faster                                                   |
| base32_small                     | 6.46 ms                                                            | 203 us: 31.76x faster                                                    |
| ascii85_small                    | 15.7 ms                                                            | 522 us: 30.13x faster                                                    |
| base85_small                     | 4.85 ms                                                            | 198 us: 24.53x faster                                                    |
| base16_large                     | 42.7 ms                                                            | 7.57 ms: 5.64x faster                                                    |
| thread_memo_naive                | 37.9 ms                                                            | 10.1 ms: 3.74x faster                                                    |
| base64_large                     | 5.69 ms                                                            | 1.59 ms: 3.58x faster                                                    |
| base16_small                     | 836 us                                                             | 355 us: 2.36x faster                                                     |
| pylint                           | 226 ms                                                             | 101 ms: 2.23x faster                                                     |
| mdp                              | 2.05 sec                                                           | 961 ms: 2.14x faster                                                     |
| argparse_many_optionals          | 12.9 ms                                                            | 8.18 ms: 1.58x faster                                                    |
| deepcopy_memo                    | 27.8 us                                                            | 18.6 us: 1.49x faster                                                    |
| deepcopy                         | 267 us                                                             | 186 us: 1.44x faster                                                     |
| go                               | 129 ms                                                             | 92.1 ms: 1.41x faster                                                    |
| thread_pipeline_naive            | 49.8 ms                                                            | 36.2 ms: 1.38x faster                                                    |
| urlsafe_base64_small             | 328 us                                                             | 246 us: 1.33x faster                                                     |
| thread_montecarlo_naive          | 18.1 ms                                                            | 13.8 ms: 1.32x faster                                                    |
| scimark_sor                      | 96.2 ms                                                            | 73.6 ms: 1.31x faster                                                    |
| async_tree_memoization_tg        | 421 ms                                                             | 327 ms: 1.29x faster                                                     |
| tomli_loads                      | 1.77 sec                                                           | 1.43 sec: 1.24x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 255 ms: 1.23x faster                                                     |
| deepcopy_reduce                  | 2.36 us                                                            | 1.93 us: 1.22x faster                                                    |
| pyflate                          | 374 ms                                                             | 307 ms: 1.22x faster                                                     |
| async_tree_eager_memoization     | 221 ms                                                             | 183 ms: 1.21x faster                                                     |
| coroutines                       | 18.2 ms                                                            | 15.2 ms: 1.19x faster                                                    |
| noop                             | 21.4 ns                                                            | 18.1 ns: 1.18x faster                                                    |
| async_tree_eager_io              | 753 ms                                                             | 644 ms: 1.17x faster                                                     |
| async_tree_memoization           | 392 ms                                                             | 337 ms: 1.16x faster                                                     |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 12.2 ms: 1.16x faster                                                    |
| fannkuch                         | 287 ms                                                             | 248 ms: 1.16x faster                                                     |
| unpickle_list                    | 3.42 us                                                            | 2.96 us: 1.16x faster                                                    |
| async_tree_io_tg                 | 781 ms                                                             | 679 ms: 1.15x faster                                                     |
| async_tree_io                    | 743 ms                                                             | 648 ms: 1.15x faster                                                     |
| json_dumps                       | 7.26 ms                                                            | 6.36 ms: 1.14x faster                                                    |
| pathlib                          | 12.2 ms                                                            | 10.7 ms: 1.14x faster                                                    |
| scimark_monte_carlo              | 47.2 ms                                                            | 41.5 ms: 1.14x faster                                                    |
| async_tree_eager                 | 88.3 ms                                                            | 77.9 ms: 1.13x faster                                                    |
| async_tree_none_tg               | 290 ms                                                             | 260 ms: 1.12x faster                                                     |
| spectral_norm                    | 68.6 ms                                                            | 61.7 ms: 1.11x faster                                                    |
| richards                         | 38.2 ms                                                            | 34.6 ms: 1.10x faster                                                    |
| nbody                            | 75.8 ms                                                            | 68.7 ms: 1.10x faster                                                    |
| asyncio_tcp                      | 316 ms                                                             | 287 ms: 1.10x faster                                                     |
| async_generators                 | 251 ms                                                             | 228 ms: 1.10x faster                                                     |
| float                            | 59.2 ms                                                            | 53.8 ms: 1.10x faster                                                    |
| richards_super                   | 43.8 ms                                                            | 39.8 ms: 1.10x faster                                                    |
| python_startup_no_site           | 6.49 ms                                                            | 6.00 ms: 1.08x faster                                                    |
| sqlglot_v2_parse                 | 979 us                                                             | 907 us: 1.08x faster                                                     |
| async_tree_eager_io_tg           | 731 ms                                                             | 680 ms: 1.07x faster                                                     |
| decimal_pi                       | 228 ms                                                             | 212 ms: 1.07x faster                                                     |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.14 sec: 1.07x faster                                                   |
| html5lib                         | 50.9 ms                                                            | 47.9 ms: 1.06x faster                                                    |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.15 ms: 1.06x faster                                                    |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 480 ms: 1.06x faster                                                     |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 467 ms: 1.06x faster                                                     |
| comprehensions                   | 11.4 us                                                            | 10.9 us: 1.05x faster                                                    |
| gc_traversal                     | 3.20 ms                                                            | 3.05 ms: 1.05x faster                                                    |
| create_gc_cycles                 | 1.77 ms                                                            | 1.69 ms: 1.05x faster                                                    |
| chameleon                        | 11.1 ms                                                            | 10.6 ms: 1.05x faster                                                    |
| regex_dna                        | 159 ms                                                             | 152 ms: 1.05x faster                                                     |
| logging_silent                   | 60.1 ns                                                            | 57.4 ns: 1.05x faster                                                    |
| quadtree_nbody                   | 675 ms                                                             | 645 ms: 1.05x faster                                                     |
| chaos                            | 43.6 ms                                                            | 41.7 ms: 1.05x faster                                                    |
| regex_effbot                     | 2.33 ms                                                            | 2.23 ms: 1.04x faster                                                    |
| xml_etree_iterparse              | 86.8 ms                                                            | 83.4 ms: 1.04x faster                                                    |
| xml_etree_generate               | 70.6 ms                                                            | 68.0 ms: 1.04x faster                                                    |
| hexiom                           | 4.75 ms                                                            | 4.58 ms: 1.04x faster                                                    |
| scimark_fft                      | 216 ms                                                             | 209 ms: 1.04x faster                                                     |
| networkx_connected_components    | 443 ms                                                             | 427 ms: 1.04x faster                                                     |
| regex_compile                    | 102 ms                                                             | 99.1 ms: 1.03x faster                                                    |
| logging_simple                   | 5.06 us                                                            | 4.91 us: 1.03x faster                                                    |
| nqueens                          | 58.3 ms                                                            | 56.8 ms: 1.03x faster                                                    |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 334 ms: 1.03x faster                                                     |
| json                             | 3.50 ms                                                            | 3.42 ms: 1.02x faster                                                    |
| networkx_shortest_path           | 454 ms                                                             | 443 ms: 1.02x faster                                                     |
| unpickle                         | 10.8 us                                                            | 10.6 us: 1.02x faster                                                    |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 41.2 ms: 1.02x faster                                                    |
| telco                            | 5.37 ms                                                            | 5.28 ms: 1.02x faster                                                    |
| xml_etree_process                | 49.9 ms                                                            | 49.1 ms: 1.02x faster                                                    |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.02x faster                                                   |
| logging_format                   | 5.62 us                                                            | 5.55 us: 1.01x faster                                                    |
| sympy_integrate                  | 15.4 ms                                                            | 15.2 ms: 1.01x faster                                                    |
| asyncio_websockets               | 313 ms                                                             | 310 ms: 1.01x faster                                                     |
| json_loads                       | 18.2 us                                                            | 18.1 us: 1.00x faster                                                    |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 83.9 ms: 1.00x slower                                                    |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                     |
| mypy2                            | 741 ms                                                             | 747 ms: 1.01x slower                                                     |
| raytrace                         | 197 ms                                                             | 199 ms: 1.01x slower                                                     |
| thread_counter_naive             | 23.7 ms                                                            | 24.0 ms: 1.01x slower                                                    |
| meteor_contest                   | 85.7 ms                                                            | 86.7 ms: 1.01x slower                                                    |
| python_startup                   | 9.51 ms                                                            | 9.64 ms: 1.01x slower                                                    |
| crypto_pyaes                     | 55.6 ms                                                            | 56.4 ms: 1.01x slower                                                    |
| argparse_subparsers              | 449 us                                                             | 458 us: 1.02x slower                                                     |
| thread_mandelbrot_optimized      | 189 ms                                                             | 193 ms: 1.02x slower                                                     |
| pickle_dict                      | 19.0 us                                                            | 19.5 us: 1.02x slower                                                    |
| fastapi_http                     | 215 ms                                                             | 221 ms: 1.03x slower                                                     |
| thread_mandelbrot_naive          | 190 ms                                                             | 195 ms: 1.03x slower                                                     |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.94 ms: 1.03x slower                                                    |
| unpickle_pure_python             | 161 us                                                             | 166 us: 1.03x slower                                                     |
| sympy_str                        | 193 ms                                                             | 199 ms: 1.03x slower                                                     |
| xml_etree_parse                  | 121 ms                                                             | 125 ms: 1.03x slower                                                     |
| sympy_expand                     | 331 ms                                                             | 343 ms: 1.03x slower                                                     |
| deltablue                        | 2.59 ms                                                            | 2.68 ms: 1.03x slower                                                    |
| base64_small                     | 222 us                                                             | 230 us: 1.04x slower                                                     |
| pprint_pformat                   | 1.13 sec                                                           | 1.17 sec: 1.04x slower                                                   |
| typing_runtime_protocols         | 112 us                                                             | 117 us: 1.04x slower                                                     |
| sqlalchemy_imperative            | 13.9 ms                                                            | 14.5 ms: 1.04x slower                                                    |
| pickle_pure_python               | 245 us                                                             | 256 us: 1.04x slower                                                     |
| pycparser                        | 901 ms                                                             | 942 ms: 1.04x slower                                                     |
| sympy_sum                        | 104 ms                                                             | 109 ms: 1.05x slower                                                     |
| pprint_safe_repr                 | 546 ms                                                             | 574 ms: 1.05x slower                                                     |
| xdsl_constant_fold               | 36.4 ms                                                            | 38.6 ms: 1.06x slower                                                    |
| django_template                  | 28.8 ms                                                            | 30.7 ms: 1.07x slower                                                    |
| regex_v8                         | 15.0 ms                                                            | 16.2 ms: 1.08x slower                                                    |
| generators                       | 22.2 ms                                                            | 24.3 ms: 1.10x slower                                                    |
| thread_counter_optimized         | 19.7 ms                                                            | 21.7 ms: 1.10x slower                                                    |
| scimark_lu                       | 70.2 ms                                                            | 77.6 ms: 1.11x slower                                                    |
| thread_memo_optimized            | 16.8 ms                                                            | 18.6 ms: 1.11x slower                                                    |
| mako                             | 8.30 ms                                                            | 9.25 ms: 1.11x slower                                                    |
| coverage                         | 55.0 ms                                                            | 61.7 ms: 1.12x slower                                                    |
| pickle                           | 7.21 us                                                            | 8.25 us: 1.14x slower                                                    |
| thread_accumulate_naive          | 36.5 ms                                                            | 43.6 ms: 1.19x slower                                                    |
| thread_accumulate_optimized      | 35.3 ms                                                            | 42.9 ms: 1.21x slower                                                    |
| pickle_list                      | 2.66 us                                                            | 3.26 us: 1.23x slower                                                    |
| thread_pipeline_optimized        | 22.8 ms                                                            | 28.2 ms: 1.24x slower                                                    |
| unpack_sequence                  | 26.4 ns                                                            | 33.8 ns: 1.28x slower                                                    |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 416 ms: 1.38x slower                                                     |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 283 ms: 1.62x slower                                                     |
| async_tree_eager_tg              | 56.8 ms                                                            | 205 ms: 3.61x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.28x faster                                                             |

Benchmark hidden because not significant (5): thrift, docutils, tornado_http, decimal_factorial, networkx_k_core
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.281x faster

# HPT report

- Reliability score: 99.99% likely to be faster
- 90% likely to have a speedup of 1.03x
- 95% likely to have a speedup of 1.02x
- 99% likely to have a speedup of 1.01x

# Memory
- memory change: 1.05x