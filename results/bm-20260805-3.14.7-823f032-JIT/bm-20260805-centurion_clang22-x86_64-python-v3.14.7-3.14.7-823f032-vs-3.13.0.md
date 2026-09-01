# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.047x faster
- HPT reliability: 88.32%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.09x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 11.0 ms: 1.01x faster                                              |
| docutils       | 1.89 sec                                                           | 1.97 sec: 1.04x slower                                             |
| fastapi_http   | 215 ms                                                             | 221 ms: 1.02x slower                                               |
| html5lib       | 50.9 ms                                                            | 47.9 ms: 1.06x faster                                              |
| tornado_http   | 98.9 ms                                                            | 103 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 349 ms: 1.21x faster                                               |
| coroutines                       | 18.2 ms                                                            | 15.7 ms: 1.16x faster                                              |
| async_tree_memoization           | 392 ms                                                             | 340 ms: 1.15x faster                                               |
| async_tree_none                  | 312 ms                                                             | 272 ms: 1.15x faster                                               |
| async_tree_eager_io              | 753 ms                                                             | 678 ms: 1.11x faster                                               |
| async_tree_io_tg                 | 781 ms                                                             | 710 ms: 1.10x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 201 ms: 1.10x faster                                               |
| async_tree_none_tg               | 290 ms                                                             | 272 ms: 1.07x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 686 ms: 1.07x faster                                               |
| async_tree_io                    | 743 ms                                                             | 705 ms: 1.05x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 483 ms: 1.05x faster                                               |
| asyncio_tcp                      | 316 ms                                                             | 301 ms: 1.05x faster                                               |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 478 ms: 1.03x faster                                               |
| async_tree_eager                 | 88.3 ms                                                            | 88.6 ms: 1.00x slower                                              |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                             |
| async_generators                 | 251 ms                                                             | 259 ms: 1.03x slower                                               |
| asyncio_websockets               | 313 ms                                                             | 328 ms: 1.05x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 423 ms: 1.40x slower                                               |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 288 ms: 1.65x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 211 ms: 3.71x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.05x slower                                                       |

Benchmark hidden because not significant (1): async_tree_eager_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 17.6 ns: 1.22x faster                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 209 ms: 1.09x faster                                               |
| decimal_factorial | 177 ms                                                             | 174 ms: 1.01x faster                                               |
| Geometric mean    | (ref)                                                              | 1.05x faster                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 43.9 ms: 1.35x faster                                              |
| quadtree_nbody | 675 ms                                                             | 592 ms: 1.14x faster                                               |
| nbody          | 75.8 ms                                                            | 84.0 ms: 1.11x slower                                              |
| Geometric mean | (ref)                                                              | 1.09x faster                                                       |

