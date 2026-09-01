# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.008x slower
- HPT reliability: 99.78%
- HPT 99th percentile: 1.00x slower
- Memory change: 0.98x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 10.5 ms: 1.02x slower                                              |
| docutils       | 1.98 sec                                                           | 1.89 sec: 1.04x faster                                             |
| fastapi_http   | 222 ms                                                             | 220 ms: 1.01x faster                                               |
| html5lib       | 45.3 ms                                                            | 48.1 ms: 1.06x slower                                              |
| tornado_http   | 101 ms                                                             | 103 ms: 1.02x slower                                               |
| Geometric mean | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.08x faster                                               |
| asyncio_websockets               | 305 ms                                                             | 297 ms: 1.03x faster                                               |
| async_tree_eager                 | 83.0 ms                                                            | 85.4 ms: 1.03x slower                                              |
| coroutines                       | 15.1 ms                                                            | 15.6 ms: 1.03x slower                                              |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 339 ms: 1.03x slower                                               |
| async_generators                 | 231 ms                                                             | 239 ms: 1.04x slower                                               |
| async_tree_eager_memoization     | 183 ms                                                             | 193 ms: 1.06x slower                                               |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 480 ms: 1.12x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 420 ms: 1.12x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 494 ms: 1.16x slower                                               |
| async_tree_none                  | 233 ms                                                             | 270 ms: 1.16x slower                                               |
| async_tree_eager_tg              | 182 ms                                                             | 215 ms: 1.18x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 670 ms: 1.18x slower                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 291 ms: 1.23x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 345 ms: 1.23x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 697 ms: 1.23x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 277 ms: 1.23x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 354 ms: 1.24x slower                                               |
| async_tree_io                    | 549 ms                                                             | 683 ms: 1.24x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 715 ms: 1.31x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.12x slower                                                       |

Benchmark hidden because not significant (1): asyncio_tcp_ssl

Benchmarks with tag 'baseline':
===============================

Benchmark hidden because not significant (1): noop

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 174 ms: 1.00x faster                                               |
| decimal_pi        | 209 ms                                                             | 212 ms: 1.01x slower                                               |
| Geometric mean    | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| quadtree_nbody | 654 ms                                                             | 631 ms: 1.04x faster                                               |
| float          | 51.2 ms                                                            | 54.3 ms: 1.06x slower                                              |
| Geometric mean | (ref)                                                              | 1.01x slower                                                       |

Benchmark hidden because not significant (2): pidigits, nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_compile  | 97.0 ms                                                            | 97.9 ms: 1.01x slower                                              |
| regex_dna      | 147 ms                                                             | 151 ms: 1.02x slower                                               |
| regex_v8       | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| regex_effbot   | 1.98 ms                                                            | 2.13 ms: 1.08x slower                                              |
| Geometric mean | (ref)                                                              | 1.03x slower                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark           | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|---------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| xml_etree_iterparse | 85.5 ms                                                            | 80.4 ms: 1.06x faster                                              |
| pickle_dict         | 20.0 us                                                            | 19.4 us: 1.03x faster                                              |
| xml_etree_process   | 50.0 ms                                                            | 48.9 ms: 1.02x faster                                              |
| base64_small        | 227 us                                                             | 223 us: 1.02x faster                                               |
| xml_etree_generate  | 68.1 ms                                                            | 67.5 ms: 1.01x faster                                              |
| pickle_pure_python  | 251 us                                                             | 249 us: 1.01x faster                                               |
| base64_large        | 5.70 ms                                                            | 5.68 ms: 1.00x faster                                              |
| base16_large        | 6.35 ms                                                            | 6.33 ms: 1.00x faster                                              |
| tomli_loads         | 1.49 sec                                                           | 1.50 sec: 1.01x slower                                             |
| base85_small        | 4.66 ms                                                            | 4.72 ms: 1.01x slower                                              |
| base85_large        | 249 ms                                                             | 254 ms: 1.02x slower                                               |
| ascii85_large       | 681 ms                                                             | 699 ms: 1.03x slower                                               |
| ascii85_small       | 13.0 ms                                                            | 13.4 ms: 1.03x slower                                              |
| json_loads          | 18.6 us                                                            | 19.2 us: 1.03x slower                                              |
| json_dumps          | 7.52 ms                                                            | 7.79 ms: 1.03x slower                                              |
| xml_etree_parse     | 118 ms                                                             | 123 ms: 1.05x slower                                               |
| pickle_list         | 3.03 us                                                            | 3.20 us: 1.06x slower                                              |
| Geometric mean      | (ref)                                                              | 1.00x slower                                                       |

