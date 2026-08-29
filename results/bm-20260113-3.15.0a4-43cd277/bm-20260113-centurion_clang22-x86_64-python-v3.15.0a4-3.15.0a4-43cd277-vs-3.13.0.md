# Results vs. 3.13.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.123x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.04x faster
- Memory change: 1.11x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.1 ms: 1.11x faster                                                  |
| docutils       | 1.89 sec                                                           | 1.97 sec: 1.05x slower                                                 |
| html5lib       | 50.9 ms                                                            | 43.7 ms: 1.17x faster                                                  |
| tornado_http   | 98.9 ms                                                            | 99.6 ms: 1.01x slower                                                  |
| Geometric mean | (ref)                                                              | 1.04x faster                                                           |

Benchmark hidden because not significant (1): fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_io_tg                 | 781 ms                                                             | 484 ms: 1.61x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 263 ms: 1.60x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 487 ms: 1.55x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 473 ms: 1.54x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 491 ms: 1.51x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 269 ms: 1.46x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 200 ms: 1.45x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 222 ms: 1.41x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 402 ms: 1.26x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 175 ms: 1.26x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 14.6 ms: 1.25x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 405 ms: 1.22x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 272 ms: 1.16x faster                                                   |
| async_generators                 | 251 ms                                                             | 220 ms: 1.14x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 80.5 ms: 1.10x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 328 ms: 1.04x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.01x faster                                                 |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 367 ms: 1.22x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 228 ms: 1.30x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 175 ms: 3.08x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.16x faster                                                           |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 17.9 ns: 1.19x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 207 ms: 1.10x faster                                                   |
| decimal_factorial | 177 ms                                                             | 173 ms: 1.02x faster                                                   |
| Geometric mean    | (ref)                                                              | 1.06x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| float          | 59.2 ms                                                            | 47.0 ms: 1.26x faster                                                  |
| quadtree_nbody | 675 ms                                                             | 572 ms: 1.18x faster                                                   |
| nbody          | 75.8 ms                                                            | 64.4 ms: 1.18x faster                                                  |
| pidigits       | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| Geometric mean | (ref)                                                              | 1.15x faster                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_effbot   | 2.33 ms                                                            | 2.06 ms: 1.13x faster                                                  |
| regex_dna      | 159 ms                                                             | 143 ms: 1.11x faster                                                   |
| regex_compile  | 102 ms                                                             | 96.1 ms: 1.07x faster                                                  |
| Geometric mean | (ref)                                                              | 1.07x faster                                                           |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large         | 42.7 ms                                                            | 6.11 ms: 6.99x faster                                                  |
| base16_small         | 836 us                                                             | 256 us: 3.26x faster                                                   |
| ascii85_small        | 15.7 ms                                                            | 12.9 ms: 1.22x faster                                                  |
| ascii85_large        | 824 ms                                                             | 687 ms: 1.20x faster                                                   |
| base32_large         | 325 ms                                                             | 277 ms: 1.17x faster                                                   |
| base32_small         | 6.46 ms                                                            | 5.53 ms: 1.17x faster                                                  |
| unpickle_list        | 3.42 us                                                            | 3.00 us: 1.14x faster                                                  |
| xml_etree_iterparse  | 86.8 ms                                                            | 76.7 ms: 1.13x faster                                                  |
| json_dumps           | 7.26 ms                                                            | 6.55 ms: 1.11x faster                                                  |
| tomli_loads          | 1.77 sec                                                           | 1.60 sec: 1.11x faster                                                 |
| base85_large         | 267 ms                                                             | 242 ms: 1.10x faster                                                   |
| base85_small         | 4.85 ms                                                            | 4.48 ms: 1.08x faster                                                  |
| xml_etree_generate   | 70.6 ms                                                            | 65.7 ms: 1.07x faster                                                  |
| unpickle_pure_python | 161 us                                                             | 154 us: 1.05x faster                                                   |
| xml_etree_process    | 49.9 ms                                                            | 47.7 ms: 1.05x faster                                                  |
| json_loads           | 18.2 us                                                            | 17.4 us: 1.05x faster                                                  |
| xml_etree_parse      | 121 ms                                                             | 116 ms: 1.04x faster                                                   |
| base64_small         | 222 us                                                             | 216 us: 1.03x faster                                                   |
| unpickle             | 10.8 us                                                            | 10.5 us: 1.03x faster                                                  |
| pickle_pure_python   | 245 us                                                             | 240 us: 1.02x faster                                                   |
| urlsafe_base64_small | 328 us                                                             | 322 us: 1.02x faster                                                   |
| pickle_dict          | 19.0 us                                                            | 19.1 us: 1.00x slower                                                  |
| base64_large         | 5.69 ms                                                            | 5.73 ms: 1.01x slower                                                  |
| pickle               | 7.21 us                                                            | 7.91 us: 1.10x slower                                                  |
| pickle_list          | 2.66 us                                                            | 2.98 us: 1.12x slower                                                  |
| Geometric mean       | (ref)                                                              | 1.20x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.24 ms: 1.04x faster                                                  |
| python_startup         | 9.51 ms                                                            | 9.46 ms: 1.01x faster                                                  |
| Geometric mean         | (ref)                                                              | 1.02x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| genshi_text     | 21.1 ms                                                            | 18.0 ms: 1.17x faster                                                  |
| genshi_xml      | 46.3 ms                                                            | 43.0 ms: 1.08x faster                                                  |
| mako            | 8.30 ms                                                            | 8.36 ms: 1.01x slower                                                  |
| django_template | 28.8 ms                                                            | 31.1 ms: 1.08x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.04x faster                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 9.47 ms: 4.00x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 35.2 ms: 1.41x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 13.4 ms: 1.36x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 11.6 ms: 1.22x faster                                                  |
| thread_counter_naive        | 23.7 ms                                                            | 22.5 ms: 1.05x faster                                                  |
| thread_mandelbrot_naive     | 190 ms                                                             | 182 ms: 1.04x faster                                                   |
| thread_mandelbrot_optimized | 189 ms                                                             | 183 ms: 1.03x faster                                                   |
| thread_counter_optimized    | 19.7 ms                                                            | 20.1 ms: 1.02x slower                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 17.8 ms: 1.06x slower                                                  |
| thread_accumulate_naive     | 36.5 ms                                                            | 41.9 ms: 1.15x slower                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 41.4 ms: 1.17x slower                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 26.9 ms: 1.18x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.16x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base16_large                     | 42.7 ms                                                            | 6.11 ms: 6.99x faster                                                  |
| thread_memo_naive                | 37.9 ms                                                            | 9.47 ms: 4.00x faster                                                  |
| base16_small                     | 836 us                                                             | 256 us: 3.26x faster                                                   |
| mdp                              | 2.05 sec                                                           | 927 ms: 2.22x faster                                                   |
| deepcopy_memo                    | 27.8 us                                                            | 16.7 us: 1.66x faster                                                  |
| async_tree_io_tg                 | 781 ms                                                             | 484 ms: 1.61x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 263 ms: 1.60x faster                                                   |
| argparse_many_optionals          | 12.9 ms                                                            | 8.23 ms: 1.57x faster                                                  |
| async_tree_eager_io              | 753 ms                                                             | 487 ms: 1.55x faster                                                   |
| async_tree_eager_io_tg           | 731 ms                                                             | 473 ms: 1.54x faster                                                   |
| go                               | 129 ms                                                             | 85.1 ms: 1.52x faster                                                  |
| async_tree_io                    | 743 ms                                                             | 491 ms: 1.51x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 269 ms: 1.46x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 200 ms: 1.45x faster                                                   |
| thread_pipeline_naive            | 49.8 ms                                                            | 35.2 ms: 1.41x faster                                                  |
| async_tree_none                  | 312 ms                                                             | 222 ms: 1.41x faster                                                   |
| deepcopy                         | 267 us                                                             | 192 us: 1.39x faster                                                   |
| thread_montecarlo_naive          | 18.1 ms                                                            | 13.4 ms: 1.36x faster                                                  |
| scimark_sor                      | 96.2 ms                                                            | 74.2 ms: 1.30x faster                                                  |
| pyflate                          | 374 ms                                                             | 293 ms: 1.28x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 402 ms: 1.26x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 175 ms: 1.26x faster                                                   |
| float                            | 59.2 ms                                                            | 47.0 ms: 1.26x faster                                                  |
| coroutines                       | 18.2 ms                                                            | 14.6 ms: 1.25x faster                                                  |
| fannkuch                         | 287 ms                                                             | 232 ms: 1.23x faster                                                   |
| scimark_monte_carlo              | 47.2 ms                                                            | 38.2 ms: 1.23x faster                                                  |
| richards                         | 38.2 ms                                                            | 31.2 ms: 1.22x faster                                                  |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 11.6 ms: 1.22x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 405 ms: 1.22x faster                                                   |
| ascii85_small                    | 15.7 ms                                                            | 12.9 ms: 1.22x faster                                                  |
| richards_super                   | 43.8 ms                                                            | 36.2 ms: 1.21x faster                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 1.96 us: 1.20x faster                                                  |
| ascii85_large                    | 824 ms                                                             | 687 ms: 1.20x faster                                                   |
| noop                             | 21.4 ns                                                            | 17.9 ns: 1.19x faster                                                  |
| quadtree_nbody                   | 675 ms                                                             | 572 ms: 1.18x faster                                                   |
| nbody                            | 75.8 ms                                                            | 64.4 ms: 1.18x faster                                                  |
| base32_large                     | 325 ms                                                             | 277 ms: 1.17x faster                                                   |
| genshi_text                      | 21.1 ms                                                            | 18.0 ms: 1.17x faster                                                  |
| base32_small                     | 6.46 ms                                                            | 5.53 ms: 1.17x faster                                                  |
| spectral_norm                    | 68.6 ms                                                            | 58.8 ms: 1.17x faster                                                  |
| scimark_fft                      | 216 ms                                                             | 185 ms: 1.17x faster                                                   |
| html5lib                         | 50.9 ms                                                            | 43.7 ms: 1.17x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 272 ms: 1.16x faster                                                   |
| unpickle_list                    | 3.42 us                                                            | 3.00 us: 1.14x faster                                                  |
| async_generators                 | 251 ms                                                             | 220 ms: 1.14x faster                                                   |
| networkx_k_core                  | 2.16 sec                                                           | 1.90 sec: 1.14x faster                                                 |
| pathlib                          | 12.2 ms                                                            | 10.7 ms: 1.14x faster                                                  |
| xml_etree_iterparse              | 86.8 ms                                                            | 76.7 ms: 1.13x faster                                                  |
| regex_effbot                     | 2.33 ms                                                            | 2.06 ms: 1.13x faster                                                  |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.01 sec: 1.12x faster                                                 |
| chaos                            | 43.6 ms                                                            | 39.0 ms: 1.12x faster                                                  |
| regex_dna                        | 159 ms                                                             | 143 ms: 1.11x faster                                                   |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.58 ms: 1.11x faster                                                  |
| json_dumps                       | 7.26 ms                                                            | 6.55 ms: 1.11x faster                                                  |
| telco                            | 5.37 ms                                                            | 4.85 ms: 1.11x faster                                                  |
| tomli_loads                      | 1.77 sec                                                           | 1.60 sec: 1.11x faster                                                 |
| chameleon                        | 11.1 ms                                                            | 10.1 ms: 1.11x faster                                                  |
| base85_large                     | 267 ms                                                             | 242 ms: 1.10x faster                                                   |
| decimal_pi                       | 228 ms                                                             | 207 ms: 1.10x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 80.5 ms: 1.10x faster                                                  |
| hexiom                           | 4.75 ms                                                            | 4.33 ms: 1.10x faster                                                  |
| base85_small                     | 4.85 ms                                                            | 4.48 ms: 1.08x faster                                                  |
| genshi_xml                       | 46.3 ms                                                            | 43.0 ms: 1.08x faster                                                  |
| logging_silent                   | 60.1 ns                                                            | 55.8 ns: 1.08x faster                                                  |
| xml_etree_generate               | 70.6 ms                                                            | 65.7 ms: 1.07x faster                                                  |
| comprehensions                   | 11.4 us                                                            | 10.7 us: 1.07x faster                                                  |
| thrift                           | 2.07 ms                                                            | 1.94 ms: 1.07x faster                                                  |
| regex_compile                    | 102 ms                                                             | 96.1 ms: 1.07x faster                                                  |
| raytrace                         | 197 ms                                                             | 186 ms: 1.06x faster                                                   |
| pprint_pformat                   | 1.13 sec                                                           | 1.06 sec: 1.06x faster                                                 |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.15 ms: 1.06x faster                                                  |
| sqlglot_v2_parse                 | 979 us                                                             | 928 us: 1.05x faster                                                   |
| thread_counter_naive             | 23.7 ms                                                            | 22.5 ms: 1.05x faster                                                  |
| pprint_safe_repr                 | 546 ms                                                             | 519 ms: 1.05x faster                                                   |
| unpickle_pure_python             | 161 us                                                             | 154 us: 1.05x faster                                                   |
| nqueens                          | 58.3 ms                                                            | 55.6 ms: 1.05x faster                                                  |
| pylint                           | 226 ms                                                             | 216 ms: 1.05x faster                                                   |
| json                             | 3.50 ms                                                            | 3.34 ms: 1.05x faster                                                  |
| xml_etree_process                | 49.9 ms                                                            | 47.7 ms: 1.05x faster                                                  |
| json_loads                       | 18.2 us                                                            | 17.4 us: 1.05x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 328 ms: 1.04x faster                                                   |
| meteor_contest                   | 85.7 ms                                                            | 82.1 ms: 1.04x faster                                                  |
| xml_etree_parse                  | 121 ms                                                             | 116 ms: 1.04x faster                                                   |
| pycparser                        | 901 ms                                                             | 865 ms: 1.04x faster                                                   |
| python_startup_no_site           | 6.49 ms                                                            | 6.24 ms: 1.04x faster                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 182 ms: 1.04x faster                                                   |
| thread_mandelbrot_optimized      | 189 ms                                                             | 183 ms: 1.03x faster                                                   |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 40.8 ms: 1.03x faster                                                  |
| networkx_connected_components    | 443 ms                                                             | 429 ms: 1.03x faster                                                   |
| crypto_pyaes                     | 55.6 ms                                                            | 54.0 ms: 1.03x faster                                                  |
| networkx_shortest_path           | 454 ms                                                             | 441 ms: 1.03x faster                                                   |
| base64_small                     | 222 us                                                             | 216 us: 1.03x faster                                                   |
| unpickle                         | 10.8 us                                                            | 10.5 us: 1.03x faster                                                  |
| logging_simple                   | 5.06 us                                                            | 4.94 us: 1.02x faster                                                  |
| typing_runtime_protocols         | 112 us                                                             | 110 us: 1.02x faster                                                   |
| pickle_pure_python               | 245 us                                                             | 240 us: 1.02x faster                                                   |
| decimal_factorial                | 177 ms                                                             | 173 ms: 1.02x faster                                                   |
| urlsafe_base64_small             | 328 us                                                             | 322 us: 1.02x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.01x faster                                                 |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 82.7 ms: 1.01x faster                                                  |
| sympy_integrate                  | 15.4 ms                                                            | 15.3 ms: 1.01x faster                                                  |
| deltablue                        | 2.59 ms                                                            | 2.56 ms: 1.01x faster                                                  |
| python_startup                   | 9.51 ms                                                            | 9.46 ms: 1.01x faster                                                  |
| pidigits                         | 216 ms                                                             | 217 ms: 1.00x slower                                                   |
| pickle_dict                      | 19.0 us                                                            | 19.1 us: 1.00x slower                                                  |
| mako                             | 8.30 ms                                                            | 8.36 ms: 1.01x slower                                                  |
| base64_large                     | 5.69 ms                                                            | 5.73 ms: 1.01x slower                                                  |
| tornado_http                     | 98.9 ms                                                            | 99.6 ms: 1.01x slower                                                  |
| thread_counter_optimized         | 19.7 ms                                                            | 20.1 ms: 1.02x slower                                                  |
| coverage                         | 55.0 ms                                                            | 56.2 ms: 1.02x slower                                                  |
| mypy2                            | 741 ms                                                             | 765 ms: 1.03x slower                                                   |
| gc_traversal                     | 3.20 ms                                                            | 3.33 ms: 1.04x slower                                                  |
| docutils                         | 1.89 sec                                                           | 1.97 sec: 1.05x slower                                                 |
| sympy_expand                     | 331 ms                                                             | 350 ms: 1.06x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 111 ms: 1.06x slower                                                   |
| thread_memo_optimized            | 16.8 ms                                                            | 17.8 ms: 1.06x slower                                                  |
| sympy_str                        | 193 ms                                                             | 204 ms: 1.06x slower                                                   |
| sqlalchemy_imperative            | 13.9 ms                                                            | 14.9 ms: 1.07x slower                                                  |
| django_template                  | 28.8 ms                                                            | 31.1 ms: 1.08x slower                                                  |
| generators                       | 22.2 ms                                                            | 24.1 ms: 1.08x slower                                                  |
| pickle                           | 7.21 us                                                            | 7.91 us: 1.10x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 498 us: 1.11x slower                                                   |
| pickle_list                      | 2.66 us                                                            | 2.98 us: 1.12x slower                                                  |
| create_gc_cycles                 | 1.77 ms                                                            | 2.01 ms: 1.13x slower                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 41.9 ms: 1.15x slower                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 41.4 ms: 1.17x slower                                                  |
| thread_pipeline_optimized        | 22.8 ms                                                            | 26.9 ms: 1.18x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 367 ms: 1.22x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 228 ms: 1.30x slower                                                   |
| unpack_sequence                  | 26.4 ns                                                            | 43.4 ns: 1.64x slower                                                  |
| async_tree_eager_tg              | 56.8 ms                                                            | 175 ms: 3.08x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.12x faster                                                           |

Benchmark hidden because not significant (6): xdsl_constant_fold, asyncio_websockets, fastapi_http, logging_format, regex_v8, scimark_lu

- Geometric mean (including insignificant results): 1.123x faster

# HPT report

- Reliability score: 100.00% likely to be faster
- 90% likely to have a speedup of 1.06x
- 95% likely to have a speedup of 1.06x
- 99% likely to have a speedup of 1.04x

# Memory
- memory change: 1.11x