Benchmark hidden because not significant (1): pidigits

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_dna      | 159 ms                                                             | 146 ms: 1.09x faster                                               |
| regex_effbot   | 2.33 ms                                                            | 2.17 ms: 1.08x faster                                              |
| regex_compile  | 102 ms                                                             | 99.9 ms: 1.02x faster                                              |
| regex_v8       | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| Geometric mean | (ref)                                                              | 1.04x faster                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.26 ms: 6.81x faster                                              |
| base16_small         | 836 us                                                             | 265 us: 3.15x faster                                               |
| ascii85_large        | 824 ms                                                             | 617 ms: 1.34x faster                                               |
| ascii85_small        | 15.7 ms                                                            | 11.9 ms: 1.33x faster                                              |
| tomli_loads          | 1.77 sec                                                           | 1.44 sec: 1.23x faster                                             |
| unpickle_pure_python | 161 us                                                             | 137 us: 1.18x faster                                               |
| xml_etree_generate   | 70.6 ms                                                            | 61.8 ms: 1.14x faster                                              |
| unpickle_list        | 3.42 us                                                            | 3.02 us: 1.13x faster                                              |
| base85_large         | 267 ms                                                             | 238 ms: 1.12x faster                                               |
| base32_large         | 325 ms                                                             | 293 ms: 1.11x faster                                               |
| xml_etree_process    | 49.9 ms                                                            | 45.0 ms: 1.11x faster                                              |
| base32_small         | 6.46 ms                                                            | 5.96 ms: 1.08x faster                                              |
| base85_small         | 4.85 ms                                                            | 4.49 ms: 1.08x faster                                              |
| xml_etree_iterparse  | 86.8 ms                                                            | 82.2 ms: 1.06x faster                                              |
| unpickle             | 10.8 us                                                            | 10.6 us: 1.02x faster                                              |
| base64_large         | 5.69 ms                                                            | 5.68 ms: 1.00x faster                                              |
| urlsafe_base64_small | 328 us                                                             | 335 us: 1.02x slower                                               |
| base64_small         | 222 us                                                             | 227 us: 1.02x slower                                               |
| xml_etree_parse      | 121 ms                                                             | 124 ms: 1.02x slower                                               |
| pickle_dict          | 19.0 us                                                            | 19.5 us: 1.03x slower                                              |
| pickle_pure_python   | 245 us                                                             | 258 us: 1.05x slower                                               |
| json_loads           | 18.2 us                                                            | 19.3 us: 1.06x slower                                              |
| json_dumps           | 7.26 ms                                                            | 7.83 ms: 1.08x slower                                              |
| pickle               | 7.21 us                                                            | 8.03 us: 1.11x slower                                              |
| pickle_list          | 2.66 us                                                            | 3.19 us: 1.20x slower                                              |
| Geometric mean       | (ref)                                                              | 1.19x faster                                                       |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.56 ms: 1.01x slower                                              |
| python_startup         | 9.51 ms                                                            | 10.00 ms: 1.05x slower                                             |
| Geometric mean         | (ref)                                                              | 1.03x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 18.9 ms: 1.12x faster                                              |
| mako            | 8.30 ms                                                            | 7.44 ms: 1.12x faster                                              |
| genshi_xml      | 46.3 ms                                                            | 45.1 ms: 1.03x faster                                              |
| django_template | 28.8 ms                                                            | 31.7 ms: 1.10x slower                                              |
| Geometric mean  | (ref)                                                              | 1.04x faster                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 11.2 ms: 3.38x faster                                              |
| thread_pipeline_naive       | 49.8 ms                                                            | 33.6 ms: 1.48x faster                                              |
| thread_counter_naive        | 23.7 ms                                                            | 20.8 ms: 1.14x faster                                              |
| thread_counter_optimized    | 19.7 ms                                                            | 17.7 ms: 1.12x faster                                              |
| thread_memo_optimized       | 16.8 ms                                                            | 16.2 ms: 1.04x faster                                              |
| thread_accumulate_naive     | 36.5 ms                                                            | 36.8 ms: 1.01x slower                                              |
| thread_montecarlo_optimized | 14.2 ms                                                            | 14.4 ms: 1.02x slower                                              |
| thread_accumulate_optimized | 35.3 ms                                                            | 35.9 ms: 1.02x slower                                              |
| thread_pipeline_optimized   | 22.8 ms                                                            | 23.1 ms: 1.02x slower                                              |
| thread_montecarlo_naive     | 18.1 ms                                                            | 18.5 ms: 1.02x slower                                              |
| thread_mandelbrot_naive     | 190 ms                                                             | 202 ms: 1.07x slower                                               |
| thread_mandelbrot_optimized | 189 ms                                                             | 204 ms: 1.08x slower                                               |
| Geometric mean              | (ref)                                                              | 1.15x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.26 ms: 6.81x faster                                              |
| thread_memo_naive                | 37.9 ms                                                            | 11.2 ms: 3.38x faster                                              |
| base16_small                     | 836 us                                                             | 265 us: 3.15x faster                                               |
| mdp                              | 2.05 sec                                                           | 991 ms: 2.07x faster                                               |
| argparse_many_optionals          | 12.9 ms                                                            | 8.38 ms: 1.54x faster                                              |
| thread_pipeline_naive            | 49.8 ms                                                            | 33.6 ms: 1.48x faster                                              |
| deepcopy_memo                    | 27.8 us                                                            | 19.5 us: 1.42x faster                                              |
| float                            | 59.2 ms                                                            | 43.9 ms: 1.35x faster                                              |
| ascii85_large                    | 824 ms                                                             | 617 ms: 1.34x faster                                               |
| ascii85_small                    | 15.7 ms                                                            | 11.9 ms: 1.33x faster                                              |
| richards                         | 38.2 ms                                                            | 29.4 ms: 1.30x faster                                              |
| deepcopy                         | 267 us                                                             | 207 us: 1.29x faster                                               |
| richards_super                   | 43.8 ms                                                            | 34.8 ms: 1.26x faster                                              |
| scimark_sor                      | 96.2 ms                                                            | 76.8 ms: 1.25x faster                                              |
| go                               | 129 ms                                                             | 105 ms: 1.23x faster                                               |
| tomli_loads                      | 1.77 sec                                                           | 1.44 sec: 1.23x faster                                             |
| scimark_fft                      | 216 ms                                                             | 177 ms: 1.22x faster                                               |
| pyflate                          | 374 ms                                                             | 307 ms: 1.22x faster                                               |
| noop                             | 21.4 ns                                                            | 17.6 ns: 1.22x faster                                              |
| async_tree_memoization_tg        | 421 ms                                                             | 349 ms: 1.21x faster                                               |
| deltablue                        | 2.59 ms                                                            | 2.17 ms: 1.19x faster                                              |
| unpickle_pure_python             | 161 us                                                             | 137 us: 1.18x faster                                               |
| spectral_norm                    | 68.6 ms                                                            | 59.2 ms: 1.16x faster                                              |
| coroutines                       | 18.2 ms                                                            | 15.7 ms: 1.16x faster                                              |
| async_tree_memoization           | 392 ms                                                             | 340 ms: 1.15x faster                                               |
| async_tree_none                  | 312 ms                                                             | 272 ms: 1.15x faster                                               |
| xml_etree_generate               | 70.6 ms                                                            | 61.8 ms: 1.14x faster                                              |
| quadtree_nbody                   | 675 ms                                                             | 592 ms: 1.14x faster                                               |
| thread_counter_naive             | 23.7 ms                                                            | 20.8 ms: 1.14x faster                                              |
| deepcopy_reduce                  | 2.36 us                                                            | 2.07 us: 1.14x faster                                              |
| unpickle_list                    | 3.42 us                                                            | 3.02 us: 1.13x faster                                              |
| fannkuch                         | 287 ms                                                             | 256 ms: 1.12x faster                                               |
| base85_large                     | 267 ms                                                             | 238 ms: 1.12x faster                                               |
| genshi_text                      | 21.1 ms                                                            | 18.9 ms: 1.12x faster                                              |
| mako                             | 8.30 ms                                                            | 7.44 ms: 1.12x faster                                              |
| thread_counter_optimized         | 19.7 ms                                                            | 17.7 ms: 1.12x faster                                              |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.03 sec: 1.11x faster                                             |
| async_tree_eager_io              | 753 ms                                                             | 678 ms: 1.11x faster                                               |
| base32_large                     | 325 ms                                                             | 293 ms: 1.11x faster                                               |
| xml_etree_process                | 49.9 ms                                                            | 45.0 ms: 1.11x faster                                              |
| async_tree_io_tg                 | 781 ms                                                             | 710 ms: 1.10x faster                                               |
| async_tree_eager_memoization     | 221 ms                                                             | 201 ms: 1.10x faster                                               |
| decimal_pi                       | 228 ms                                                             | 209 ms: 1.09x faster                                               |
| regex_dna                        | 159 ms                                                             | 146 ms: 1.09x faster                                               |
| base32_small                     | 6.46 ms                                                            | 5.96 ms: 1.08x faster                                              |
| base85_small                     | 4.85 ms                                                            | 4.49 ms: 1.08x faster                                              |
| regex_effbot                     | 2.33 ms                                                            | 2.17 ms: 1.08x faster                                              |
| async_tree_none_tg               | 290 ms                                                             | 272 ms: 1.07x faster                                               |
| async_tree_eager_io_tg           | 731 ms                                                             | 686 ms: 1.07x faster                                               |
| html5lib                         | 50.9 ms                                                            | 47.9 ms: 1.06x faster                                              |
| xml_etree_iterparse              | 86.8 ms                                                            | 82.2 ms: 1.06x faster                                              |
| async_tree_io                    | 743 ms                                                             | 705 ms: 1.05x faster                                               |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 483 ms: 1.05x faster                                               |
| asyncio_tcp                      | 316 ms                                                             | 301 ms: 1.05x faster                                               |
| thread_memo_optimized            | 16.8 ms                                                            | 16.2 ms: 1.04x faster                                              |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 478 ms: 1.03x faster                                               |
| genshi_xml                       | 46.3 ms                                                            | 45.1 ms: 1.03x faster                                              |
| regex_compile                    | 102 ms                                                             | 99.9 ms: 1.02x faster                                              |
| unpickle                         | 10.8 us                                                            | 10.6 us: 1.02x faster                                              |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.80 ms: 1.02x faster                                              |
| networkx_connected_components    | 443 ms                                                             | 434 ms: 1.02x faster                                               |
| chaos                            | 43.6 ms                                                            | 42.8 ms: 1.02x faster                                              |
| chameleon                        | 11.1 ms                                                            | 11.0 ms: 1.01x faster                                              |
| decimal_factorial                | 177 ms                                                             | 174 ms: 1.01x faster                                               |
| coverage                         | 55.0 ms                                                            | 54.4 ms: 1.01x faster                                              |
| networkx_shortest_path           | 454 ms                                                             | 451 ms: 1.01x faster                                               |
| base64_large                     | 5.69 ms                                                            | 5.68 ms: 1.00x faster                                              |
| async_tree_eager                 | 88.3 ms                                                            | 88.6 ms: 1.00x slower                                              |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.29 sec: 1.01x slower                                             |
| thread_accumulate_naive          | 36.5 ms                                                            | 36.8 ms: 1.01x slower                                              |
| python_startup_no_site           | 6.49 ms                                                            | 6.56 ms: 1.01x slower                                              |
| meteor_contest                   | 85.7 ms                                                            | 86.8 ms: 1.01x slower                                              |
| hexiom                           | 4.75 ms                                                            | 4.81 ms: 1.01x slower                                              |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 14.4 ms: 1.02x slower                                              |
| thread_accumulate_optimized      | 35.3 ms                                                            | 35.9 ms: 1.02x slower                                              |
| thrift                           | 2.07 ms                                                            | 2.11 ms: 1.02x slower                                              |
| thread_pipeline_optimized        | 22.8 ms                                                            | 23.1 ms: 1.02x slower                                              |
| thread_montecarlo_naive          | 18.1 ms                                                            | 18.5 ms: 1.02x slower                                              |
| json                             | 3.50 ms                                                            | 3.57 ms: 1.02x slower                                              |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 43.0 ms: 1.02x slower                                              |
| urlsafe_base64_small             | 328 us                                                             | 335 us: 1.02x slower                                               |
| telco                            | 5.37 ms                                                            | 5.49 ms: 1.02x slower                                              |
| base64_small                     | 222 us                                                             | 227 us: 1.02x slower                                               |
| xml_etree_parse                  | 121 ms                                                             | 124 ms: 1.02x slower                                               |
| fastapi_http                     | 215 ms                                                             | 221 ms: 1.02x slower                                               |
| pickle_dict                      | 19.0 us                                                            | 19.5 us: 1.03x slower                                              |
| regex_v8                         | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| sympy_integrate                  | 15.4 ms                                                            | 15.9 ms: 1.03x slower                                              |
| logging_simple                   | 5.06 us                                                            | 5.21 us: 1.03x slower                                              |
| logging_format                   | 5.62 us                                                            | 5.80 us: 1.03x slower                                              |
| async_generators                 | 251 ms                                                             | 259 ms: 1.03x slower                                               |
| gc_traversal                     | 3.20 ms                                                            | 3.30 ms: 1.03x slower                                              |
| sqlglot_v2_parse                 | 979 us                                                             | 1.01 ms: 1.03x slower                                              |
| pathlib                          | 12.2 ms                                                            | 12.6 ms: 1.03x slower                                              |
| nqueens                          | 58.3 ms                                                            | 60.8 ms: 1.04x slower                                              |
| crypto_pyaes                     | 55.6 ms                                                            | 58.0 ms: 1.04x slower                                              |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.27 ms: 1.04x slower                                              |
| docutils                         | 1.89 sec                                                           | 1.97 sec: 1.04x slower                                             |
| tornado_http                     | 98.9 ms                                                            | 103 ms: 1.04x slower                                               |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 87.4 ms: 1.05x slower                                              |
| asyncio_websockets               | 313 ms                                                             | 328 ms: 1.05x slower                                               |
| pylint                           | 226 ms                                                             | 237 ms: 1.05x slower                                               |
| python_startup                   | 9.51 ms                                                            | 10.00 ms: 1.05x slower                                             |
| pickle_pure_python               | 245 us                                                             | 258 us: 1.05x slower                                               |
| xdsl_constant_fold               | 36.4 ms                                                            | 38.4 ms: 1.06x slower                                              |
| typing_runtime_protocols         | 112 us                                                             | 118 us: 1.06x slower                                               |
| raytrace                         | 197 ms                                                             | 208 ms: 1.06x slower                                               |
| json_loads                       | 18.2 us                                                            | 19.3 us: 1.06x slower                                              |
| comprehensions                   | 11.4 us                                                            | 12.2 us: 1.06x slower                                              |
| scimark_lu                       | 70.2 ms                                                            | 74.7 ms: 1.06x slower                                              |
| generators                       | 22.2 ms                                                            | 23.6 ms: 1.06x slower                                              |
| thread_mandelbrot_naive          | 190 ms                                                             | 202 ms: 1.07x slower                                               |
| create_gc_cycles                 | 1.77 ms                                                            | 1.90 ms: 1.07x slower                                              |
| sympy_sum                        | 104 ms                                                             | 113 ms: 1.08x slower                                               |
| json_dumps                       | 7.26 ms                                                            | 7.83 ms: 1.08x slower                                              |
| thread_mandelbrot_optimized      | 189 ms                                                             | 204 ms: 1.08x slower                                               |
| sympy_expand                     | 331 ms                                                             | 359 ms: 1.08x slower                                               |
| sympy_str                        | 193 ms                                                             | 209 ms: 1.08x slower                                               |
| django_template                  | 28.8 ms                                                            | 31.7 ms: 1.10x slower                                              |
| pycparser                        | 901 ms                                                             | 997 ms: 1.11x slower                                               |
| scimark_monte_carlo              | 47.2 ms                                                            | 52.3 ms: 1.11x slower                                              |
| nbody                            | 75.8 ms                                                            | 84.0 ms: 1.11x slower                                              |
| pickle                           | 7.21 us                                                            | 8.03 us: 1.11x slower                                              |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.6 ms: 1.12x slower                                              |
| argparse_subparsers              | 449 us                                                             | 534 us: 1.19x slower                                               |
| pickle_list                      | 2.66 us                                                            | 3.19 us: 1.20x slower                                              |
| pprint_safe_repr                 | 546 ms                                                             | 667 ms: 1.22x slower                                               |
| pprint_pformat                   | 1.13 sec                                                           | 1.39 sec: 1.23x slower                                             |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 423 ms: 1.40x slower                                               |
| mypy2                            | 741 ms                                                             | 1.09 sec: 1.47x slower                                             |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 288 ms: 1.65x slower                                               |
| async_tree_eager_tg              | 56.8 ms                                                            | 211 ms: 3.71x slower                                               |
| unpack_sequence                  | 26.4 ns                                                            | 107 ns: 4.03x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.04x faster                                                       |

Benchmark hidden because not significant (4): logging_silent, pidigits, networkx_k_core, async_tree_eager_cpu_io_mixed

- Geometric mean (including insignificant results): 1.047x faster

# HPT report

- Reliability score: 88.32% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.09x