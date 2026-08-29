# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.178x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.19x slower
- Memory change: 1.33x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 14.9 ms: 1.45x slower                                              |
| docutils       | 1.98 sec                                                           | 2.25 sec: 1.14x slower                                             |
| fastapi_http   | 222 ms                                                             | 281 ms: 1.27x slower                                               |
| html5lib       | 45.3 ms                                                            | 68.9 ms: 1.52x slower                                              |
| tornado_http   | 101 ms                                                             | 112 ms: 1.11x slower                                               |
| Geometric mean | (ref)                                                              | 1.29x slower                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                             | 82.4 ms: 2.21x faster                                              |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 191 ms: 1.24x faster                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 326 ms: 1.15x faster                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 604 ms: 1.07x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.42 sec: 1.10x slower                                             |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 484 ms: 1.13x slower                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 374 ms: 1.14x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 656 ms: 1.16x slower                                               |
| asyncio_tcp                      | 324 ms                                                             | 378 ms: 1.17x slower                                               |
| async_generators                 | 231 ms                                                             | 271 ms: 1.18x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 647 ms: 1.19x slower                                               |
| coroutines                       | 15.1 ms                                                            | 18.6 ms: 1.23x slower                                              |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 531 ms: 1.24x slower                                               |
| async_tree_io                    | 549 ms                                                             | 682 ms: 1.24x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 284 ms: 1.27x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 369 ms: 1.32x slower                                               |
| async_tree_eager_memoization     | 183 ms                                                             | 242 ms: 1.32x slower                                               |
| async_tree_none                  | 233 ms                                                             | 326 ms: 1.40x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 403 ms: 1.41x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 128 ms: 1.54x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.12x slower                                                       |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 24.8 ns: 1.29x slower                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 188 ms: 1.08x slower                                               |
| decimal_pi        | 209 ms                                                             | 252 ms: 1.21x slower                                               |
| Geometric mean    | (ref)                                                              | 1.14x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 213 ms: 1.02x faster                                               |
| nbody          | 74.2 ms                                                            | 131 ms: 1.77x slower                                               |
| float          | 51.2 ms                                                            | 91.7 ms: 1.79x slower                                              |
| quadtree_nbody | 654 ms                                                             | 1.37 sec: 2.09x slower                                             |
| Geometric mean | (ref)                                                              | 1.60x slower                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                            | 14.8 ms: 1.01x faster                                              |
| regex_dna      | 147 ms                                                             | 163 ms: 1.11x slower                                               |
| regex_effbot   | 1.98 ms                                                            | 2.37 ms: 1.20x slower                                              |
| regex_compile  | 97.0 ms                                                            | 139 ms: 1.44x slower                                               |
| Geometric mean | (ref)                                                              | 1.17x slower                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| pickle_list          | 3.03 us                                                            | 2.61 us: 1.16x faster                                              |
| pickle               | 8.04 us                                                            | 7.12 us: 1.13x faster                                              |
| xml_etree_iterparse  | 85.5 ms                                                            | 80.7 ms: 1.06x faster                                              |
| pickle_dict          | 20.0 us                                                            | 19.4 us: 1.03x faster                                              |
| xml_etree_parse      | 118 ms                                                             | 115 ms: 1.02x faster                                               |
| base64_large         | 5.70 ms                                                            | 5.75 ms: 1.01x slower                                              |
| xml_etree_generate   | 68.1 ms                                                            | 73.1 ms: 1.07x slower                                              |
| json_dumps           | 7.52 ms                                                            | 8.31 ms: 1.10x slower                                              |
| json_loads           | 18.6 us                                                            | 20.7 us: 1.11x slower                                              |
| base32_large         | 289 ms                                                             | 328 ms: 1.13x slower                                               |
| base32_small         | 5.71 ms                                                            | 6.48 ms: 1.14x slower                                              |
| unpickle             | 10.5 us                                                            | 12.0 us: 1.14x slower                                              |
| unpickle_list        | 3.03 us                                                            | 3.52 us: 1.16x slower                                              |
| xml_etree_process    | 50.0 ms                                                            | 59.5 ms: 1.19x slower                                              |
| base64_small         | 227 us                                                             | 272 us: 1.20x slower                                               |
| urlsafe_base64_small | 340 us                                                             | 414 us: 1.22x slower                                               |
| base85_large         | 249 ms                                                             | 308 ms: 1.24x slower                                               |
| base85_small         | 4.66 ms                                                            | 5.82 ms: 1.25x slower                                              |
| ascii85_small        | 13.0 ms                                                            | 17.7 ms: 1.36x slower                                              |
| ascii85_large        | 681 ms                                                             | 935 ms: 1.37x slower                                               |
| tomli_loads          | 1.49 sec                                                           | 2.15 sec: 1.44x slower                                             |
| unpickle_pure_python | 163 us                                                             | 238 us: 1.46x slower                                               |
| pickle_pure_python   | 251 us                                                             | 368 us: 1.47x slower                                               |
| base16_small         | 265 us                                                             | 884 us: 3.34x slower                                               |
| base16_large         | 6.35 ms                                                            | 36.7 ms: 5.79x slower                                              |
| Geometric mean       | (ref)                                                              | 1.28x slower                                                       |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 11.4 ms: 1.15x slower                                              |
| python_startup_no_site | 6.52 ms                                                            | 7.90 ms: 1.21x slower                                              |
| Geometric mean         | (ref)                                                              | 1.18x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_xml      | 43.2 ms                                                            | 56.4 ms: 1.30x slower                                              |
| django_template | 30.5 ms                                                            | 41.1 ms: 1.35x slower                                              |
| genshi_text     | 18.0 ms                                                            | 26.7 ms: 1.48x slower                                              |
| mako            | 8.69 ms                                                            | 13.3 ms: 1.53x slower                                              |
| Geometric mean  | (ref)                                                              | 1.41x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.8 ms                                                            | 6.84 ms: 3.77x faster                                              |
| thread_accumulate_optimized | 39.5 ms                                                            | 10.7 ms: 3.70x faster                                              |
| thread_mandelbrot_optimized | 205 ms                                                             | 55.8 ms: 3.68x faster                                              |
| thread_mandelbrot_naive     | 207 ms                                                             | 57.3 ms: 3.60x faster                                              |
| thread_accumulate_naive     | 40.4 ms                                                            | 11.8 ms: 3.41x faster                                              |
| thread_counter_optimized    | 18.3 ms                                                            | 5.98 ms: 3.06x faster                                              |
| thread_memo_optimized       | 17.5 ms                                                            | 6.21 ms: 2.82x faster                                              |
| thread_montecarlo_optimized | 12.9 ms                                                            | 5.16 ms: 2.50x faster                                              |
| thread_counter_naive        | 21.2 ms                                                            | 26.5 ms: 1.25x slower                                              |
| thread_pipeline_naive       | 34.9 ms                                                            | 48.4 ms: 1.39x slower                                              |
| thread_memo_naive           | 12.4 ms                                                            | 47.9 ms: 3.86x slower                                              |
| thread_montecarlo_naive     | 14.3 ms                                                            | 64.3 ms: 4.51x slower                                              |
| Geometric mean              | (ref)                                                              | 1.66x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_pipeline_optimized        | 25.8 ms                                                            | 6.84 ms: 3.77x faster                                              |
| thread_accumulate_optimized      | 39.5 ms                                                            | 10.7 ms: 3.70x faster                                              |
| thread_mandelbrot_optimized      | 205 ms                                                             | 55.8 ms: 3.68x faster                                              |
| thread_mandelbrot_naive          | 207 ms                                                             | 57.3 ms: 3.60x faster                                              |
| thread_accumulate_naive          | 40.4 ms                                                            | 11.8 ms: 3.41x faster                                              |
| thread_counter_optimized         | 18.3 ms                                                            | 5.98 ms: 3.06x faster                                              |
| thread_memo_optimized            | 17.5 ms                                                            | 6.21 ms: 2.82x faster                                              |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 5.16 ms: 2.50x faster                                              |
| async_tree_eager_tg              | 182 ms                                                             | 82.4 ms: 2.21x faster                                              |
| argparse_many_optionals          | 34.5 ms                                                            | 17.9 ms: 1.92x faster                                              |
| argparse_subparsers              | 687 us                                                             | 540 us: 1.27x faster                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 191 ms: 1.24x faster                                               |
| gc_traversal                     | 3.36 ms                                                            | 2.75 ms: 1.22x faster                                              |
| create_gc_cycles                 | 2.02 ms                                                            | 1.68 ms: 1.20x faster                                              |
| pickle_list                      | 3.03 us                                                            | 2.61 us: 1.16x faster                                              |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 326 ms: 1.15x faster                                               |
| pickle                           | 8.04 us                                                            | 7.12 us: 1.13x faster                                              |
| xml_etree_iterparse              | 85.5 ms                                                            | 80.7 ms: 1.06x faster                                              |
| pickle_dict                      | 20.0 us                                                            | 19.4 us: 1.03x faster                                              |
| xml_etree_parse                  | 118 ms                                                             | 115 ms: 1.02x faster                                               |
| pidigits                         | 216 ms                                                             | 213 ms: 1.02x faster                                               |
| regex_v8                         | 15.0 ms                                                            | 14.8 ms: 1.01x faster                                              |
| base64_large                     | 5.70 ms                                                            | 5.75 ms: 1.01x slower                                              |
| generators                       | 24.2 ms                                                            | 25.5 ms: 1.05x slower                                              |
| async_tree_eager_io_tg           | 565 ms                                                             | 604 ms: 1.07x slower                                               |
| xml_etree_generate               | 68.1 ms                                                            | 73.1 ms: 1.07x slower                                              |
| decimal_factorial                | 174 ms                                                             | 188 ms: 1.08x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.42 sec: 1.10x slower                                             |
| json_dumps                       | 7.52 ms                                                            | 8.31 ms: 1.10x slower                                              |
| coverage                         | 54.5 ms                                                            | 60.2 ms: 1.11x slower                                              |
| regex_dna                        | 147 ms                                                             | 163 ms: 1.11x slower                                               |
| tornado_http                     | 101 ms                                                             | 112 ms: 1.11x slower                                               |
| json                             | 3.46 ms                                                            | 3.84 ms: 1.11x slower                                              |
| json_loads                       | 18.6 us                                                            | 20.7 us: 1.11x slower                                              |
| base32_large                     | 289 ms                                                             | 328 ms: 1.13x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 484 ms: 1.13x slower                                               |
| base32_small                     | 5.71 ms                                                            | 6.48 ms: 1.14x slower                                              |
| docutils                         | 1.98 sec                                                           | 2.25 sec: 1.14x slower                                             |
| unpickle                         | 10.5 us                                                            | 12.0 us: 1.14x slower                                              |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 374 ms: 1.14x slower                                               |
| python_startup                   | 9.93 ms                                                            | 11.4 ms: 1.15x slower                                              |
| networkx_k_core                  | 2.05 sec                                                           | 2.37 sec: 1.16x slower                                             |
| async_tree_eager_io              | 568 ms                                                             | 656 ms: 1.16x slower                                               |
| unpickle_list                    | 3.03 us                                                            | 3.52 us: 1.16x slower                                              |
| meteor_contest                   | 85.4 ms                                                            | 99.6 ms: 1.17x slower                                              |
| asyncio_tcp                      | 324 ms                                                             | 378 ms: 1.17x slower                                               |
| pathlib                          | 12.7 ms                                                            | 14.8 ms: 1.17x slower                                              |
| async_generators                 | 231 ms                                                             | 271 ms: 1.18x slower                                               |
| pylint                           | 222 ms                                                             | 263 ms: 1.18x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 647 ms: 1.19x slower                                               |
| nqueens                          | 59.8 ms                                                            | 70.9 ms: 1.19x slower                                              |
| networkx_shortest_path           | 447 ms                                                             | 530 ms: 1.19x slower                                               |
| sqlalchemy_imperative            | 14.8 ms                                                            | 17.6 ms: 1.19x slower                                              |
| xml_etree_process                | 50.0 ms                                                            | 59.5 ms: 1.19x slower                                              |
| base64_small                     | 227 us                                                             | 272 us: 1.20x slower                                               |
| regex_effbot                     | 1.98 ms                                                            | 2.37 ms: 1.20x slower                                              |
| networkx_connected_components    | 425 ms                                                             | 511 ms: 1.20x slower                                               |
| decimal_pi                       | 209 ms                                                             | 252 ms: 1.21x slower                                               |
| telco                            | 5.39 ms                                                            | 6.52 ms: 1.21x slower                                              |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 3.50 ms: 1.21x slower                                              |
| python_startup_no_site           | 6.52 ms                                                            | 7.90 ms: 1.21x slower                                              |
| scimark_fft                      | 211 ms                                                             | 257 ms: 1.22x slower                                               |
| urlsafe_base64_small             | 340 us                                                             | 414 us: 1.22x slower                                               |
| xdsl_constant_fold               | 36.0 ms                                                            | 44.0 ms: 1.22x slower                                              |
| pycparser                        | 878 ms                                                             | 1.08 sec: 1.23x slower                                             |
| coroutines                       | 15.1 ms                                                            | 18.6 ms: 1.23x slower                                              |
| base85_large                     | 249 ms                                                             | 308 ms: 1.24x slower                                               |
| crypto_pyaes                     | 56.7 ms                                                            | 70.1 ms: 1.24x slower                                              |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 531 ms: 1.24x slower                                               |
| async_tree_io                    | 549 ms                                                             | 682 ms: 1.24x slower                                               |
| base85_small                     | 4.66 ms                                                            | 5.82 ms: 1.25x slower                                              |
| thread_counter_naive             | 21.2 ms                                                            | 26.5 ms: 1.25x slower                                              |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.89 sec: 1.25x slower                                             |
| mypy2                            | 780 ms                                                             | 981 ms: 1.26x slower                                               |
| fastapi_http                     | 222 ms                                                             | 281 ms: 1.27x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 284 ms: 1.27x slower                                               |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 53.7 ms: 1.28x slower                                              |
| sympy_integrate                  | 15.1 ms                                                            | 19.5 ms: 1.29x slower                                              |
| noop                             | 19.2 ns                                                            | 24.8 ns: 1.29x slower                                              |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 110 ms: 1.30x slower                                               |
| fannkuch                         | 246 ms                                                             | 321 ms: 1.30x slower                                               |
| genshi_xml                       | 43.2 ms                                                            | 56.4 ms: 1.30x slower                                              |
| async_tree_memoization_tg        | 279 ms                                                             | 369 ms: 1.32x slower                                               |
| async_tree_eager_memoization     | 183 ms                                                             | 242 ms: 1.32x slower                                               |
| typing_runtime_protocols         | 115 us                                                             | 155 us: 1.34x slower                                               |
| django_template                  | 30.5 ms                                                            | 41.1 ms: 1.35x slower                                              |
| ascii85_small                    | 13.0 ms                                                            | 17.7 ms: 1.36x slower                                              |
| ascii85_large                    | 681 ms                                                             | 935 ms: 1.37x slower                                               |
| thread_pipeline_naive            | 34.9 ms                                                            | 48.4 ms: 1.39x slower                                              |
| sympy_str                        | 200 ms                                                             | 280 ms: 1.40x slower                                               |
| async_tree_none                  | 233 ms                                                             | 326 ms: 1.40x slower                                               |
| logging_format                   | 6.00 us                                                            | 8.45 us: 1.41x slower                                              |
| async_tree_memoization           | 285 ms                                                             | 403 ms: 1.41x slower                                               |
| regex_compile                    | 97.0 ms                                                            | 139 ms: 1.44x slower                                               |
| tomli_loads                      | 1.49 sec                                                           | 2.15 sec: 1.44x slower                                             |
| chameleon                        | 10.3 ms                                                            | 14.9 ms: 1.45x slower                                              |
| comprehensions                   | 11.4 us                                                            | 16.6 us: 1.46x slower                                              |
| pprint_safe_repr                 | 534 ms                                                             | 781 ms: 1.46x slower                                               |
| unpickle_pure_python             | 163 us                                                             | 238 us: 1.46x slower                                               |
| pickle_pure_python               | 251 us                                                             | 368 us: 1.47x slower                                               |
| pprint_pformat                   | 1.10 sec                                                           | 1.62 sec: 1.48x slower                                             |
| genshi_text                      | 18.0 ms                                                            | 26.7 ms: 1.48x slower                                              |
| sympy_expand                     | 344 ms                                                             | 516 ms: 1.50x slower                                               |
| pyflate                          | 309 ms                                                             | 467 ms: 1.51x slower                                               |
| html5lib                         | 45.3 ms                                                            | 68.9 ms: 1.52x slower                                              |
| richards                         | 34.7 ms                                                            | 53.1 ms: 1.53x slower                                              |
| mako                             | 8.69 ms                                                            | 13.3 ms: 1.53x slower                                              |
| richards_super                   | 40.3 ms                                                            | 61.9 ms: 1.53x slower                                              |
| logging_simple                   | 5.02 us                                                            | 7.70 us: 1.53x slower                                              |
| async_tree_eager                 | 83.0 ms                                                            | 128 ms: 1.54x slower                                               |
| thrift                           | 2.00 ms                                                            | 3.08 ms: 1.54x slower                                              |
| deepcopy_reduce                  | 2.02 us                                                            | 3.13 us: 1.55x slower                                              |
| spectral_norm                    | 64.1 ms                                                            | 99.4 ms: 1.55x slower                                              |
| sympy_sum                        | 109 ms                                                             | 171 ms: 1.57x slower                                               |
| hexiom                           | 4.50 ms                                                            | 7.08 ms: 1.57x slower                                              |
| scimark_monte_carlo              | 42.3 ms                                                            | 67.7 ms: 1.60x slower                                              |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 2.04 ms: 1.69x slower                                              |
| deepcopy                         | 198 us                                                             | 342 us: 1.73x slower                                               |
| chaos                            | 42.9 ms                                                            | 74.3 ms: 1.73x slower                                              |
| logging_silent                   | 59.2 ns                                                            | 104 ns: 1.75x slower                                               |
| deepcopy_memo                    | 19.1 us                                                            | 33.6 us: 1.76x slower                                              |
| nbody                            | 74.2 ms                                                            | 131 ms: 1.77x slower                                               |
| float                            | 51.2 ms                                                            | 91.7 ms: 1.79x slower                                              |
| sqlglot_v2_parse                 | 954 us                                                             | 1.75 ms: 1.84x slower                                              |
| raytrace                         | 201 ms                                                             | 380 ms: 1.89x slower                                               |
| deltablue                        | 2.76 ms                                                            | 5.39 ms: 1.95x slower                                              |
| scimark_sor                      | 78.2 ms                                                            | 156 ms: 2.00x slower                                               |
| scimark_lu                       | 74.7 ms                                                            | 153 ms: 2.05x slower                                               |
| quadtree_nbody                   | 654 ms                                                             | 1.37 sec: 2.09x slower                                             |
| go                               | 91.1 ms                                                            | 197 ms: 2.16x slower                                               |
| unpack_sequence                  | 35.6 ns                                                            | 83.6 ns: 2.35x slower                                              |
| mdp                              | 971 ms                                                             | 2.31 sec: 2.38x slower                                             |
| base16_small                     | 265 us                                                             | 884 us: 3.34x slower                                               |
| thread_memo_naive                | 12.4 ms                                                            | 47.9 ms: 3.86x slower                                              |
| thread_montecarlo_naive          | 14.3 ms                                                            | 64.3 ms: 4.51x slower                                              |
| base16_large                     | 6.35 ms                                                            | 36.7 ms: 5.79x slower                                              |
| Geometric mean                   | (ref)                                                              | 1.22x slower                                                       |

Benchmark hidden because not significant (1): asyncio_websockets

- Geometric mean (including insignificant results): 1.178x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.20x
- 95% likely to have a slowdown of 1.20x
- 99% likely to have a slowdown of 1.19x

# Memory
- memory change: 1.33x