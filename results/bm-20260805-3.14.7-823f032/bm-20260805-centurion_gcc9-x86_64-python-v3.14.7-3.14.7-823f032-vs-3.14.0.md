# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.021x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.01x slower
- Memory change: 0.99x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.00 ms: 1.05x slower                                          |
| docutils       | 1.95 sec                                                        | 1.88 sec: 1.04x faster                                          |
| fastapi_http   | 216 ms                                                          | 219 ms: 1.01x slower                                            |
| html5lib       | 46.9 ms                                                         | 49.6 ms: 1.06x slower                                           |
| Geometric mean | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (1): tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| asyncio_tcp                      | 325 ms                                                          | 314 ms: 1.03x faster                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.29 sec: 1.01x slower                                          |
| asyncio_websockets               | 296 ms                                                          | 299 ms: 1.01x slower                                            |
| async_tree_eager                 | 81.3 ms                                                         | 83.2 ms: 1.02x slower                                           |
| coroutines                       | 15.1 ms                                                         | 15.6 ms: 1.03x slower                                           |
| async_generators                 | 228 ms                                                          | 235 ms: 1.03x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 189 ms: 1.05x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 394 ms: 1.09x slower                                            |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 451 ms: 1.11x slower                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 468 ms: 1.14x slower                                            |
| async_tree_eager_tg              | 182 ms                                                          | 212 ms: 1.16x slower                                            |
| async_tree_none                  | 228 ms                                                          | 266 ms: 1.17x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 650 ms: 1.18x slower                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 286 ms: 1.21x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 338 ms: 1.22x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 273 ms: 1.22x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 345 ms: 1.23x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 682 ms: 1.24x slower                                            |
| async_tree_io                    | 531 ms                                                          | 668 ms: 1.26x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 701 ms: 1.30x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.12x slower                                                    |

