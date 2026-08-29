# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.060x slower
- HPT reliability: 99.98%
- HPT 99th percentile: 1.01x slower
- Memory change: 0.92x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.1 ms: 1.08x slower                                              |
| docutils       | 1.98 sec                                                           | 1.89 sec: 1.05x faster                                             |
| fastapi_http   | 222 ms                                                             | 215 ms: 1.03x faster                                               |
| html5lib       | 45.3 ms                                                            | 50.9 ms: 1.12x slower                                              |
| tornado_http   | 101 ms                                                             | 98.9 ms: 1.02x faster                                              |
| Geometric mean | (ref)                                                              | 1.02x slower                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                             | 56.8 ms: 3.21x faster                                              |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 175 ms: 1.35x faster                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 301 ms: 1.24x faster                                               |
| asyncio_tcp                      | 324 ms                                                             | 316 ms: 1.02x faster                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.28 sec: 1.01x faster                                             |
| asyncio_websockets               | 305 ms                                                             | 313 ms: 1.03x slower                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 342 ms: 1.05x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 88.3 ms: 1.06x slower                                              |
| async_generators                 | 231 ms                                                             | 251 ms: 1.09x slower                                               |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 494 ms: 1.15x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 507 ms: 1.19x slower                                               |
| coroutines                       | 15.1 ms                                                            | 18.2 ms: 1.20x slower                                              |
| async_tree_eager_memoization     | 183 ms                                                             | 221 ms: 1.21x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 731 ms: 1.29x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 290 ms: 1.29x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 753 ms: 1.33x slower                                               |
| async_tree_none                  | 233 ms                                                             | 312 ms: 1.34x slower                                               |
| async_tree_io                    | 549 ms                                                             | 743 ms: 1.35x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 392 ms: 1.38x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 781 ms: 1.43x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 421 ms: 1.51x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.08x slower                                                       |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 21.4 ns: 1.12x slower                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 177 ms: 1.01x slower                                               |
| decimal_pi        | 209 ms                                                             | 228 ms: 1.09x slower                                               |
| Geometric mean    | (ref)                                                              | 1.05x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 216 ms: 1.00x faster                                               |
| nbody          | 74.2 ms                                                            | 75.8 ms: 1.02x slower                                              |
| quadtree_nbody | 654 ms                                                             | 675 ms: 1.03x slower                                               |
| float          | 51.2 ms                                                            | 59.2 ms: 1.16x slower                                              |
| Geometric mean | (ref)                                                              | 1.05x slower                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_compile  | 97.0 ms                                                            | 102 ms: 1.06x slower                                               |
| regex_dna      | 147 ms                                                             | 159 ms: 1.08x slower                                               |
| regex_effbot   | 1.98 ms                                                            | 2.33 ms: 1.18x slower                                              |
| Geometric mean | (ref)                                                              | 1.08x slower                                                       |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| pickle_list          | 3.03 us                                                            | 2.66 us: 1.14x faster                                              |
| pickle               | 8.04 us                                                            | 7.21 us: 1.12x faster                                              |
| pickle_dict          | 20.0 us                                                            | 19.0 us: 1.05x faster                                              |
| urlsafe_base64_small | 340 us                                                             | 328 us: 1.04x faster                                               |
| json_dumps           | 7.52 ms                                                            | 7.26 ms: 1.04x faster                                              |
| base64_small         | 227 us                                                             | 222 us: 1.02x faster                                               |
| pickle_pure_python   | 251 us                                                             | 245 us: 1.02x faster                                               |
| json_loads           | 18.6 us                                                            | 18.2 us: 1.02x faster                                              |
| unpickle_pure_python | 163 us                                                             | 161 us: 1.01x faster                                               |
| xml_etree_iterparse  | 85.5 ms                                                            | 86.8 ms: 1.02x slower                                              |
| xml_etree_parse      | 118 ms                                                             | 121 ms: 1.03x slower                                               |
| unpickle             | 10.5 us                                                            | 10.8 us: 1.03x slower                                              |
| xml_etree_generate   | 68.1 ms                                                            | 70.6 ms: 1.04x slower                                              |
| base85_small         | 4.66 ms                                                            | 4.85 ms: 1.04x slower                                              |
| base85_large         | 249 ms                                                             | 267 ms: 1.07x slower                                               |
| base32_large         | 289 ms                                                             | 325 ms: 1.12x slower                                               |
| unpickle_list        | 3.03 us                                                            | 3.42 us: 1.13x slower                                              |
| base32_small         | 5.71 ms                                                            | 6.46 ms: 1.13x slower                                              |
| tomli_loads          | 1.49 sec                                                           | 1.77 sec: 1.19x slower                                             |
| ascii85_small        | 13.0 ms                                                            | 15.7 ms: 1.21x slower                                              |
| ascii85_large        | 681 ms                                                             | 824 ms: 1.21x slower                                               |
| base16_small         | 265 us                                                             | 836 us: 3.16x slower                                               |
| base16_large         | 6.35 ms                                                            | 42.7 ms: 6.72x slower                                              |
| Geometric mean       | (ref)                                                              | 1.16x slower                                                       |

