# Results vs. 3.13.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.041x faster
- HPT reliability: 93.16%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.08x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.95 ms                                                         | 10.00 ms: 1.00x slower                                          |
| docutils       | 1.89 sec                                                        | 1.88 sec: 1.00x faster                                          |
| html5lib       | 51.7 ms                                                         | 49.6 ms: 1.04x faster                                           |
| tornado_http   | 101 ms                                                          | 102 ms: 1.01x slower                                            |
| Geometric mean | (ref)                                                           | 1.01x faster                                                    |

Benchmark hidden because not significant (1): fastapi_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_memoization_tg        | 419 ms                                                          | 338 ms: 1.24x faster                                            |
| async_tree_none                  | 308 ms                                                          | 266 ms: 1.16x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 189 ms: 1.16x faster                                            |
| async_tree_eager_io              | 749 ms                                                          | 650 ms: 1.15x faster                                            |
| async_tree_memoization           | 388 ms                                                          | 345 ms: 1.12x faster                                            |
| async_tree_io                    | 741 ms                                                          | 668 ms: 1.11x faster                                            |
| async_tree_io_tg                 | 778 ms                                                          | 701 ms: 1.11x faster                                            |
| async_tree_eager                 | 89.6 ms                                                         | 83.2 ms: 1.08x faster                                           |
| async_tree_eager_io_tg           | 728 ms                                                          | 682 ms: 1.07x faster                                            |
| async_tree_none_tg               | 291 ms                                                          | 273 ms: 1.06x faster                                            |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 451 ms: 1.05x faster                                            |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 468 ms: 1.05x faster                                            |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 314 ms: 1.03x faster                                            |
| async_generators                 | 240 ms                                                          | 235 ms: 1.02x faster                                            |
| asyncio_websockets               | 303 ms                                                          | 299 ms: 1.02x faster                                            |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.29 sec: 1.00x slower                                          |
| coroutines                       | 15.4 ms                                                         | 15.6 ms: 1.01x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 394 ms: 1.38x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 286 ms: 1.63x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 212 ms: 3.61x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.04x slower                                                    |

Benchmark hidden because not significant (1): asyncio_tcp

Benchmarks with tag 'baseline':
===============================

Benchmark hidden because not significant (1): noop

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_pi        | 222 ms                                                          | 214 ms: 1.04x faster                                            |
| decimal_factorial | 177 ms                                                          | 174 ms: 1.02x faster                                            |
| Geometric mean    | (ref)                                                           | 1.03x faster                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 57.0 ms                                                         | 50.7 ms: 1.12x faster                                           |
| quadtree_nbody | 626 ms                                                          | 612 ms: 1.02x faster                                            |
| pidigits       | 189 ms                                                          | 188 ms: 1.01x faster                                            |
| nbody          | 65.9 ms                                                         | 70.3 ms: 1.07x slower                                           |
| Geometric mean | (ref)                                                           | 1.02x faster                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_effbot   | 2.30 ms                                                         | 1.99 ms: 1.16x faster                                           |
| regex_dna      | 162 ms                                                          | 152 ms: 1.06x faster                                            |
| regex_compile  | 98.5 ms                                                         | 95.4 ms: 1.03x faster                                           |
| regex_v8       | 15.2 ms                                                         | 16.2 ms: 1.06x slower                                           |
| Geometric mean | (ref)                                                           | 1.05x faster                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large         | 37.0 ms                                                         | 5.34 ms: 6.93x faster                                           |
| base16_small         | 740 us                                                          | 307 us: 2.41x faster                                            |
| pickle_list          | 3.14 us                                                         | 2.86 us: 1.10x faster                                           |
| tomli_loads          | 1.62 sec                                                        | 1.53 sec: 1.06x faster                                          |
| pickle_dict          | 22.0 us                                                         | 21.2 us: 1.04x faster                                           |
| ascii85_large        | 717 ms                                                          | 695 ms: 1.03x faster                                            |
| xml_etree_iterparse  | 79.9 ms                                                         | 77.5 ms: 1.03x faster                                           |
| ascii85_small        | 13.6 ms                                                         | 13.3 ms: 1.02x faster                                           |
| xml_etree_process    | 46.6 ms                                                         | 45.8 ms: 1.02x faster                                           |
| base64_small         | 177 us                                                          | 175 us: 1.02x faster                                            |
| xml_etree_generate   | 64.2 ms                                                         | 63.4 ms: 1.01x faster                                           |
| base64_large         | 3.33 ms                                                         | 3.32 ms: 1.00x faster                                           |
| urlsafe_base64_small | 325 us                                                          | 327 us: 1.01x slower                                            |
| base85_large         | 252 ms                                                          | 255 ms: 1.01x slower                                            |
| json_dumps           | 6.95 ms                                                         | 7.11 ms: 1.02x slower                                           |
| unpickle_pure_python | 151 us                                                          | 155 us: 1.03x slower                                            |
| base32_large         | 296 ms                                                          | 306 ms: 1.03x slower                                            |
| base32_small         | 5.79 ms                                                         | 6.00 ms: 1.04x slower                                           |
| base85_small         | 4.59 ms                                                         | 4.83 ms: 1.05x slower                                           |
| xml_etree_parse      | 104 ms                                                          | 110 ms: 1.05x slower                                            |
| unpickle_list        | 3.33 us                                                         | 3.54 us: 1.06x slower                                           |
| pickle_pure_python   | 223 us                                                          | 240 us: 1.07x slower                                            |
| pickle               | 7.44 us                                                         | 8.29 us: 1.11x slower                                           |
| json_loads           | 16.2 us                                                         | 19.5 us: 1.20x slower                                           |
| Geometric mean       | (ref)                                                           | 1.10x faster                                                    |

