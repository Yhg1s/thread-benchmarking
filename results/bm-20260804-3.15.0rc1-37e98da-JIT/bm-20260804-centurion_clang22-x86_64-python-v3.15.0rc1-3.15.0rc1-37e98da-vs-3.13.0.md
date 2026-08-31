# Results vs. 3.13.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.361x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.05x faster
- Memory change: 1.17x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.5 ms: 1.06x faster                                                    |
| docutils       | 1.89 sec                                                           | 1.97 sec: 1.05x slower                                                   |
| fastapi_http   | 215 ms                                                             | 208 ms: 1.04x faster                                                     |
| html5lib       | 50.9 ms                                                            | 47.6 ms: 1.07x faster                                                    |
| tornado_http   | 98.9 ms                                                            | 102 ms: 1.03x slower                                                     |
| Geometric mean | (ref)                                                              | 1.02x faster                                                             |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 313 ms: 1.34x faster                                                     |
| async_tree_none                  | 312 ms                                                             | 233 ms: 1.34x faster                                                     |
| async_tree_memoization           | 392 ms                                                             | 300 ms: 1.31x faster                                                     |
| async_tree_eager_io              | 753 ms                                                             | 606 ms: 1.24x faster                                                     |
| async_tree_io_tg                 | 781 ms                                                             | 636 ms: 1.23x faster                                                     |
| async_tree_none_tg               | 290 ms                                                             | 236 ms: 1.23x faster                                                     |
| async_tree_io                    | 743 ms                                                             | 621 ms: 1.20x faster                                                     |
| async_tree_eager_memoization     | 221 ms                                                             | 185 ms: 1.19x faster                                                     |
| asyncio_tcp                      | 316 ms                                                             | 271 ms: 1.17x faster                                                     |
| coroutines                       | 18.2 ms                                                            | 15.8 ms: 1.16x faster                                                    |
| async_tree_eager_io_tg           | 731 ms                                                             | 635 ms: 1.15x faster                                                     |
| async_tree_eager                 | 88.3 ms                                                            | 78.1 ms: 1.13x faster                                                    |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 451 ms: 1.12x faster                                                     |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 440 ms: 1.12x faster                                                     |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 332 ms: 1.03x faster                                                     |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.01x faster                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 410 ms: 1.36x slower                                                     |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 270 ms: 1.54x slower                                                     |
| async_tree_eager_tg              | 56.8 ms                                                            | 192 ms: 3.37x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.03x faster                                                             |