Benchmark hidden because not significant (2): xml_etree_process, base64_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 9.51 ms: 1.04x faster                                              |
| python_startup_no_site | 6.52 ms                                                            | 6.49 ms: 1.00x faster                                              |
| Geometric mean         | (ref)                                                              | 1.02x faster                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 28.8 ms: 1.06x faster                                              |
| mako            | 8.69 ms                                                            | 8.30 ms: 1.05x faster                                              |
| genshi_xml      | 43.2 ms                                                            | 46.3 ms: 1.07x slower                                              |
| genshi_text     | 18.0 ms                                                            | 21.1 ms: 1.17x slower                                              |
| Geometric mean  | (ref)                                                              | 1.03x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.8 ms                                                            | 22.8 ms: 1.13x faster                                              |
| thread_accumulate_optimized | 39.5 ms                                                            | 35.3 ms: 1.12x faster                                              |
| thread_accumulate_naive     | 40.4 ms                                                            | 36.5 ms: 1.11x faster                                              |
| thread_mandelbrot_naive     | 207 ms                                                             | 190 ms: 1.09x faster                                               |
| thread_mandelbrot_optimized | 205 ms                                                             | 189 ms: 1.09x faster                                               |
| thread_memo_optimized       | 17.5 ms                                                            | 16.8 ms: 1.04x faster                                              |
| thread_counter_optimized    | 18.3 ms                                                            | 19.7 ms: 1.08x slower                                              |
| thread_montecarlo_optimized | 12.9 ms                                                            | 14.2 ms: 1.10x slower                                              |
| thread_counter_naive        | 21.2 ms                                                            | 23.7 ms: 1.12x slower                                              |
| thread_montecarlo_naive     | 14.3 ms                                                            | 18.1 ms: 1.27x slower                                              |
| thread_pipeline_naive       | 34.9 ms                                                            | 49.8 ms: 1.43x slower                                              |
| thread_memo_naive           | 12.4 ms                                                            | 37.9 ms: 3.05x slower                                              |
| Geometric mean              | (ref)                                                              | 1.13x slower                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                             | 56.8 ms: 3.21x faster                                              |
| argparse_many_optionals          | 34.5 ms                                                            | 12.9 ms: 2.67x faster                                              |
| argparse_subparsers              | 687 us                                                             | 449 us: 1.53x faster                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 175 ms: 1.35x faster                                               |
| unpack_sequence                  | 35.6 ns                                                            | 26.4 ns: 1.35x faster                                              |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 301 ms: 1.24x faster                                               |
| pickle_list                      | 3.03 us                                                            | 2.66 us: 1.14x faster                                              |
| create_gc_cycles                 | 2.02 ms                                                            | 1.77 ms: 1.14x faster                                              |
| thread_pipeline_optimized        | 25.8 ms                                                            | 22.8 ms: 1.13x faster                                              |
| thread_accumulate_optimized      | 39.5 ms                                                            | 35.3 ms: 1.12x faster                                              |
| pickle                           | 8.04 us                                                            | 7.21 us: 1.12x faster                                              |
| thread_accumulate_naive          | 40.4 ms                                                            | 36.5 ms: 1.11x faster                                              |
| thread_mandelbrot_naive          | 207 ms                                                             | 190 ms: 1.09x faster                                               |
| generators                       | 24.2 ms                                                            | 22.2 ms: 1.09x faster                                              |
| thread_mandelbrot_optimized      | 205 ms                                                             | 189 ms: 1.09x faster                                               |
| logging_format                   | 6.00 us                                                            | 5.62 us: 1.07x faster                                              |
| deltablue                        | 2.76 ms                                                            | 2.59 ms: 1.07x faster                                              |
| sqlalchemy_imperative            | 14.8 ms                                                            | 13.9 ms: 1.06x faster                                              |
| scimark_lu                       | 74.7 ms                                                            | 70.2 ms: 1.06x faster                                              |
| django_template                  | 30.5 ms                                                            | 28.8 ms: 1.06x faster                                              |
| mypy2                            | 780 ms                                                             | 741 ms: 1.05x faster                                               |
| gc_traversal                     | 3.36 ms                                                            | 3.20 ms: 1.05x faster                                              |
| pickle_dict                      | 20.0 us                                                            | 19.0 us: 1.05x faster                                              |
| mako                             | 8.69 ms                                                            | 8.30 ms: 1.05x faster                                              |
| docutils                         | 1.98 sec                                                           | 1.89 sec: 1.05x faster                                             |
| python_startup                   | 9.93 ms                                                            | 9.51 ms: 1.04x faster                                              |
| thread_memo_optimized            | 17.5 ms                                                            | 16.8 ms: 1.04x faster                                              |
| sympy_sum                        | 109 ms                                                             | 104 ms: 1.04x faster                                               |
| urlsafe_base64_small             | 340 us                                                             | 328 us: 1.04x faster                                               |
| pathlib                          | 12.7 ms                                                            | 12.2 ms: 1.04x faster                                              |
| json_dumps                       | 7.52 ms                                                            | 7.26 ms: 1.04x faster                                              |
| sympy_expand                     | 344 ms                                                             | 331 ms: 1.04x faster                                               |
| sympy_str                        | 200 ms                                                             | 193 ms: 1.04x faster                                               |
| fastapi_http                     | 222 ms                                                             | 215 ms: 1.03x faster                                               |
| typing_runtime_protocols         | 115 us                                                             | 112 us: 1.02x faster                                               |
| nqueens                          | 59.8 ms                                                            | 58.3 ms: 1.02x faster                                              |
| base64_small                     | 227 us                                                             | 222 us: 1.02x faster                                               |
| asyncio_tcp                      | 324 ms                                                             | 316 ms: 1.02x faster                                               |
| pickle_pure_python               | 251 us                                                             | 245 us: 1.02x faster                                               |
| json_loads                       | 18.6 us                                                            | 18.2 us: 1.02x faster                                              |
| tornado_http                     | 101 ms                                                             | 98.9 ms: 1.02x faster                                              |
| raytrace                         | 201 ms                                                             | 197 ms: 1.02x faster                                               |
| crypto_pyaes                     | 56.7 ms                                                            | 55.6 ms: 1.02x faster                                              |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 83.6 ms: 1.01x faster                                              |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.86 ms: 1.01x faster                                              |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.28 sec: 1.01x faster                                             |
| unpickle_pure_python             | 163 us                                                             | 161 us: 1.01x faster                                               |
| telco                            | 5.39 ms                                                            | 5.37 ms: 1.01x faster                                              |
| python_startup_no_site           | 6.52 ms                                                            | 6.49 ms: 1.00x faster                                              |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x faster                                               |
| meteor_contest                   | 85.4 ms                                                            | 85.7 ms: 1.00x slower                                              |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.22 ms: 1.01x slower                                              |
| logging_simple                   | 5.02 us                                                            | 5.06 us: 1.01x slower                                              |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 42.1 ms: 1.01x slower                                              |
| coverage                         | 54.5 ms                                                            | 55.0 ms: 1.01x slower                                              |
| json                             | 3.46 ms                                                            | 3.50 ms: 1.01x slower                                              |
| decimal_factorial                | 174 ms                                                             | 177 ms: 1.01x slower                                               |
| logging_silent                   | 59.2 ns                                                            | 60.1 ns: 1.01x slower                                              |
| xml_etree_iterparse              | 85.5 ms                                                            | 86.8 ms: 1.02x slower                                              |
| chaos                            | 42.9 ms                                                            | 43.6 ms: 1.02x slower                                              |
| networkx_shortest_path           | 447 ms                                                             | 454 ms: 1.02x slower                                               |
| sympy_integrate                  | 15.1 ms                                                            | 15.4 ms: 1.02x slower                                              |
| pprint_safe_repr                 | 534 ms                                                             | 546 ms: 1.02x slower                                               |
| nbody                            | 74.2 ms                                                            | 75.8 ms: 1.02x slower                                              |
| scimark_fft                      | 211 ms                                                             | 216 ms: 1.02x slower                                               |
| pprint_pformat                   | 1.10 sec                                                           | 1.13 sec: 1.03x slower                                             |
| sqlglot_v2_parse                 | 954 us                                                             | 979 us: 1.03x slower                                               |
| asyncio_websockets               | 305 ms                                                             | 313 ms: 1.03x slower                                               |
| pycparser                        | 878 ms                                                             | 901 ms: 1.03x slower                                               |
| xml_etree_parse                  | 118 ms                                                             | 121 ms: 1.03x slower                                               |
| quadtree_nbody                   | 654 ms                                                             | 675 ms: 1.03x slower                                               |
| unpickle                         | 10.5 us                                                            | 10.8 us: 1.03x slower                                              |
| thrift                           | 2.00 ms                                                            | 2.07 ms: 1.04x slower                                              |
| xml_etree_generate               | 68.1 ms                                                            | 70.6 ms: 1.04x slower                                              |
| base85_small                     | 4.66 ms                                                            | 4.85 ms: 1.04x slower                                              |
| networkx_connected_components    | 425 ms                                                             | 443 ms: 1.04x slower                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 342 ms: 1.05x slower                                               |
| networkx_k_core                  | 2.05 sec                                                           | 2.16 sec: 1.05x slower                                             |
| hexiom                           | 4.50 ms                                                            | 4.75 ms: 1.06x slower                                              |
| regex_compile                    | 97.0 ms                                                            | 102 ms: 1.06x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 88.3 ms: 1.06x slower                                              |
| spectral_norm                    | 64.1 ms                                                            | 68.6 ms: 1.07x slower                                              |
| base85_large                     | 249 ms                                                             | 267 ms: 1.07x slower                                               |
| genshi_xml                       | 43.2 ms                                                            | 46.3 ms: 1.07x slower                                              |
| regex_dna                        | 147 ms                                                             | 159 ms: 1.08x slower                                               |
| thread_counter_optimized         | 18.3 ms                                                            | 19.7 ms: 1.08x slower                                              |
| chameleon                        | 10.3 ms                                                            | 11.1 ms: 1.08x slower                                              |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.37 sec: 1.09x slower                                             |
| richards_super                   | 40.3 ms                                                            | 43.8 ms: 1.09x slower                                              |
| async_generators                 | 231 ms                                                             | 251 ms: 1.09x slower                                               |
| decimal_pi                       | 209 ms                                                             | 228 ms: 1.09x slower                                               |
| richards                         | 34.7 ms                                                            | 38.2 ms: 1.10x slower                                              |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 14.2 ms: 1.10x slower                                              |
| scimark_monte_carlo              | 42.3 ms                                                            | 47.2 ms: 1.11x slower                                              |
| noop                             | 19.2 ns                                                            | 21.4 ns: 1.12x slower                                              |
| thread_counter_naive             | 21.2 ms                                                            | 23.7 ms: 1.12x slower                                              |
| base32_large                     | 289 ms                                                             | 325 ms: 1.12x slower                                               |
| html5lib                         | 45.3 ms                                                            | 50.9 ms: 1.12x slower                                              |
| unpickle_list                    | 3.03 us                                                            | 3.42 us: 1.13x slower                                              |
| base32_small                     | 5.71 ms                                                            | 6.46 ms: 1.13x slower                                              |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 494 ms: 1.15x slower                                               |
| float                            | 51.2 ms                                                            | 59.2 ms: 1.16x slower                                              |
| fannkuch                         | 246 ms                                                             | 287 ms: 1.16x slower                                               |
| deepcopy_reduce                  | 2.02 us                                                            | 2.36 us: 1.17x slower                                              |
| genshi_text                      | 18.0 ms                                                            | 21.1 ms: 1.17x slower                                              |
| regex_effbot                     | 1.98 ms                                                            | 2.33 ms: 1.18x slower                                              |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 507 ms: 1.19x slower                                               |
| tomli_loads                      | 1.49 sec                                                           | 1.77 sec: 1.19x slower                                             |
| coroutines                       | 15.1 ms                                                            | 18.2 ms: 1.20x slower                                              |
| ascii85_small                    | 13.0 ms                                                            | 15.7 ms: 1.21x slower                                              |
| async_tree_eager_memoization     | 183 ms                                                             | 221 ms: 1.21x slower                                               |
| pyflate                          | 309 ms                                                             | 374 ms: 1.21x slower                                               |
| ascii85_large                    | 681 ms                                                             | 824 ms: 1.21x slower                                               |
| scimark_sor                      | 78.2 ms                                                            | 96.2 ms: 1.23x slower                                              |
| thread_montecarlo_naive          | 14.3 ms                                                            | 18.1 ms: 1.27x slower                                              |
| async_tree_eager_io_tg           | 565 ms                                                             | 731 ms: 1.29x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 290 ms: 1.29x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 753 ms: 1.33x slower                                               |
| async_tree_none                  | 233 ms                                                             | 312 ms: 1.34x slower                                               |
| deepcopy                         | 198 us                                                             | 267 us: 1.35x slower                                               |
| async_tree_io                    | 549 ms                                                             | 743 ms: 1.35x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 392 ms: 1.38x slower                                               |
| go                               | 91.1 ms                                                            | 129 ms: 1.42x slower                                               |
| thread_pipeline_naive            | 34.9 ms                                                            | 49.8 ms: 1.43x slower                                              |
| async_tree_io_tg                 | 545 ms                                                             | 781 ms: 1.43x slower                                               |
| deepcopy_memo                    | 19.1 us                                                            | 27.8 us: 1.45x slower                                              |
| async_tree_memoization_tg        | 279 ms                                                             | 421 ms: 1.51x slower                                               |
| mdp                              | 971 ms                                                             | 2.05 sec: 2.12x slower                                             |
| thread_memo_naive                | 12.4 ms                                                            | 37.9 ms: 3.05x slower                                              |
| base16_small                     | 265 us                                                             | 836 us: 3.16x slower                                               |
| base16_large                     | 6.35 ms                                                            | 42.7 ms: 6.72x slower                                              |
| Geometric mean                   | (ref)                                                              | 1.06x slower                                                       |

Benchmark hidden because not significant (6): xml_etree_process, base64_large, regex_v8, comprehensions, xdsl_constant_fold, pylint

- Geometric mean (including insignificant results): 1.060x slower

# HPT report

- Reliability score: 99.98% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 0.92x