Benchmark hidden because not significant (1): unpickle

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup_no_site | 6.46 ms                                                         | 6.45 ms: 1.00x faster                                           |
| python_startup         | 9.51 ms                                                         | 9.90 ms: 1.04x slower                                           |
| Geometric mean         | (ref)                                                           | 1.02x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| genshi_text     | 17.8 ms                                                         | 17.3 ms: 1.03x faster                                           |
| genshi_xml      | 41.3 ms                                                         | 40.4 ms: 1.02x faster                                           |
| django_template | 27.6 ms                                                         | 28.2 ms: 1.02x slower                                           |
| mako            | 7.16 ms                                                         | 7.57 ms: 1.06x slower                                           |
| Geometric mean  | (ref)                                                           | 1.01x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_memo_naive           | 36.1 ms                                                         | 11.7 ms: 3.09x faster                                           |
| thread_pipeline_naive       | 47.3 ms                                                         | 32.8 ms: 1.44x faster                                           |
| thread_montecarlo_naive     | 19.0 ms                                                         | 17.5 ms: 1.09x faster                                           |
| thread_counter_naive        | 20.6 ms                                                         | 20.9 ms: 1.01x slower                                           |
| thread_montecarlo_optimized | 14.5 ms                                                         | 15.3 ms: 1.06x slower                                           |
| thread_counter_optimized    | 16.5 ms                                                         | 17.8 ms: 1.08x slower                                           |
| thread_memo_optimized       | 15.3 ms                                                         | 16.5 ms: 1.08x slower                                           |
| thread_accumulate_naive     | 33.4 ms                                                         | 37.2 ms: 1.11x slower                                           |
| thread_pipeline_optimized   | 20.9 ms                                                         | 23.4 ms: 1.12x slower                                           |
| thread_mandelbrot_naive     | 210 ms                                                          | 237 ms: 1.13x slower                                            |
| thread_mandelbrot_optimized | 208 ms                                                          | 235 ms: 1.13x slower                                            |
| thread_accumulate_optimized | 32.3 ms                                                         | 37.1 ms: 1.15x slower                                           |
| Geometric mean              | (ref)                                                           | 1.06x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| base16_large                     | 37.0 ms                                                         | 5.34 ms: 6.93x faster                                           |
| thread_memo_naive                | 36.1 ms                                                         | 11.7 ms: 3.09x faster                                           |
| base16_small                     | 740 us                                                          | 307 us: 2.41x faster                                            |
| mdp                              | 2.15 sec                                                        | 961 ms: 2.23x faster                                            |
| argparse_many_optionals          | 12.8 ms                                                         | 7.69 ms: 1.67x faster                                           |
| deepcopy_memo                    | 26.5 us                                                         | 18.3 us: 1.45x faster                                           |
| thread_pipeline_naive            | 47.3 ms                                                         | 32.8 ms: 1.44x faster                                           |
| deepcopy                         | 269 us                                                          | 193 us: 1.39x faster                                            |
| go                               | 117 ms                                                          | 85.8 ms: 1.36x faster                                           |
| async_tree_memoization_tg        | 419 ms                                                          | 338 ms: 1.24x faster                                            |
| deepcopy_reduce                  | 2.40 us                                                         | 2.01 us: 1.20x faster                                           |
| richards                         | 37.8 ms                                                         | 32.4 ms: 1.17x faster                                           |
| regex_effbot                     | 2.30 ms                                                         | 1.99 ms: 1.16x faster                                           |
| async_tree_none                  | 308 ms                                                          | 266 ms: 1.16x faster                                            |
| async_tree_eager_memoization     | 219 ms                                                          | 189 ms: 1.16x faster                                            |
| richards_super                   | 42.8 ms                                                         | 37.1 ms: 1.16x faster                                           |
| async_tree_eager_io              | 749 ms                                                          | 650 ms: 1.15x faster                                            |
| float                            | 57.0 ms                                                         | 50.7 ms: 1.12x faster                                           |
| async_tree_memoization           | 388 ms                                                          | 345 ms: 1.12x faster                                            |
| async_tree_io                    | 741 ms                                                          | 668 ms: 1.11x faster                                            |
| async_tree_io_tg                 | 778 ms                                                          | 701 ms: 1.11x faster                                            |
| pyflate                          | 342 ms                                                          | 309 ms: 1.11x faster                                            |
| pickle_list                      | 3.14 us                                                         | 2.86 us: 1.10x faster                                           |
| scimark_monte_carlo              | 46.5 ms                                                         | 42.4 ms: 1.10x faster                                           |
| thread_montecarlo_naive          | 19.0 ms                                                         | 17.5 ms: 1.09x faster                                           |
| telco                            | 5.83 ms                                                         | 5.40 ms: 1.08x faster                                           |
| pprint_safe_repr                 | 530 ms                                                          | 491 ms: 1.08x faster                                            |
| async_tree_eager                 | 89.6 ms                                                         | 83.2 ms: 1.08x faster                                           |
| async_tree_eager_io_tg           | 728 ms                                                          | 682 ms: 1.07x faster                                            |
| unpack_sequence                  | 27.1 ns                                                         | 25.4 ns: 1.07x faster                                           |
| async_tree_none_tg               | 291 ms                                                          | 273 ms: 1.06x faster                                            |
| pprint_pformat                   | 1.09 sec                                                        | 1.03 sec: 1.06x faster                                          |
| regex_dna                        | 162 ms                                                          | 152 ms: 1.06x faster                                            |
| tomli_loads                      | 1.62 sec                                                        | 1.53 sec: 1.06x faster                                          |
| async_tree_cpu_io_mixed          | 474 ms                                                          | 451 ms: 1.05x faster                                            |
| thrift                           | 2.02 ms                                                         | 1.92 ms: 1.05x faster                                           |
| async_tree_cpu_io_mixed_tg       | 490 ms                                                          | 468 ms: 1.05x faster                                            |
| bpe_tokeniser                    | 3.30 sec                                                        | 3.15 sec: 1.04x faster                                          |
| html5lib                         | 51.7 ms                                                         | 49.6 ms: 1.04x faster                                           |
| scimark_sor                      | 78.9 ms                                                         | 75.6 ms: 1.04x faster                                           |
| sqlglot_v2_transpile             | 1.20 ms                                                         | 1.16 ms: 1.04x faster                                           |
| networkx_k_core                  | 2.16 sec                                                        | 2.07 sec: 1.04x faster                                          |
| sqlglot_v2_parse                 | 958 us                                                          | 921 us: 1.04x faster                                            |
| decimal_pi                       | 222 ms                                                          | 214 ms: 1.04x faster                                            |
| pickle_dict                      | 22.0 us                                                         | 21.2 us: 1.04x faster                                           |
| generators                       | 21.2 ms                                                         | 20.5 ms: 1.03x faster                                           |
| genshi_text                      | 17.8 ms                                                         | 17.3 ms: 1.03x faster                                           |
| regex_compile                    | 98.5 ms                                                         | 95.4 ms: 1.03x faster                                           |
| ascii85_large                    | 717 ms                                                          | 695 ms: 1.03x faster                                            |
| xml_etree_iterparse              | 79.9 ms                                                         | 77.5 ms: 1.03x faster                                           |
| async_tree_eager_cpu_io_mixed    | 323 ms                                                          | 314 ms: 1.03x faster                                            |
| quadtree_nbody                   | 626 ms                                                          | 612 ms: 1.02x faster                                            |
| ascii85_small                    | 13.6 ms                                                         | 13.3 ms: 1.02x faster                                           |
| hexiom                           | 4.30 ms                                                         | 4.21 ms: 1.02x faster                                           |
| genshi_xml                       | 41.3 ms                                                         | 40.4 ms: 1.02x faster                                           |
| async_generators                 | 240 ms                                                          | 235 ms: 1.02x faster                                            |
| xml_etree_process                | 46.6 ms                                                         | 45.8 ms: 1.02x faster                                           |
| decimal_factorial                | 177 ms                                                          | 174 ms: 1.02x faster                                            |
| asyncio_websockets               | 303 ms                                                          | 299 ms: 1.02x faster                                            |
| base64_small                     | 177 us                                                          | 175 us: 1.02x faster                                            |
| chaos                            | 45.1 ms                                                         | 44.6 ms: 1.01x faster                                           |
| xml_etree_generate               | 64.2 ms                                                         | 63.4 ms: 1.01x faster                                           |
| deltablue                        | 2.41 ms                                                         | 2.39 ms: 1.01x faster                                           |
| sympy_integrate                  | 15.8 ms                                                         | 15.7 ms: 1.01x faster                                           |
| pidigits                         | 189 ms                                                          | 188 ms: 1.01x faster                                            |
| sqlglot_v2_normalize             | 80.5 ms                                                         | 80.0 ms: 1.01x faster                                           |
| docutils                         | 1.89 sec                                                        | 1.88 sec: 1.00x faster                                          |
| sqlglot_v2_optimize              | 40.1 ms                                                         | 39.9 ms: 1.00x faster                                           |
| base64_large                     | 3.33 ms                                                         | 3.32 ms: 1.00x faster                                           |
| python_startup_no_site           | 6.46 ms                                                         | 6.45 ms: 1.00x faster                                           |
| asyncio_tcp_ssl                  | 1.29 sec                                                        | 1.29 sec: 1.00x slower                                          |
| chameleon                        | 9.95 ms                                                         | 10.00 ms: 1.00x slower                                          |
| sympy_expand                     | 336 ms                                                          | 338 ms: 1.01x slower                                            |
| urlsafe_base64_small             | 325 us                                                          | 327 us: 1.01x slower                                            |
| coverage                         | 55.8 ms                                                         | 56.1 ms: 1.01x slower                                           |
| logging_simple                   | 4.71 us                                                         | 4.73 us: 1.01x slower                                           |
| sympy_str                        | 197 ms                                                          | 198 ms: 1.01x slower                                            |
| mypy2                            | 724 ms                                                          | 730 ms: 1.01x slower                                            |
| tornado_http                     | 101 ms                                                          | 102 ms: 1.01x slower                                            |
| meteor_contest                   | 84.4 ms                                                         | 85.3 ms: 1.01x slower                                           |
| raytrace                         | 195 ms                                                          | 197 ms: 1.01x slower                                            |
| base85_large                     | 252 ms                                                          | 255 ms: 1.01x slower                                            |
| thread_counter_naive             | 20.6 ms                                                         | 20.9 ms: 1.01x slower                                           |
| comprehensions                   | 10.9 us                                                         | 11.1 us: 1.01x slower                                           |
| coroutines                       | 15.4 ms                                                         | 15.6 ms: 1.01x slower                                           |
| fannkuch                         | 246 ms                                                          | 250 ms: 1.02x slower                                            |
| sympy_sum                        | 106 ms                                                          | 108 ms: 1.02x slower                                            |
| networkx_shortest_path           | 437 ms                                                          | 446 ms: 1.02x slower                                            |
| json_dumps                       | 6.95 ms                                                         | 7.11 ms: 1.02x slower                                           |
| django_template                  | 27.6 ms                                                         | 28.2 ms: 1.02x slower                                           |
| pathlib                          | 12.8 ms                                                         | 13.1 ms: 1.02x slower                                           |
| spectral_norm                    | 65.9 ms                                                         | 67.7 ms: 1.03x slower                                           |
| networkx_connected_components    | 425 ms                                                          | 437 ms: 1.03x slower                                            |
| scimark_lu                       | 74.5 ms                                                         | 76.8 ms: 1.03x slower                                           |
| unpickle_pure_python             | 151 us                                                          | 155 us: 1.03x slower                                            |
| sqlalchemy_imperative            | 13.9 ms                                                         | 14.3 ms: 1.03x slower                                           |
| base32_large                     | 296 ms                                                          | 306 ms: 1.03x slower                                            |
| base32_small                     | 5.79 ms                                                         | 6.00 ms: 1.04x slower                                           |
| python_startup                   | 9.51 ms                                                         | 9.90 ms: 1.04x slower                                           |
| pycparser                        | 860 ms                                                          | 897 ms: 1.04x slower                                            |
| scimark_fft                      | 226 ms                                                          | 237 ms: 1.05x slower                                            |
| nqueens                          | 53.6 ms                                                         | 56.2 ms: 1.05x slower                                           |
| base85_small                     | 4.59 ms                                                         | 4.83 ms: 1.05x slower                                           |
| xml_etree_parse                  | 104 ms                                                          | 110 ms: 1.05x slower                                            |
| json                             | 3.51 ms                                                         | 3.69 ms: 1.05x slower                                           |
| mako                             | 7.16 ms                                                         | 7.57 ms: 1.06x slower                                           |
| thread_montecarlo_optimized      | 14.5 ms                                                         | 15.3 ms: 1.06x slower                                           |
| regex_v8                         | 15.2 ms                                                         | 16.2 ms: 1.06x slower                                           |
| unpickle_list                    | 3.33 us                                                         | 3.54 us: 1.06x slower                                           |
| gc_traversal                     | 3.07 ms                                                         | 3.27 ms: 1.07x slower                                           |
| nbody                            | 65.9 ms                                                         | 70.3 ms: 1.07x slower                                           |
| create_gc_cycles                 | 1.75 ms                                                         | 1.87 ms: 1.07x slower                                           |
| scimark_sparse_mat_mult          | 3.14 ms                                                         | 3.37 ms: 1.07x slower                                           |
| pickle_pure_python               | 223 us                                                          | 240 us: 1.07x slower                                            |
| thread_counter_optimized         | 16.5 ms                                                         | 17.8 ms: 1.08x slower                                           |
| thread_memo_optimized            | 15.3 ms                                                         | 16.5 ms: 1.08x slower                                           |
| crypto_pyaes                     | 50.9 ms                                                         | 55.5 ms: 1.09x slower                                           |
| argparse_subparsers              | 452 us                                                          | 501 us: 1.11x slower                                            |
| thread_accumulate_naive          | 33.4 ms                                                         | 37.2 ms: 1.11x slower                                           |
| pickle                           | 7.44 us                                                         | 8.29 us: 1.11x slower                                           |
| thread_pipeline_optimized        | 20.9 ms                                                         | 23.4 ms: 1.12x slower                                           |
| thread_mandelbrot_naive          | 210 ms                                                          | 237 ms: 1.13x slower                                            |
| thread_mandelbrot_optimized      | 208 ms                                                          | 235 ms: 1.13x slower                                            |
| logging_silent                   | 61.0 ns                                                         | 69.5 ns: 1.14x slower                                           |
| thread_accumulate_optimized      | 32.3 ms                                                         | 37.1 ms: 1.15x slower                                           |
| json_loads                       | 16.2 us                                                         | 19.5 us: 1.20x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 285 ms                                                          | 394 ms: 1.38x slower                                            |
| async_tree_eager_memoization_tg  | 175 ms                                                          | 286 ms: 1.63x slower                                            |
| async_tree_eager_tg              | 58.6 ms                                                         | 212 ms: 3.61x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.04x faster                                                    |

Benchmark hidden because not significant (8): asyncio_tcp, pylint, noop, logging_format, unpickle, typing_runtime_protocols, fastapi_http, xdsl_constant_fold

- Geometric mean (including insignificant results): 1.041x faster

# HPT report

- Reliability score: 93.16% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.08x