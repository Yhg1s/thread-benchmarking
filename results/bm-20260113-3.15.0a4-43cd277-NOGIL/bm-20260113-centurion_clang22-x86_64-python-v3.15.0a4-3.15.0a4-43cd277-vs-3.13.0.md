# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.066x faster
- HPT reliability: 90.88%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.60x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 12.3 ms: 1.11x slower                                                  |
| docutils       | 1.89 sec                                                           | 2.18 sec: 1.15x slower                                                 |
| fastapi_http   | 215 ms                                                             | 204 ms: 1.06x faster                                                   |
| Geometric mean | (ref)                                                              | 1.04x slower                                                           |

Benchmark hidden because not significant (2): html5lib, tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 503 ms: 1.55x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 490 ms: 1.49x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 283 ms: 1.48x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 534 ms: 1.41x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 539 ms: 1.38x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 217 ms: 1.34x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 243 ms: 1.29x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 314 ms: 1.25x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 422 ms: 1.20x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 195 ms: 1.13x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 281 ms: 1.12x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 16.6 ms: 1.10x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 451 ms: 1.09x faster                                                   |
| asyncio_websockets               | 313 ms                                                             | 288 ms: 1.09x faster                                                   |
| async_generators                 | 251 ms                                                             | 258 ms: 1.03x slower                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.36 sec: 1.06x slower                                                 |
| async_tree_eager                 | 88.3 ms                                                            | 100 ms: 1.14x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 405 ms: 1.35x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 264 ms: 1.51x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 190 ms: 3.34x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.06x faster                                                           |

Benchmark hidden because not significant (1): async_tree_eager_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 22.8 ns: 1.06x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 240 ms: 1.05x slower                                                   |
| decimal_factorial | 177 ms                                                             | 188 ms: 1.06x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 57.4 ms: 1.03x faster                                                  |
| pidigits       | 216 ms                                                             | 216 ms: 1.00x faster                                                   |
| quadtree_nbody | 675 ms                                                             | 753 ms: 1.12x slower                                                   |
| nbody          | 75.8 ms                                                            | 89.8 ms: 1.19x slower                                                  |
| Geometric mean | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 2.00 ms: 1.17x faster                                                  |
| regex_dna      | 159 ms                                                             | 145 ms: 1.09x faster                                                   |
| regex_v8       | 15.0 ms                                                            | 14.7 ms: 1.02x faster                                                  |
| regex_compile  | 102 ms                                                             | 115 ms: 1.12x slower                                                   |
| Geometric mean | (ref)                                                              | 1.04x faster                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 5.97 ms: 7.15x faster                                                  |
| base16_small         | 836 us                                                             | 263 us: 3.18x faster                                                   |
| xml_etree_iterparse  | 86.8 ms                                                            | 74.4 ms: 1.17x faster                                                  |
| xml_etree_parse      | 121 ms                                                             | 112 ms: 1.07x faster                                                   |
| base64_large         | 5.69 ms                                                            | 5.47 ms: 1.04x faster                                                  |
| json_dumps           | 7.26 ms                                                            | 7.13 ms: 1.02x faster                                                  |
| base64_small         | 222 us                                                             | 219 us: 1.01x faster                                                   |
| base32_small         | 6.46 ms                                                            | 6.52 ms: 1.01x slower                                                  |
| base32_large         | 325 ms                                                             | 330 ms: 1.01x slower                                                   |
| xml_etree_generate   | 70.6 ms                                                            | 71.6 ms: 1.01x slower                                                  |
| json_loads           | 18.2 us                                                            | 18.5 us: 1.02x slower                                                  |
| unpickle             | 10.8 us                                                            | 11.1 us: 1.02x slower                                                  |
| tomli_loads          | 1.77 sec                                                           | 1.83 sec: 1.03x slower                                                 |
| ascii85_small        | 15.7 ms                                                            | 16.6 ms: 1.06x slower                                                  |
| urlsafe_base64_small | 328 us                                                             | 347 us: 1.06x slower                                                   |
| xml_etree_process    | 49.9 ms                                                            | 53.3 ms: 1.07x slower                                                  |
| ascii85_large        | 824 ms                                                             | 883 ms: 1.07x slower                                                   |
| pickle               | 7.21 us                                                            | 7.74 us: 1.07x slower                                                  |
| pickle_list          | 2.66 us                                                            | 2.86 us: 1.08x slower                                                  |
| base85_large         | 267 ms                                                             | 295 ms: 1.10x slower                                                   |
| base85_small         | 4.85 ms                                                            | 5.52 ms: 1.14x slower                                                  |
| pickle_pure_python   | 245 us                                                             | 282 us: 1.15x slower                                                   |
| unpickle_pure_python | 161 us                                                             | 188 us: 1.17x slower                                                   |
| Geometric mean       | (ref)                                                              | 1.10x faster                                                           |