Benchmark hidden because not significant (2): asyncio_websockets, async_generators

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 17.5 ns: 1.22x faster                                                    |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 205 ms: 1.11x faster                                                     |
| decimal_factorial | 177 ms                                                             | 175 ms: 1.01x faster                                                     |
| Geometric mean    | (ref)                                                              | 1.06x faster                                                             |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| nbody          | 75.8 ms                                                            | 43.8 ms: 1.73x faster                                                    |
| float          | 59.2 ms                                                            | 40.0 ms: 1.48x faster                                                    |
| quadtree_nbody | 675 ms                                                             | 552 ms: 1.22x faster                                                     |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x slower                                                     |
| Geometric mean | (ref)                                                              | 1.33x faster                                                             |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| regex_compile  | 102 ms                                                             | 88.1 ms: 1.16x faster                                                    |
| regex_dna      | 159 ms                                                             | 152 ms: 1.04x faster                                                     |
| regex_effbot   | 2.33 ms                                                            | 2.28 ms: 1.02x faster                                                    |
| regex_v8       | 15.0 ms                                                            | 15.5 ms: 1.04x slower                                                    |
| Geometric mean | (ref)                                                              | 1.05x faster                                                             |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large         | 325 ms                                                             | 1.90 ms: 171.10x faster                                                  |
| ascii85_large        | 824 ms                                                             | 13.8 ms: 59.85x faster                                                   |
| base85_large         | 267 ms                                                             | 5.13 ms: 52.03x faster                                                   |
| base32_small         | 6.46 ms                                                            | 159 us: 40.57x faster                                                    |
| ascii85_small        | 15.7 ms                                                            | 490 us: 32.09x faster                                                    |
| base85_small         | 4.85 ms                                                            | 183 us: 26.42x faster                                                    |
| base16_large         | 42.7 ms                                                            | 10.1 ms: 4.23x faster                                                    |
| base64_large         | 5.69 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| base16_small         | 836 us                                                             | 354 us: 2.36x faster                                                     |
| urlsafe_base64_small | 328 us                                                             | 210 us: 1.56x faster                                                     |
| tomli_loads          | 1.77 sec                                                           | 1.37 sec: 1.29x faster                                                   |
| base64_small         | 222 us                                                             | 172 us: 1.29x faster                                                     |
| unpickle_pure_python | 161 us                                                             | 131 us: 1.24x faster                                                     |
| json_dumps           | 7.26 ms                                                            | 6.01 ms: 1.21x faster                                                    |
| xml_etree_process    | 49.9 ms                                                            | 42.6 ms: 1.17x faster                                                    |
| xml_etree_generate   | 70.6 ms                                                            | 61.9 ms: 1.14x faster                                                    |
| unpickle_list        | 3.42 us                                                            | 3.02 us: 1.14x faster                                                    |
| pickle_pure_python   | 245 us                                                             | 217 us: 1.13x faster                                                     |
| xml_etree_iterparse  | 86.8 ms                                                            | 80.9 ms: 1.07x faster                                                    |
| unpickle             | 10.8 us                                                            | 10.6 us: 1.02x faster                                                    |
| json_loads           | 18.2 us                                                            | 17.9 us: 1.02x faster                                                    |
| xml_etree_parse      | 121 ms                                                             | 122 ms: 1.01x slower                                                     |
| pickle_dict          | 19.0 us                                                            | 19.8 us: 1.04x slower                                                    |
| pickle               | 7.21 us                                                            | 8.19 us: 1.14x slower                                                    |
| pickle_list          | 2.66 us                                                            | 3.31 us: 1.24x slower                                                    |
| Geometric mean       | (ref)                                                              | 3.17x faster                                                             |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.12 ms: 1.06x faster                                                    |
| python_startup         | 9.51 ms                                                            | 9.76 ms: 1.03x slower                                                    |
| Geometric mean         | (ref)                                                              | 1.02x faster                                                             |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| mako            | 8.30 ms                                                            | 7.28 ms: 1.14x faster                                                    |
| django_template | 28.8 ms                                                            | 34.8 ms: 1.21x slower                                                    |
| Geometric mean  | (ref)                                                              | 1.03x slower                                                             |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 8.30 ms: 4.56x faster                                                    |
| thread_pipeline_naive       | 49.8 ms                                                            | 31.6 ms: 1.58x faster                                                    |
| thread_montecarlo_naive     | 18.1 ms                                                            | 15.3 ms: 1.18x faster                                                    |
| thread_counter_naive        | 23.7 ms                                                            | 20.5 ms: 1.16x faster                                                    |
| thread_counter_optimized    | 19.7 ms                                                            | 18.7 ms: 1.06x faster                                                    |
| thread_mandelbrot_naive     | 190 ms                                                             | 186 ms: 1.02x faster                                                     |
| thread_mandelbrot_optimized | 189 ms                                                             | 190 ms: 1.01x slower                                                     |
| thread_memo_optimized       | 16.8 ms                                                            | 17.0 ms: 1.01x slower                                                    |
| thread_accumulate_naive     | 36.5 ms                                                            | 40.2 ms: 1.10x slower                                                    |
| thread_pipeline_optimized   | 22.8 ms                                                            | 25.6 ms: 1.13x slower                                                    |
| thread_accumulate_optimized | 35.3 ms                                                            | 40.0 ms: 1.13x slower                                                    |
| Geometric mean              | (ref)                                                              | 1.18x faster                                                             |