Benchmark hidden because not significant (8): urlsafe_base64_small, base32_small, unpickle_pure_python, base32_large, unpickle_list, base16_small, pickle, unpickle

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup_no_site | 6.52 ms                                                            | 6.53 ms: 1.00x slower                                              |
| python_startup         | 9.93 ms                                                            | 10.0 ms: 1.01x slower                                              |
| Geometric mean         | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 30.3 ms: 1.01x faster                                              |
| mako            | 8.69 ms                                                            | 8.64 ms: 1.01x faster                                              |
| genshi_text     | 18.0 ms                                                            | 18.2 ms: 1.01x slower                                              |
| genshi_xml      | 43.2 ms                                                            | 43.8 ms: 1.01x slower                                              |
| Geometric mean  | (ref)                                                              | 1.00x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 207 ms                                                             | 202 ms: 1.02x faster                                               |
| thread_mandelbrot_optimized | 205 ms                                                             | 201 ms: 1.02x faster                                               |
| thread_pipeline_optimized   | 25.8 ms                                                            | 25.5 ms: 1.01x faster                                              |
| thread_accumulate_optimized | 39.5 ms                                                            | 39.0 ms: 1.01x faster                                              |
| thread_accumulate_naive     | 40.4 ms                                                            | 40.0 ms: 1.01x faster                                              |
| thread_memo_naive           | 12.4 ms                                                            | 12.3 ms: 1.01x faster                                              |
| thread_montecarlo_optimized | 12.9 ms                                                            | 12.9 ms: 1.00x slower                                              |
| thread_counter_optimized    | 18.3 ms                                                            | 18.4 ms: 1.01x slower                                              |
| thread_pipeline_naive       | 34.9 ms                                                            | 35.3 ms: 1.01x slower                                              |
| thread_counter_naive        | 21.2 ms                                                            | 21.6 ms: 1.02x slower                                              |
| thread_montecarlo_naive     | 14.3 ms                                                            | 14.8 ms: 1.04x slower                                              |
| Geometric mean              | (ref)                                                              | 1.00x faster                                                       |