Benchmark hidden because not significant (2): unpickle_list, pickle_dict

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.51 ms                                                            | 11.6 ms: 1.22x slower                                                  |
| python_startup_no_site | 6.49 ms                                                            | 8.15 ms: 1.26x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.24x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 22.2 ms: 1.05x slower                                                  |
| genshi_xml      | 46.3 ms                                                            | 50.8 ms: 1.10x slower                                                  |
| django_template | 28.8 ms                                                            | 35.6 ms: 1.24x slower                                                  |
| mako            | 8.30 ms                                                            | 12.1 ms: 1.45x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.20x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_optimized | 189 ms                                                             | 53.4 ms: 3.54x faster                                                  |
| thread_mandelbrot_naive     | 190 ms                                                             | 53.7 ms: 3.53x faster                                                  |
| thread_counter_optimized    | 19.7 ms                                                            | 6.01 ms: 3.28x faster                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 7.45 ms: 3.05x faster                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 11.7 ms: 3.01x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 4.89 ms: 2.90x faster                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 6.04 ms: 2.79x faster                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 13.6 ms: 2.68x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 24.8 ms: 2.01x faster                                                  |
| thread_memo_naive           | 37.9 ms                                                            | 21.0 ms: 1.80x faster                                                  |
| thread_counter_naive        | 23.7 ms                                                            | 21.0 ms: 1.13x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 25.7 ms: 1.42x slower                                                  |
| Geometric mean              | (ref)                                                              | 2.31x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 5.97 ms: 7.15x faster                                                  |
| thread_mandelbrot_optimized      | 189 ms                                                             | 53.4 ms: 3.54x faster                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 53.7 ms: 3.53x faster                                                  |
| thread_counter_optimized         | 19.7 ms                                                            | 6.01 ms: 3.28x faster                                                  |
| base16_small                     | 836 us                                                             | 263 us: 3.18x faster                                                   |
| thread_pipeline_optimized        | 22.8 ms                                                            | 7.45 ms: 3.05x faster                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 11.7 ms: 3.01x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 4.89 ms: 2.90x faster                                                  |
| thread_memo_optimized            | 16.8 ms                                                            | 6.04 ms: 2.79x faster                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 13.6 ms: 2.68x faster                                                  |
| thread_pipeline_naive            | 49.8 ms                                                            | 24.8 ms: 2.01x faster                                                  |
| gc_traversal                     | 3.20 ms                                                            | 1.61 ms: 1.99x faster                                                  |
| mdp                              | 2.05 sec                                                           | 1.09 sec: 1.89x faster                                                 |
| thread_memo_naive                | 37.9 ms                                                            | 21.0 ms: 1.80x faster                                                  |
| async_tree_io_tg                 | 781 ms                                                             | 503 ms: 1.55x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 490 ms: 1.49x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 283 ms: 1.48x faster                                                   |
| argparse_many_optionals          | 12.9 ms                                                            | 8.85 ms: 1.46x faster                                                  |
| async_tree_eager_io              | 753 ms                                                             | 534 ms: 1.41x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 539 ms: 1.38x faster                                                   |
| create_gc_cycles                 | 1.77 ms                                                            | 1.29 ms: 1.37x faster                                                  |
| async_tree_none_tg               | 290 ms                                                             | 217 ms: 1.34x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 243 ms: 1.29x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 314 ms: 1.25x faster                                                   |
| deepcopy_memo                    | 27.8 us                                                            | 22.4 us: 1.24x faster                                                  |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 422 ms: 1.20x faster                                                   |
| deepcopy                         | 267 us                                                             | 225 us: 1.18x faster                                                   |
| go                               | 129 ms                                                             | 111 ms: 1.17x faster                                                   |
| regex_effbot                     | 2.33 ms                                                            | 2.00 ms: 1.17x faster                                                  |
| xml_etree_iterparse              | 86.8 ms                                                            | 74.4 ms: 1.17x faster                                                  |
| thread_counter_naive             | 23.7 ms                                                            | 21.0 ms: 1.13x faster                                                  |
| async_tree_eager_memoization     | 221 ms                                                             | 195 ms: 1.13x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 281 ms: 1.12x faster                                                   |
| pathlib                          | 12.2 ms                                                            | 11.0 ms: 1.11x faster                                                  |
| coroutines                       | 18.2 ms                                                            | 16.6 ms: 1.10x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 451 ms: 1.09x faster                                                   |
| regex_dna                        | 159 ms                                                             | 145 ms: 1.09x faster                                                   |
| asyncio_websockets               | 313 ms                                                             | 288 ms: 1.09x faster                                                   |
| xml_etree_parse                  | 121 ms                                                             | 112 ms: 1.07x faster                                                   |
| fastapi_http                     | 215 ms                                                             | 204 ms: 1.06x faster                                                   |
| scimark_sor                      | 96.2 ms                                                            | 91.9 ms: 1.05x faster                                                  |
| base64_large                     | 5.69 ms                                                            | 5.47 ms: 1.04x faster                                                  |
| json                             | 3.50 ms                                                            | 3.38 ms: 1.04x faster                                                  |
| float                            | 59.2 ms                                                            | 57.4 ms: 1.03x faster                                                  |
| pyflate                          | 374 ms                                                             | 364 ms: 1.03x faster                                                   |
| regex_v8                         | 15.0 ms                                                            | 14.7 ms: 1.02x faster                                                  |
| json_dumps                       | 7.26 ms                                                            | 7.13 ms: 1.02x faster                                                  |
| base64_small                     | 222 us                                                             | 219 us: 1.01x faster                                                   |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.35 sec: 1.01x faster                                                 |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x faster                                                   |
| base32_small                     | 6.46 ms                                                            | 6.52 ms: 1.01x slower                                                  |
| base32_large                     | 325 ms                                                             | 330 ms: 1.01x slower                                                   |
| xml_etree_generate               | 70.6 ms                                                            | 71.6 ms: 1.01x slower                                                  |
| json_loads                       | 18.2 us                                                            | 18.5 us: 1.02x slower                                                  |
| unpickle                         | 10.8 us                                                            | 11.1 us: 1.02x slower                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 2.42 us: 1.03x slower                                                  |
| async_generators                 | 251 ms                                                             | 258 ms: 1.03x slower                                                   |
| tomli_loads                      | 1.77 sec                                                           | 1.83 sec: 1.03x slower                                                 |
| telco                            | 5.37 ms                                                            | 5.60 ms: 1.04x slower                                                  |
| scimark_fft                      | 216 ms                                                             | 226 ms: 1.05x slower                                                   |
| spectral_norm                    | 68.6 ms                                                            | 71.9 ms: 1.05x slower                                                  |
| genshi_text                      | 21.1 ms                                                            | 22.2 ms: 1.05x slower                                                  |
| decimal_pi                       | 228 ms                                                             | 240 ms: 1.05x slower                                                   |
| ascii85_small                    | 15.7 ms                                                            | 16.6 ms: 1.06x slower                                                  |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 44.6 ms: 1.06x slower                                                  |
| urlsafe_base64_small             | 328 us                                                             | 347 us: 1.06x slower                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.36 sec: 1.06x slower                                                 |
| noop                             | 21.4 ns                                                            | 22.8 ns: 1.06x slower                                                  |
| decimal_factorial                | 177 ms                                                             | 188 ms: 1.06x slower                                                   |
| xml_etree_process                | 49.9 ms                                                            | 53.3 ms: 1.07x slower                                                  |
| ascii85_large                    | 824 ms                                                             | 883 ms: 1.07x slower                                                   |
| pickle                           | 7.21 us                                                            | 7.74 us: 1.07x slower                                                  |
| pickle_list                      | 2.66 us                                                            | 2.86 us: 1.08x slower                                                  |
| thrift                           | 2.07 ms                                                            | 2.24 ms: 1.08x slower                                                  |
| pycparser                        | 901 ms                                                             | 985 ms: 1.09x slower                                                   |
| genshi_xml                       | 46.3 ms                                                            | 50.8 ms: 1.10x slower                                                  |
| base85_large                     | 267 ms                                                             | 295 ms: 1.10x slower                                                   |
| sympy_integrate                  | 15.4 ms                                                            | 17.1 ms: 1.11x slower                                                  |
| chameleon                        | 11.1 ms                                                            | 12.3 ms: 1.11x slower                                                  |
| fannkuch                         | 287 ms                                                             | 319 ms: 1.11x slower                                                   |
| quadtree_nbody                   | 675 ms                                                             | 753 ms: 1.12x slower                                                   |
| richards_super                   | 43.8 ms                                                            | 49.0 ms: 1.12x slower                                                  |
| regex_compile                    | 102 ms                                                             | 115 ms: 1.12x slower                                                   |
| richards                         | 38.2 ms                                                            | 43.0 ms: 1.13x slower                                                  |
| meteor_contest                   | 85.7 ms                                                            | 96.7 ms: 1.13x slower                                                  |
| scimark_monte_carlo              | 47.2 ms                                                            | 53.2 ms: 1.13x slower                                                  |
| xdsl_constant_fold               | 36.4 ms                                                            | 41.2 ms: 1.13x slower                                                  |
| async_tree_eager                 | 88.3 ms                                                            | 100 ms: 1.14x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 119 ms: 1.14x slower                                                   |
| base85_small                     | 4.85 ms                                                            | 5.52 ms: 1.14x slower                                                  |
| chaos                            | 43.6 ms                                                            | 49.7 ms: 1.14x slower                                                  |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 95.3 ms: 1.14x slower                                                  |
| logging_simple                   | 5.06 us                                                            | 5.77 us: 1.14x slower                                                  |
| pickle_pure_python               | 245 us                                                             | 282 us: 1.15x slower                                                   |
| comprehensions                   | 11.4 us                                                            | 13.2 us: 1.15x slower                                                  |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.40 ms: 1.15x slower                                                  |
| networkx_shortest_path           | 454 ms                                                             | 523 ms: 1.15x slower                                                   |
| docutils                         | 1.89 sec                                                           | 2.18 sec: 1.15x slower                                                 |
| networkx_connected_components    | 443 ms                                                             | 511 ms: 1.16x slower                                                   |
| hexiom                           | 4.75 ms                                                            | 5.50 ms: 1.16x slower                                                  |
| sympy_str                        | 193 ms                                                             | 225 ms: 1.17x slower                                                   |
| unpickle_pure_python             | 161 us                                                             | 188 us: 1.17x slower                                                   |
| mypy2                            | 741 ms                                                             | 866 ms: 1.17x slower                                                   |
| logging_format                   | 5.62 us                                                            | 6.58 us: 1.17x slower                                                  |
| sympy_expand                     | 331 ms                                                             | 388 ms: 1.17x slower                                                   |
| pprint_safe_repr                 | 546 ms                                                             | 641 ms: 1.18x slower                                                   |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 3.36 ms: 1.18x slower                                                  |
| crypto_pyaes                     | 55.6 ms                                                            | 65.6 ms: 1.18x slower                                                  |
| pprint_pformat                   | 1.13 sec                                                           | 1.33 sec: 1.18x slower                                                 |
| nqueens                          | 58.3 ms                                                            | 69.1 ms: 1.18x slower                                                  |
| nbody                            | 75.8 ms                                                            | 89.8 ms: 1.19x slower                                                  |
| sqlglot_v2_parse                 | 979 us                                                             | 1.17 ms: 1.20x slower                                                  |
| sqlalchemy_imperative            | 13.9 ms                                                            | 16.7 ms: 1.20x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 541 us: 1.20x slower                                                   |
| scimark_lu                       | 70.2 ms                                                            | 84.7 ms: 1.21x slower                                                  |
| raytrace                         | 197 ms                                                             | 240 ms: 1.22x slower                                                   |
| generators                       | 22.2 ms                                                            | 27.0 ms: 1.22x slower                                                  |
| typing_runtime_protocols         | 112 us                                                             | 137 us: 1.22x slower                                                   |
| python_startup                   | 9.51 ms                                                            | 11.6 ms: 1.22x slower                                                  |
| deltablue                        | 2.59 ms                                                            | 3.19 ms: 1.23x slower                                                  |
| django_template                  | 28.8 ms                                                            | 35.6 ms: 1.24x slower                                                  |
| logging_silent                   | 60.1 ns                                                            | 74.9 ns: 1.25x slower                                                  |
| python_startup_no_site           | 6.49 ms                                                            | 8.15 ms: 1.26x slower                                                  |
| coverage                         | 55.0 ms                                                            | 73.4 ms: 1.33x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 405 ms: 1.35x slower                                                   |
| unpack_sequence                  | 26.4 ns                                                            | 36.0 ns: 1.36x slower                                                  |
| thread_montecarlo_naive          | 18.1 ms                                                            | 25.7 ms: 1.42x slower                                                  |
| mako                             | 8.30 ms                                                            | 12.1 ms: 1.45x slower                                                  |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 264 ms: 1.51x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 190 ms: 3.34x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.06x faster                                                           |

Benchmark hidden because not significant (7): html5lib, unpickle_list, pickle_dict, tornado_http, async_tree_eager_cpu_io_mixed, networkx_k_core, pylint

- Geometric mean (including insignificant results): 1.066x faster

# HPT report

- Reliability score: 90.88% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.60x