Benchmark hidden because not significant (1): thread_montecarlo_optimized

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260804-centurion_clang22-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------------:|
| base32_large                     | 325 ms                                                             | 1.90 ms: 171.10x faster                                                  |
| ascii85_large                    | 824 ms                                                             | 13.8 ms: 59.85x faster                                                   |
| base85_large                     | 267 ms                                                             | 5.13 ms: 52.03x faster                                                   |
| base32_small                     | 6.46 ms                                                            | 159 us: 40.57x faster                                                    |
| ascii85_small                    | 15.7 ms                                                            | 490 us: 32.09x faster                                                    |
| base85_small                     | 4.85 ms                                                            | 183 us: 26.42x faster                                                    |
| thread_memo_naive                | 37.9 ms                                                            | 8.30 ms: 4.56x faster                                                    |
| base16_large                     | 42.7 ms                                                            | 10.1 ms: 4.23x faster                                                    |
| base64_large                     | 5.69 ms                                                            | 1.58 ms: 3.60x faster                                                    |
| base16_small                     | 836 us                                                             | 354 us: 2.36x faster                                                     |
| richards_super                   | 43.8 ms                                                            | 18.8 ms: 2.33x faster                                                    |
| richards                         | 38.2 ms                                                            | 16.5 ms: 2.32x faster                                                    |
| pylint                           | 226 ms                                                             | 105 ms: 2.16x faster                                                     |
| mdp                              | 2.05 sec                                                           | 1.02 sec: 2.01x faster                                                   |
| scimark_sor                      | 96.2 ms                                                            | 50.8 ms: 1.89x faster                                                    |
| deepcopy_memo                    | 27.8 us                                                            | 15.4 us: 1.80x faster                                                    |
| nbody                            | 75.8 ms                                                            | 43.8 ms: 1.73x faster                                                    |
| argparse_many_optionals          | 12.9 ms                                                            | 8.08 ms: 1.60x faster                                                    |
| thread_pipeline_naive            | 49.8 ms                                                            | 31.6 ms: 1.58x faster                                                    |
| go                               | 129 ms                                                             | 82.5 ms: 1.57x faster                                                    |
| urlsafe_base64_small             | 328 us                                                             | 210 us: 1.56x faster                                                     |
| float                            | 59.2 ms                                                            | 40.0 ms: 1.48x faster                                                    |
| spectral_norm                    | 68.6 ms                                                            | 47.7 ms: 1.44x faster                                                    |
| scimark_lu                       | 70.2 ms                                                            | 49.0 ms: 1.43x faster                                                    |
| pyflate                          | 374 ms                                                             | 264 ms: 1.42x faster                                                     |
| fannkuch                         | 287 ms                                                             | 206 ms: 1.40x faster                                                     |
| async_tree_memoization_tg        | 421 ms                                                             | 313 ms: 1.34x faster                                                     |
| async_tree_none                  | 312 ms                                                             | 233 ms: 1.34x faster                                                     |
| async_tree_memoization           | 392 ms                                                             | 300 ms: 1.31x faster                                                     |
| deepcopy                         | 267 us                                                             | 206 us: 1.30x faster                                                     |
| tomli_loads                      | 1.77 sec                                                           | 1.37 sec: 1.29x faster                                                   |
| base64_small                     | 222 us                                                             | 172 us: 1.29x faster                                                     |
| scimark_fft                      | 216 ms                                                             | 169 ms: 1.28x faster                                                     |
| scimark_monte_carlo              | 47.2 ms                                                            | 37.2 ms: 1.27x faster                                                    |
| deltablue                        | 2.59 ms                                                            | 2.05 ms: 1.26x faster                                                    |
| async_tree_eager_io              | 753 ms                                                             | 606 ms: 1.24x faster                                                     |
| unpickle_pure_python             | 161 us                                                             | 131 us: 1.24x faster                                                     |
| async_tree_io_tg                 | 781 ms                                                             | 636 ms: 1.23x faster                                                     |
| async_tree_none_tg               | 290 ms                                                             | 236 ms: 1.23x faster                                                     |
| noop                             | 21.4 ns                                                            | 17.5 ns: 1.22x faster                                                    |
| quadtree_nbody                   | 675 ms                                                             | 552 ms: 1.22x faster                                                     |
| pathlib                          | 12.2 ms                                                            | 10.0 ms: 1.22x faster                                                    |
| json_dumps                       | 7.26 ms                                                            | 6.01 ms: 1.21x faster                                                    |
| async_tree_io                    | 743 ms                                                             | 621 ms: 1.20x faster                                                     |
| async_tree_eager_memoization     | 221 ms                                                             | 185 ms: 1.19x faster                                                     |
| nqueens                          | 58.3 ms                                                            | 49.1 ms: 1.19x faster                                                    |
| thread_montecarlo_naive          | 18.1 ms                                                            | 15.3 ms: 1.18x faster                                                    |
| comprehensions                   | 11.4 us                                                            | 9.75 us: 1.17x faster                                                    |
| xml_etree_process                | 49.9 ms                                                            | 42.6 ms: 1.17x faster                                                    |
| asyncio_tcp                      | 316 ms                                                             | 271 ms: 1.17x faster                                                     |
| regex_compile                    | 102 ms                                                             | 88.1 ms: 1.16x faster                                                    |
| sqlglot_v2_parse                 | 979 us                                                             | 844 us: 1.16x faster                                                     |
| thread_counter_naive             | 23.7 ms                                                            | 20.5 ms: 1.16x faster                                                    |
| coroutines                       | 18.2 ms                                                            | 15.8 ms: 1.16x faster                                                    |
| async_tree_eager_io_tg           | 731 ms                                                             | 635 ms: 1.15x faster                                                     |
| logging_simple                   | 5.06 us                                                            | 4.42 us: 1.14x faster                                                    |
| xml_etree_generate               | 70.6 ms                                                            | 61.9 ms: 1.14x faster                                                    |
| telco                            | 5.37 ms                                                            | 4.70 ms: 1.14x faster                                                    |
| mako                             | 8.30 ms                                                            | 7.28 ms: 1.14x faster                                                    |
| unpickle_list                    | 3.42 us                                                            | 3.02 us: 1.14x faster                                                    |
| async_tree_eager                 | 88.3 ms                                                            | 78.1 ms: 1.13x faster                                                    |
| pickle_pure_python               | 245 us                                                             | 217 us: 1.13x faster                                                     |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 451 ms: 1.12x faster                                                     |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 440 ms: 1.12x faster                                                     |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.01 sec: 1.12x faster                                                   |
| logging_format                   | 5.62 us                                                            | 5.02 us: 1.12x faster                                                    |
| hexiom                           | 4.75 ms                                                            | 4.25 ms: 1.12x faster                                                    |
| decimal_pi                       | 228 ms                                                             | 205 ms: 1.11x faster                                                     |
| crypto_pyaes                     | 55.6 ms                                                            | 50.4 ms: 1.10x faster                                                    |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 39.1 ms: 1.08x faster                                                    |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.13 ms: 1.07x faster                                                    |
| xml_etree_iterparse              | 86.8 ms                                                            | 80.9 ms: 1.07x faster                                                    |
| html5lib                         | 50.9 ms                                                            | 47.6 ms: 1.07x faster                                                    |
| python_startup_no_site           | 6.49 ms                                                            | 6.12 ms: 1.06x faster                                                    |
| thrift                           | 2.07 ms                                                            | 1.96 ms: 1.06x faster                                                    |
| thread_counter_optimized         | 19.7 ms                                                            | 18.7 ms: 1.06x faster                                                    |
| chameleon                        | 11.1 ms                                                            | 10.5 ms: 1.06x faster                                                    |
| chaos                            | 43.6 ms                                                            | 41.3 ms: 1.06x faster                                                    |
| json                             | 3.50 ms                                                            | 3.32 ms: 1.06x faster                                                    |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 79.3 ms: 1.05x faster                                                    |
| sympy_expand                     | 331 ms                                                             | 314 ms: 1.05x faster                                                     |
| raytrace                         | 197 ms                                                             | 188 ms: 1.05x faster                                                     |
| meteor_contest                   | 85.7 ms                                                            | 81.5 ms: 1.05x faster                                                    |
| gc_traversal                     | 3.20 ms                                                            | 3.07 ms: 1.04x faster                                                    |
| regex_dna                        | 159 ms                                                             | 152 ms: 1.04x faster                                                     |
| fastapi_http                     | 215 ms                                                             | 208 ms: 1.04x faster                                                     |
| create_gc_cycles                 | 1.77 ms                                                            | 1.72 ms: 1.03x faster                                                    |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 332 ms: 1.03x faster                                                     |
| typing_runtime_protocols         | 112 us                                                             | 110 us: 1.02x faster                                                     |
| regex_effbot                     | 2.33 ms                                                            | 2.28 ms: 1.02x faster                                                    |
| unpickle                         | 10.8 us                                                            | 10.6 us: 1.02x faster                                                    |
| thread_mandelbrot_naive          | 190 ms                                                             | 186 ms: 1.02x faster                                                     |
| json_loads                       | 18.2 us                                                            | 17.9 us: 1.02x faster                                                    |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.01x faster                                                   |
| networkx_connected_components    | 443 ms                                                             | 439 ms: 1.01x faster                                                     |
| decimal_factorial                | 177 ms                                                             | 175 ms: 1.01x faster                                                     |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x slower                                                     |
| thread_mandelbrot_optimized      | 189 ms                                                             | 190 ms: 1.01x slower                                                     |
| pprint_pformat                   | 1.13 sec                                                           | 1.13 sec: 1.01x slower                                                   |
| thread_memo_optimized            | 16.8 ms                                                            | 17.0 ms: 1.01x slower                                                    |
| xml_etree_parse                  | 121 ms                                                             | 122 ms: 1.01x slower                                                     |
| pprint_safe_repr                 | 546 ms                                                             | 555 ms: 1.02x slower                                                     |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.91 ms: 1.02x slower                                                    |
| python_startup                   | 9.51 ms                                                            | 9.76 ms: 1.03x slower                                                    |
| tornado_http                     | 98.9 ms                                                            | 102 ms: 1.03x slower                                                     |
| deepcopy_reduce                  | 2.36 us                                                            | 2.42 us: 1.03x slower                                                    |
| sympy_str                        | 193 ms                                                             | 198 ms: 1.03x slower                                                     |
| sqlalchemy_imperative            | 13.9 ms                                                            | 14.3 ms: 1.03x slower                                                    |
| regex_v8                         | 15.0 ms                                                            | 15.5 ms: 1.04x slower                                                    |
| pickle_dict                      | 19.0 us                                                            | 19.8 us: 1.04x slower                                                    |
| logging_silent                   | 60.1 ns                                                            | 62.5 ns: 1.04x slower                                                    |
| argparse_subparsers              | 449 us                                                             | 468 us: 1.04x slower                                                     |
| sympy_integrate                  | 15.4 ms                                                            | 16.1 ms: 1.04x slower                                                    |
| docutils                         | 1.89 sec                                                           | 1.97 sec: 1.05x slower                                                   |
| pycparser                        | 901 ms                                                             | 953 ms: 1.06x slower                                                     |
| networkx_k_core                  | 2.16 sec                                                           | 2.31 sec: 1.07x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 112 ms: 1.07x slower                                                     |
| thread_accumulate_naive          | 36.5 ms                                                            | 40.2 ms: 1.10x slower                                                    |
| thread_pipeline_optimized        | 22.8 ms                                                            | 25.6 ms: 1.13x slower                                                    |
| thread_accumulate_optimized      | 35.3 ms                                                            | 40.0 ms: 1.13x slower                                                    |
| coverage                         | 55.0 ms                                                            | 62.5 ms: 1.14x slower                                                    |
| pickle                           | 7.21 us                                                            | 8.19 us: 1.14x slower                                                    |
| generators                       | 22.2 ms                                                            | 26.0 ms: 1.17x slower                                                    |
| django_template                  | 28.8 ms                                                            | 34.8 ms: 1.21x slower                                                    |
| pickle_list                      | 2.66 us                                                            | 3.31 us: 1.24x slower                                                    |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 410 ms: 1.36x slower                                                     |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 270 ms: 1.54x slower                                                     |
| mypy2                            | 741 ms                                                             | 1.16 sec: 1.56x slower                                                   |
| unpack_sequence                  | 26.4 ns                                                            | 78.7 ns: 2.98x slower                                                    |
| async_tree_eager_tg              | 56.8 ms                                                            | 192 ms: 3.37x slower                                                     |
| Geometric mean                   | (ref)                                                              | 1.35x faster                                                             |

Benchmark hidden because not significant (5): xdsl_constant_fold, asyncio_websockets, thread_montecarlo_optimized, networkx_shortest_path, async_generators
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.361x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.07x
- 95% likely to have a speedup of 1.06x
- 99% likely to have a speedup of 1.05x

# Memory
- memory change: 1.17x