Benchmark hidden because not significant (1): async_tree_eager_cpu_io_mixed

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 20.4 ns: 1.05x slower                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 174 ms: 1.01x slower                                            |
| decimal_pi        | 208 ms                                                          | 214 ms: 1.03x slower                                            |
| Geometric mean    | (ref)                                                           | 1.02x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 188 ms: 1.01x faster                                            |
| quadtree_nbody | 596 ms                                                          | 612 ms: 1.03x slower                                            |
| nbody          | 67.9 ms                                                         | 70.3 ms: 1.04x slower                                           |
| float          | 47.3 ms                                                         | 50.7 ms: 1.07x slower                                           |
| Geometric mean | (ref)                                                           | 1.03x slower                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_dna      | 150 ms                                                          | 152 ms: 1.01x slower                                            |
| regex_compile  | 93.9 ms                                                         | 95.4 ms: 1.02x slower                                           |
| regex_effbot   | 1.95 ms                                                         | 1.99 ms: 1.02x slower                                           |
| regex_v8       | 14.8 ms                                                         | 16.2 ms: 1.09x slower                                           |
| Geometric mean | (ref)                                                           | 1.03x slower                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pickle_list          | 3.24 us                                                         | 2.86 us: 1.13x faster                                           |
| base64_large         | 3.63 ms                                                         | 3.32 ms: 1.09x faster                                           |
| base64_small         | 186 us                                                          | 175 us: 1.06x faster                                            |
| pickle_dict          | 21.5 us                                                         | 21.2 us: 1.02x faster                                           |
| urlsafe_base64_small | 329 us                                                          | 327 us: 1.01x faster                                            |
| base16_small         | 305 us                                                          | 307 us: 1.01x slower                                            |
| pickle               | 8.20 us                                                         | 8.29 us: 1.01x slower                                           |
| xml_etree_generate   | 62.6 ms                                                         | 63.4 ms: 1.01x slower                                           |
| xml_etree_iterparse  | 76.2 ms                                                         | 77.5 ms: 1.02x slower                                           |
| unpickle_pure_python | 152 us                                                          | 155 us: 1.02x slower                                            |
| json_dumps           | 6.95 ms                                                         | 7.11 ms: 1.02x slower                                           |
| xml_etree_process    | 44.7 ms                                                         | 45.8 ms: 1.02x slower                                           |
| base85_large         | 248 ms                                                          | 255 ms: 1.03x slower                                            |
| base85_small         | 4.69 ms                                                         | 4.83 ms: 1.03x slower                                           |
| unpickle_list        | 3.43 us                                                         | 3.54 us: 1.03x slower                                           |
| unpickle             | 10.2 us                                                         | 10.5 us: 1.03x slower                                           |
| ascii85_large        | 667 ms                                                          | 695 ms: 1.04x slower                                            |
| base32_large         | 292 ms                                                          | 306 ms: 1.05x slower                                            |
| ascii85_small        | 12.7 ms                                                         | 13.3 ms: 1.05x slower                                           |
| base32_small         | 5.71 ms                                                         | 6.00 ms: 1.05x slower                                           |
| tomli_loads          | 1.44 sec                                                        | 1.53 sec: 1.06x slower                                          |
| json_loads           | 17.5 us                                                         | 19.5 us: 1.11x slower                                           |
| xml_etree_parse      | 94.3 ms                                                         | 110 ms: 1.17x slower                                            |
| Geometric mean       | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (2): pickle_pure_python, base16_large

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup_no_site | 6.38 ms                                                         | 6.45 ms: 1.01x slower                                           |
| python_startup         | 9.73 ms                                                         | 9.90 ms: 1.02x slower                                           |
| Geometric mean         | (ref)                                                           | 1.01x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| django_template | 27.8 ms                                                         | 28.2 ms: 1.01x slower                                           |
| mako            | 7.40 ms                                                         | 7.57 ms: 1.02x slower                                           |
| genshi_xml      | 39.5 ms                                                         | 40.4 ms: 1.02x slower                                           |
| genshi_text     | 16.8 ms                                                         | 17.3 ms: 1.03x slower                                           |
| Geometric mean  | (ref)                                                           | 1.02x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_mandelbrot_optimized | 233 ms                                                          | 235 ms: 1.01x slower                                            |
| thread_mandelbrot_naive     | 233 ms                                                          | 237 ms: 1.01x slower                                            |
| thread_memo_naive           | 11.5 ms                                                         | 11.7 ms: 1.02x slower                                           |
| thread_pipeline_naive       | 32.0 ms                                                         | 32.8 ms: 1.03x slower                                           |
| thread_counter_naive        | 20.2 ms                                                         | 20.9 ms: 1.03x slower                                           |
| thread_memo_optimized       | 15.9 ms                                                         | 16.5 ms: 1.04x slower                                           |
| thread_pipeline_optimized   | 22.5 ms                                                         | 23.4 ms: 1.04x slower                                           |
| thread_accumulate_naive     | 35.8 ms                                                         | 37.2 ms: 1.04x slower                                           |
| thread_counter_optimized    | 17.1 ms                                                         | 17.8 ms: 1.04x slower                                           |
| thread_accumulate_optimized | 35.1 ms                                                         | 37.1 ms: 1.06x slower                                           |
| thread_montecarlo_optimized | 13.9 ms                                                         | 15.3 ms: 1.10x slower                                           |
| thread_montecarlo_naive     | 15.8 ms                                                         | 17.5 ms: 1.11x slower                                           |
| Geometric mean              | (ref)                                                           | 1.04x slower                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| argparse_many_optionals          | 34.4 ms                                                         | 7.69 ms: 4.48x faster                                           |
| argparse_subparsers              | 686 us                                                          | 501 us: 1.37x faster                                            |
| pickle_list                      | 3.24 us                                                         | 2.86 us: 1.13x faster                                           |
| base64_large                     | 3.63 ms                                                         | 3.32 ms: 1.09x faster                                           |
| base64_small                     | 186 us                                                          | 175 us: 1.06x faster                                            |
| create_gc_cycles                 | 1.96 ms                                                         | 1.87 ms: 1.05x faster                                           |
| telco                            | 5.59 ms                                                         | 5.40 ms: 1.04x faster                                           |
| docutils                         | 1.95 sec                                                        | 1.88 sec: 1.04x faster                                          |
| asyncio_tcp                      | 325 ms                                                          | 314 ms: 1.03x faster                                            |
| mypy2                            | 753 ms                                                          | 730 ms: 1.03x faster                                            |
| coverage                         | 57.4 ms                                                         | 56.1 ms: 1.02x faster                                           |
| logging_format                   | 5.35 us                                                         | 5.24 us: 1.02x faster                                           |
| pickle_dict                      | 21.5 us                                                         | 21.2 us: 1.02x faster                                           |
| unpack_sequence                  | 25.8 ns                                                         | 25.4 ns: 1.01x faster                                           |
| logging_simple                   | 4.79 us                                                         | 4.73 us: 1.01x faster                                           |
| nqueens                          | 56.8 ms                                                         | 56.2 ms: 1.01x faster                                           |
| richards_super                   | 37.4 ms                                                         | 37.1 ms: 1.01x faster                                           |
| pidigits                         | 189 ms                                                          | 188 ms: 1.01x faster                                            |
| richards                         | 32.6 ms                                                         | 32.4 ms: 1.01x faster                                           |
| urlsafe_base64_small             | 329 us                                                          | 327 us: 1.01x faster                                            |
| deepcopy                         | 193 us                                                          | 193 us: 1.00x slower                                            |
| deepcopy_reduce                  | 2.00 us                                                         | 2.01 us: 1.00x slower                                           |
| gc_traversal                     | 3.26 ms                                                         | 3.27 ms: 1.00x slower                                           |
| base16_small                     | 305 us                                                          | 307 us: 1.01x slower                                            |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.16 ms: 1.01x slower                                           |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.29 sec: 1.01x slower                                          |
| decimal_factorial                | 173 ms                                                          | 174 ms: 1.01x slower                                            |
| thread_mandelbrot_optimized      | 233 ms                                                          | 235 ms: 1.01x slower                                            |
| pathlib                          | 13.0 ms                                                         | 13.1 ms: 1.01x slower                                           |
| asyncio_websockets               | 296 ms                                                          | 299 ms: 1.01x slower                                            |
| pickle                           | 8.20 us                                                         | 8.29 us: 1.01x slower                                           |
| sqlalchemy_imperative            | 14.2 ms                                                         | 14.3 ms: 1.01x slower                                           |
| sqlglot_v2_parse                 | 911 us                                                          | 921 us: 1.01x slower                                            |
| python_startup_no_site           | 6.38 ms                                                         | 6.45 ms: 1.01x slower                                           |
| typing_runtime_protocols         | 112 us                                                          | 113 us: 1.01x slower                                            |
| go                               | 84.7 ms                                                         | 85.8 ms: 1.01x slower                                           |
| xml_etree_generate               | 62.6 ms                                                         | 63.4 ms: 1.01x slower                                           |
| fastapi_http                     | 216 ms                                                          | 219 ms: 1.01x slower                                            |
| meteor_contest                   | 84.1 ms                                                         | 85.3 ms: 1.01x slower                                           |
| django_template                  | 27.8 ms                                                         | 28.2 ms: 1.01x slower                                           |
| thread_mandelbrot_naive          | 233 ms                                                          | 237 ms: 1.01x slower                                            |
| deepcopy_memo                    | 18.0 us                                                         | 18.3 us: 1.01x slower                                           |
| regex_dna                        | 150 ms                                                          | 152 ms: 1.01x slower                                            |
| regex_compile                    | 93.9 ms                                                         | 95.4 ms: 1.02x slower                                           |
| thread_memo_naive                | 11.5 ms                                                         | 11.7 ms: 1.02x slower                                           |
| mdp                              | 946 ms                                                          | 961 ms: 1.02x slower                                            |
| python_startup                   | 9.73 ms                                                         | 9.90 ms: 1.02x slower                                           |
| xml_etree_iterparse              | 76.2 ms                                                         | 77.5 ms: 1.02x slower                                           |
| raytrace                         | 194 ms                                                          | 197 ms: 1.02x slower                                            |
| crypto_pyaes                     | 54.5 ms                                                         | 55.5 ms: 1.02x slower                                           |
| chaos                            | 43.8 ms                                                         | 44.6 ms: 1.02x slower                                           |
| sympy_expand                     | 332 ms                                                          | 338 ms: 1.02x slower                                            |
| sympy_integrate                  | 15.4 ms                                                         | 15.7 ms: 1.02x slower                                           |
| regex_effbot                     | 1.95 ms                                                         | 1.99 ms: 1.02x slower                                           |
| sympy_sum                        | 106 ms                                                          | 108 ms: 1.02x slower                                            |
| fannkuch                         | 245 ms                                                          | 250 ms: 1.02x slower                                            |
| deltablue                        | 2.34 ms                                                         | 2.39 ms: 1.02x slower                                           |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 39.9 ms: 1.02x slower                                           |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 80.0 ms: 1.02x slower                                           |
| unpickle_pure_python             | 152 us                                                          | 155 us: 1.02x slower                                            |
| sympy_str                        | 194 ms                                                          | 198 ms: 1.02x slower                                            |
| mako                             | 7.40 ms                                                         | 7.57 ms: 1.02x slower                                           |
| async_tree_eager                 | 81.3 ms                                                         | 83.2 ms: 1.02x slower                                           |
| json_dumps                       | 6.95 ms                                                         | 7.11 ms: 1.02x slower                                           |
| genshi_xml                       | 39.5 ms                                                         | 40.4 ms: 1.02x slower                                           |
| hexiom                           | 4.11 ms                                                         | 4.21 ms: 1.02x slower                                           |
| xml_etree_process                | 44.7 ms                                                         | 45.8 ms: 1.02x slower                                           |
| thread_pipeline_naive            | 32.0 ms                                                         | 32.8 ms: 1.03x slower                                           |
| comprehensions                   | 10.8 us                                                         | 11.1 us: 1.03x slower                                           |
| quadtree_nbody                   | 596 ms                                                          | 612 ms: 1.03x slower                                            |
| base85_large                     | 248 ms                                                          | 255 ms: 1.03x slower                                            |
| base85_small                     | 4.69 ms                                                         | 4.83 ms: 1.03x slower                                           |
| genshi_text                      | 16.8 ms                                                         | 17.3 ms: 1.03x slower                                           |
| decimal_pi                       | 208 ms                                                          | 214 ms: 1.03x slower                                            |
| coroutines                       | 15.1 ms                                                         | 15.6 ms: 1.03x slower                                           |
| thrift                           | 1.86 ms                                                         | 1.92 ms: 1.03x slower                                           |
| spectral_norm                    | 65.6 ms                                                         | 67.7 ms: 1.03x slower                                           |
| thread_counter_naive             | 20.2 ms                                                         | 20.9 ms: 1.03x slower                                           |
| pyflate                          | 299 ms                                                          | 309 ms: 1.03x slower                                            |
| async_generators                 | 228 ms                                                          | 235 ms: 1.03x slower                                            |
| unpickle_list                    | 3.43 us                                                         | 3.54 us: 1.03x slower                                           |
| unpickle                         | 10.2 us                                                         | 10.5 us: 1.03x slower                                           |
| nbody                            | 67.9 ms                                                         | 70.3 ms: 1.04x slower                                           |
| pprint_safe_repr                 | 474 ms                                                          | 491 ms: 1.04x slower                                            |
| thread_memo_optimized            | 15.9 ms                                                         | 16.5 ms: 1.04x slower                                           |
| pprint_pformat                   | 989 ms                                                          | 1.03 sec: 1.04x slower                                          |
| pylint                           | 216 ms                                                          | 224 ms: 1.04x slower                                            |
| scimark_lu                       | 73.8 ms                                                         | 76.8 ms: 1.04x slower                                           |
| thread_pipeline_optimized        | 22.5 ms                                                         | 23.4 ms: 1.04x slower                                           |
| thread_accumulate_naive          | 35.8 ms                                                         | 37.2 ms: 1.04x slower                                           |
| ascii85_large                    | 667 ms                                                          | 695 ms: 1.04x slower                                            |
| thread_counter_optimized         | 17.1 ms                                                         | 17.8 ms: 1.04x slower                                           |
| scimark_monte_carlo              | 40.7 ms                                                         | 42.4 ms: 1.04x slower                                           |
| base32_large                     | 292 ms                                                          | 306 ms: 1.05x slower                                            |
| scimark_fft                      | 226 ms                                                          | 237 ms: 1.05x slower                                            |
| ascii85_small                    | 12.7 ms                                                         | 13.3 ms: 1.05x slower                                           |
| chameleon                        | 9.52 ms                                                         | 10.00 ms: 1.05x slower                                          |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.15 sec: 1.05x slower                                          |
| base32_small                     | 5.71 ms                                                         | 6.00 ms: 1.05x slower                                           |
| async_tree_eager_memoization     | 180 ms                                                          | 189 ms: 1.05x slower                                            |
| noop                             | 19.4 ns                                                         | 20.4 ns: 1.05x slower                                           |
| pycparser                        | 851 ms                                                          | 897 ms: 1.05x slower                                            |
| html5lib                         | 46.9 ms                                                         | 49.6 ms: 1.06x slower                                           |
| thread_accumulate_optimized      | 35.1 ms                                                         | 37.1 ms: 1.06x slower                                           |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.37 ms: 1.06x slower                                           |
| tomli_loads                      | 1.44 sec                                                        | 1.53 sec: 1.06x slower                                          |
| logging_silent                   | 65.3 ns                                                         | 69.5 ns: 1.06x slower                                           |
| float                            | 47.3 ms                                                         | 50.7 ms: 1.07x slower                                           |
| json                             | 3.42 ms                                                         | 3.69 ms: 1.08x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 394 ms: 1.09x slower                                            |
| xdsl_constant_fold               | 34.7 ms                                                         | 37.8 ms: 1.09x slower                                           |
| regex_v8                         | 14.8 ms                                                         | 16.2 ms: 1.09x slower                                           |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 15.3 ms: 1.10x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 451 ms: 1.11x slower                                            |
| thread_montecarlo_naive          | 15.8 ms                                                         | 17.5 ms: 1.11x slower                                           |
| json_loads                       | 17.5 us                                                         | 19.5 us: 1.11x slower                                           |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 468 ms: 1.14x slower                                            |
| async_tree_eager_tg              | 182 ms                                                          | 212 ms: 1.16x slower                                            |
| xml_etree_parse                  | 94.3 ms                                                         | 110 ms: 1.17x slower                                            |
| async_tree_none                  | 228 ms                                                          | 266 ms: 1.17x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 650 ms: 1.18x slower                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 286 ms: 1.21x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 338 ms: 1.22x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 273 ms: 1.22x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 345 ms: 1.23x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 682 ms: 1.24x slower                                            |
| async_tree_io                    | 531 ms                                                          | 668 ms: 1.26x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 701 ms: 1.30x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (9): scimark_sor, networkx_connected_components, pickle_pure_python, networkx_k_core, base16_large, async_tree_eager_cpu_io_mixed, networkx_shortest_path, tornado_http, generators

- Geometric mean (including insignificant results): 1.021x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.01x
- 95% likely to have a slowdown of 1.01x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 0.99x