Benchmark hidden because not significant (1): thread_memo_optimized

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| argparse_many_optionals          | 34.5 ms                                                            | 8.02 ms: 4.30x faster                                              |
| argparse_subparsers              | 687 us                                                             | 503 us: 1.37x faster                                               |
| create_gc_cycles                 | 2.02 ms                                                            | 1.87 ms: 1.08x faster                                              |
| asyncio_tcp                      | 324 ms                                                             | 301 ms: 1.08x faster                                               |
| xml_etree_iterparse              | 85.5 ms                                                            | 80.4 ms: 1.06x faster                                              |
| deltablue                        | 2.76 ms                                                            | 2.61 ms: 1.06x faster                                              |
| logging_format                   | 6.00 us                                                            | 5.73 us: 1.05x faster                                              |
| docutils                         | 1.98 sec                                                           | 1.89 sec: 1.04x faster                                             |
| mypy2                            | 780 ms                                                             | 753 ms: 1.04x faster                                               |
| quadtree_nbody                   | 654 ms                                                             | 631 ms: 1.04x faster                                               |
| gc_traversal                     | 3.36 ms                                                            | 3.25 ms: 1.03x faster                                              |
| pickle_dict                      | 20.0 us                                                            | 19.4 us: 1.03x faster                                              |
| asyncio_websockets               | 305 ms                                                             | 297 ms: 1.03x faster                                               |
| hexiom                           | 4.50 ms                                                            | 4.39 ms: 1.02x faster                                              |
| comprehensions                   | 11.4 us                                                            | 11.1 us: 1.02x faster                                              |
| xml_etree_process                | 50.0 ms                                                            | 48.9 ms: 1.02x faster                                              |
| scimark_sor                      | 78.2 ms                                                            | 76.6 ms: 1.02x faster                                              |
| thread_mandelbrot_naive          | 207 ms                                                             | 202 ms: 1.02x faster                                               |
| thread_mandelbrot_optimized      | 205 ms                                                             | 201 ms: 1.02x faster                                               |
| generators                       | 24.2 ms                                                            | 23.7 ms: 1.02x faster                                              |
| base64_small                     | 227 us                                                             | 223 us: 1.02x faster                                               |
| typing_runtime_protocols         | 115 us                                                             | 113 us: 1.02x faster                                               |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 2.84 ms: 1.02x faster                                              |
| networkx_shortest_path           | 447 ms                                                             | 440 ms: 1.01x faster                                               |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.19 ms: 1.01x faster                                              |
| thread_pipeline_optimized        | 25.8 ms                                                            | 25.5 ms: 1.01x faster                                              |
| thread_accumulate_optimized      | 39.5 ms                                                            | 39.0 ms: 1.01x faster                                              |
| thread_accumulate_naive          | 40.4 ms                                                            | 40.0 ms: 1.01x faster                                              |
| xml_etree_generate               | 68.1 ms                                                            | 67.5 ms: 1.01x faster                                              |
| chaos                            | 42.9 ms                                                            | 42.5 ms: 1.01x faster                                              |
| thread_memo_naive                | 12.4 ms                                                            | 12.3 ms: 1.01x faster                                              |
| pickle_pure_python               | 251 us                                                             | 249 us: 1.01x faster                                               |
| pprint_safe_repr                 | 534 ms                                                             | 531 ms: 1.01x faster                                               |
| django_template                  | 30.5 ms                                                            | 30.3 ms: 1.01x faster                                              |
| fastapi_http                     | 222 ms                                                             | 220 ms: 1.01x faster                                               |
| mako                             | 8.69 ms                                                            | 8.64 ms: 1.01x faster                                              |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 84.5 ms: 1.00x faster                                              |
| base64_large                     | 5.70 ms                                                            | 5.68 ms: 1.00x faster                                              |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 41.6 ms: 1.00x faster                                              |
| base16_large                     | 6.35 ms                                                            | 6.33 ms: 1.00x faster                                              |
| decimal_factorial                | 174 ms                                                             | 174 ms: 1.00x faster                                               |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 12.9 ms: 1.00x slower                                              |
| python_startup_no_site           | 6.52 ms                                                            | 6.53 ms: 1.00x slower                                              |
| pathlib                          | 12.7 ms                                                            | 12.7 ms: 1.00x slower                                              |
| sqlglot_v2_parse                 | 954 us                                                             | 958 us: 1.00x slower                                               |
| deepcopy                         | 198 us                                                             | 199 us: 1.01x slower                                               |
| tomli_loads                      | 1.49 sec                                                           | 1.50 sec: 1.01x slower                                             |
| thread_counter_optimized         | 18.3 ms                                                            | 18.4 ms: 1.01x slower                                              |
| sympy_str                        | 200 ms                                                             | 201 ms: 1.01x slower                                               |
| python_startup                   | 9.93 ms                                                            | 10.0 ms: 1.01x slower                                              |
| genshi_text                      | 18.0 ms                                                            | 18.2 ms: 1.01x slower                                              |
| richards                         | 34.7 ms                                                            | 35.0 ms: 1.01x slower                                              |
| pyflate                          | 309 ms                                                             | 312 ms: 1.01x slower                                               |
| regex_compile                    | 97.0 ms                                                            | 97.9 ms: 1.01x slower                                              |
| networkx_connected_components    | 425 ms                                                             | 430 ms: 1.01x slower                                               |
| genshi_xml                       | 43.2 ms                                                            | 43.8 ms: 1.01x slower                                              |
| base85_small                     | 4.66 ms                                                            | 4.72 ms: 1.01x slower                                              |
| thread_pipeline_naive            | 34.9 ms                                                            | 35.3 ms: 1.01x slower                                              |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.0 ms: 1.01x slower                                              |
| fannkuch                         | 246 ms                                                             | 250 ms: 1.01x slower                                               |
| mdp                              | 971 ms                                                             | 984 ms: 1.01x slower                                               |
| decimal_pi                       | 209 ms                                                             | 212 ms: 1.01x slower                                               |
| sympy_sum                        | 109 ms                                                             | 110 ms: 1.01x slower                                               |
| logging_simple                   | 5.02 us                                                            | 5.09 us: 1.02x slower                                              |
| logging_silent                   | 59.2 ns                                                            | 60.2 ns: 1.02x slower                                              |
| tornado_http                     | 101 ms                                                             | 103 ms: 1.02x slower                                               |
| deepcopy_reduce                  | 2.02 us                                                            | 2.06 us: 1.02x slower                                              |
| sympy_integrate                  | 15.1 ms                                                            | 15.4 ms: 1.02x slower                                              |
| base85_large                     | 249 ms                                                             | 254 ms: 1.02x slower                                               |
| chameleon                        | 10.3 ms                                                            | 10.5 ms: 1.02x slower                                              |
| thread_counter_naive             | 21.2 ms                                                            | 21.6 ms: 1.02x slower                                              |
| regex_dna                        | 147 ms                                                             | 151 ms: 1.02x slower                                               |
| go                               | 91.1 ms                                                            | 93.1 ms: 1.02x slower                                              |
| unpack_sequence                  | 35.6 ns                                                            | 36.4 ns: 1.02x slower                                              |
| ascii85_large                    | 681 ms                                                             | 699 ms: 1.03x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 85.4 ms: 1.03x slower                                              |
| coroutines                       | 15.1 ms                                                            | 15.6 ms: 1.03x slower                                              |
| regex_v8                         | 15.0 ms                                                            | 15.4 ms: 1.03x slower                                              |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.20 sec: 1.03x slower                                             |
| json                             | 3.46 ms                                                            | 3.57 ms: 1.03x slower                                              |
| ascii85_small                    | 13.0 ms                                                            | 13.4 ms: 1.03x slower                                              |
| json_loads                       | 18.6 us                                                            | 19.2 us: 1.03x slower                                              |
| spectral_norm                    | 64.1 ms                                                            | 66.0 ms: 1.03x slower                                              |
| pylint                           | 222 ms                                                             | 229 ms: 1.03x slower                                               |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 339 ms: 1.03x slower                                               |
| json_dumps                       | 7.52 ms                                                            | 7.79 ms: 1.03x slower                                              |
| async_generators                 | 231 ms                                                             | 239 ms: 1.04x slower                                               |
| thread_montecarlo_naive          | 14.3 ms                                                            | 14.8 ms: 1.04x slower                                              |
| scimark_fft                      | 211 ms                                                             | 220 ms: 1.04x slower                                               |
| xml_etree_parse                  | 118 ms                                                             | 123 ms: 1.05x slower                                               |
| nqueens                          | 59.8 ms                                                            | 62.7 ms: 1.05x slower                                              |
| pickle_list                      | 3.03 us                                                            | 3.20 us: 1.06x slower                                              |
| async_tree_eager_memoization     | 183 ms                                                             | 193 ms: 1.06x slower                                               |
| float                            | 51.2 ms                                                            | 54.3 ms: 1.06x slower                                              |
| html5lib                         | 45.3 ms                                                            | 48.1 ms: 1.06x slower                                              |
| pycparser                        | 878 ms                                                             | 937 ms: 1.07x slower                                               |
| xdsl_constant_fold               | 36.0 ms                                                            | 38.4 ms: 1.07x slower                                              |
| regex_effbot                     | 1.98 ms                                                            | 2.13 ms: 1.08x slower                                              |
| scimark_monte_carlo              | 42.3 ms                                                            | 46.0 ms: 1.09x slower                                              |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 480 ms: 1.12x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 420 ms: 1.12x slower                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 494 ms: 1.16x slower                                               |
| async_tree_none                  | 233 ms                                                             | 270 ms: 1.16x slower                                               |
| async_tree_eager_tg              | 182 ms                                                             | 215 ms: 1.18x slower                                               |
| async_tree_eager_io              | 568 ms                                                             | 670 ms: 1.18x slower                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 291 ms: 1.23x slower                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 345 ms: 1.23x slower                                               |
| async_tree_eager_io_tg           | 565 ms                                                             | 697 ms: 1.23x slower                                               |
| async_tree_none_tg               | 224 ms                                                             | 277 ms: 1.23x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 354 ms: 1.24x slower                                               |
| async_tree_io                    | 549 ms                                                             | 683 ms: 1.24x slower                                               |
| async_tree_io_tg                 | 545 ms                                                             | 715 ms: 1.31x slower                                               |
| Geometric mean                   | (ref)                                                              | 1.01x slower                                                       |

Benchmark hidden because not significant (25): urlsafe_base64_small, base32_small, asyncio_tcp_ssl, unpickle_pure_python, base32_large, unpickle_list, base16_small, telco, deepcopy_memo, thread_memo_optimized, noop, pidigits, meteor_contest, thrift, richards_super, sympy_expand, networkx_k_core, pickle, raytrace, coverage, pprint_pformat, crypto_pyaes, nbody, unpickle, scimark_lu

- Geometric mean (including insignificant results): 1.008x slower

# HPT report

- Reliability score: 99.78% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 0.98x