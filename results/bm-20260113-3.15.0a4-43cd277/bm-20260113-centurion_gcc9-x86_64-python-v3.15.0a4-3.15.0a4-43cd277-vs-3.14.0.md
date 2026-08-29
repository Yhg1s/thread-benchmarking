# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.015x faster
- HPT reliability: 78.48%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.02x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.1 ms: 1.06x slower                                               |
| docutils       | 1.95 sec                                                        | 1.96 sec: 1.01x slower                                              |
| fastapi_http   | 216 ms                                                          | 217 ms: 1.01x slower                                                |
| html5lib       | 46.9 ms                                                         | 44.7 ms: 1.05x faster                                               |
| tornado_http   | 101 ms                                                          | 101 ms: 1.01x faster                                                |
| Geometric mean | (ref)                                                           | 1.00x slower                                                        |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| asyncio_tcp                      | 325 ms                                                          | 265 ms: 1.22x faster                                                |
| async_tree_eager_io_tg           | 550 ms                                                          | 467 ms: 1.18x faster                                                |
| async_tree_eager_io              | 552 ms                                                          | 484 ms: 1.14x faster                                                |
| async_tree_none_tg               | 223 ms                                                          | 202 ms: 1.11x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 490 ms: 1.10x faster                                                |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 381 ms: 1.08x faster                                                |
| async_tree_io                    | 531 ms                                                          | 497 ms: 1.07x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 344 ms: 1.06x faster                                                |
| async_tree_memoization_tg        | 277 ms                                                          | 264 ms: 1.05x faster                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 388 ms: 1.05x faster                                                |
| async_tree_eager_memoization     | 180 ms                                                          | 173 ms: 1.04x faster                                                |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 302 ms: 1.04x faster                                                |
| async_tree_none                  | 228 ms                                                          | 220 ms: 1.04x faster                                                |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 228 ms: 1.04x faster                                                |
| async_tree_memoization           | 281 ms                                                          | 274 ms: 1.02x faster                                                |
| async_generators                 | 228 ms                                                          | 223 ms: 1.02x faster                                                |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.26 sec: 1.02x faster                                              |
| async_tree_eager_tg              | 182 ms                                                          | 179 ms: 1.02x faster                                                |
| async_tree_eager                 | 81.3 ms                                                         | 80.9 ms: 1.00x faster                                               |
| coroutines                       | 15.1 ms                                                         | 15.3 ms: 1.01x slower                                               |
| asyncio_websockets               | 296 ms                                                          | 312 ms: 1.05x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.06x faster                                                        |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 21.3 ns: 1.10x slower                                               |

Benchmarks with tag 'decimal':
==============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| decimal_pi     | 208 ms                                                          | 210 ms: 1.01x slower                                                |
| Geometric mean | (ref)                                                           | 1.00x slower                                                        |

Benchmark hidden because not significant (1): decimal_factorial

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| quadtree_nbody | 596 ms                                                          | 587 ms: 1.02x faster                                                |
| nbody          | 67.9 ms                                                         | 67.0 ms: 1.01x faster                                               |
| pidigits       | 189 ms                                                          | 188 ms: 1.01x faster                                                |
| float          | 47.3 ms                                                         | 49.1 ms: 1.04x slower                                               |
| Geometric mean | (ref)                                                           | 1.00x slower                                                        |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| regex_compile  | 93.9 ms                                                         | 94.2 ms: 1.00x slower                                               |
| regex_effbot   | 1.95 ms                                                         | 2.01 ms: 1.03x slower                                               |
| regex_dna      | 150 ms                                                          | 157 ms: 1.04x slower                                                |
| Geometric mean | (ref)                                                           | 1.02x slower                                                        |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| xml_etree_iterparse  | 76.2 ms                                                         | 69.6 ms: 1.09x faster                                               |
| base16_large         | 5.33 ms                                                         | 4.91 ms: 1.09x faster                                               |
| json_dumps           | 6.95 ms                                                         | 6.41 ms: 1.08x faster                                               |
| base64_large         | 3.63 ms                                                         | 3.45 ms: 1.05x faster                                               |
| base64_small         | 186 us                                                          | 178 us: 1.04x faster                                                |
| json_loads           | 17.5 us                                                         | 16.8 us: 1.04x faster                                               |
| pickle_dict          | 21.5 us                                                         | 21.2 us: 1.01x faster                                               |
| base16_small         | 305 us                                                          | 302 us: 1.01x faster                                                |
| xml_etree_parse      | 94.3 ms                                                         | 93.5 ms: 1.01x faster                                               |
| xml_etree_generate   | 62.6 ms                                                         | 62.3 ms: 1.00x faster                                               |
| unpickle_pure_python | 152 us                                                          | 153 us: 1.00x slower                                                |
| ascii85_large        | 667 ms                                                          | 671 ms: 1.00x slower                                                |
| pickle_pure_python   | 240 us                                                          | 242 us: 1.01x slower                                                |
| base85_small         | 4.69 ms                                                         | 4.74 ms: 1.01x slower                                               |
| ascii85_small        | 12.7 ms                                                         | 12.8 ms: 1.01x slower                                               |
| unpickle_list        | 3.43 us                                                         | 3.49 us: 1.02x slower                                               |
| xml_etree_process    | 44.7 ms                                                         | 45.7 ms: 1.02x slower                                               |
| pickle               | 8.20 us                                                         | 8.38 us: 1.02x slower                                               |
| base85_large         | 248 ms                                                          | 254 ms: 1.03x slower                                                |
| pickle_list          | 3.24 us                                                         | 3.33 us: 1.03x slower                                               |
| base32_large         | 292 ms                                                          | 303 ms: 1.04x slower                                                |
| unpickle             | 10.2 us                                                         | 10.6 us: 1.04x slower                                               |
| base32_small         | 5.71 ms                                                         | 5.96 ms: 1.04x slower                                               |
| tomli_loads          | 1.44 sec                                                        | 1.68 sec: 1.16x slower                                              |
| Geometric mean       | (ref)                                                           | 1.00x faster                                                        |

Benchmark hidden because not significant (1): urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 9.39 ms: 1.04x faster                                               |
| python_startup_no_site | 6.38 ms                                                         | 6.19 ms: 1.03x faster                                               |
| Geometric mean         | (ref)                                                           | 1.03x faster                                                        |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| genshi_text     | 16.8 ms                                                         | 17.1 ms: 1.02x slower                                               |
| genshi_xml      | 39.5 ms                                                         | 41.0 ms: 1.04x slower                                               |
| mako            | 7.40 ms                                                         | 7.70 ms: 1.04x slower                                               |
| django_template | 27.8 ms                                                         | 29.8 ms: 1.07x slower                                               |
| Geometric mean  | (ref)                                                           | 1.04x slower                                                        |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| thread_memo_naive           | 11.5 ms                                                         | 10.5 ms: 1.09x faster                                               |
| thread_mandelbrot_naive     | 233 ms                                                          | 221 ms: 1.05x faster                                                |
| thread_mandelbrot_optimized | 233 ms                                                          | 228 ms: 1.02x faster                                                |
| thread_montecarlo_optimized | 13.9 ms                                                         | 14.2 ms: 1.02x slower                                               |
| thread_pipeline_naive       | 32.0 ms                                                         | 33.7 ms: 1.05x slower                                               |
| thread_montecarlo_naive     | 15.8 ms                                                         | 16.8 ms: 1.06x slower                                               |
| thread_accumulate_naive     | 35.8 ms                                                         | 39.2 ms: 1.09x slower                                               |
| thread_counter_naive        | 20.2 ms                                                         | 22.1 ms: 1.09x slower                                               |
| thread_memo_optimized       | 15.9 ms                                                         | 17.7 ms: 1.11x slower                                               |
| thread_accumulate_optimized | 35.1 ms                                                         | 39.1 ms: 1.11x slower                                               |
| thread_pipeline_optimized   | 22.5 ms                                                         | 25.5 ms: 1.13x slower                                               |
| thread_counter_optimized    | 17.1 ms                                                         | 20.0 ms: 1.17x slower                                               |
| Geometric mean              | (ref)                                                           | 1.05x slower                                                        |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_gcc9-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:---------------------------------------------------------------:|:-------------------------------------------------------------------:|
| argparse_many_optionals          | 34.4 ms                                                         | 7.59 ms: 4.53x faster                                               |
| argparse_subparsers              | 686 us                                                          | 486 us: 1.41x faster                                                |
| asyncio_tcp                      | 325 ms                                                          | 265 ms: 1.22x faster                                                |
| async_tree_eager_io_tg           | 550 ms                                                          | 467 ms: 1.18x faster                                                |
| async_tree_eager_io              | 552 ms                                                          | 484 ms: 1.14x faster                                                |
| pathlib                          | 13.0 ms                                                         | 11.6 ms: 1.12x faster                                               |
| async_tree_none_tg               | 223 ms                                                          | 202 ms: 1.11x faster                                                |
| async_tree_io_tg                 | 539 ms                                                          | 490 ms: 1.10x faster                                                |
| telco                            | 5.59 ms                                                         | 5.11 ms: 1.10x faster                                               |
| thread_memo_naive                | 11.5 ms                                                         | 10.5 ms: 1.09x faster                                               |
| xml_etree_iterparse              | 76.2 ms                                                         | 69.6 ms: 1.09x faster                                               |
| base16_large                     | 5.33 ms                                                         | 4.91 ms: 1.09x faster                                               |
| networkx_k_core                  | 2.07 sec                                                        | 1.91 sec: 1.08x faster                                              |
| json_dumps                       | 6.95 ms                                                         | 6.41 ms: 1.08x faster                                               |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 381 ms: 1.08x faster                                                |
| async_tree_io                    | 531 ms                                                          | 497 ms: 1.07x faster                                                |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 344 ms: 1.06x faster                                                |
| scimark_fft                      | 226 ms                                                          | 214 ms: 1.06x faster                                                |
| logging_silent                   | 65.3 ns                                                         | 61.8 ns: 1.06x faster                                               |
| thread_mandelbrot_naive          | 233 ms                                                          | 221 ms: 1.05x faster                                                |
| base64_large                     | 3.63 ms                                                         | 3.45 ms: 1.05x faster                                               |
| richards                         | 32.6 ms                                                         | 31.0 ms: 1.05x faster                                               |
| async_tree_memoization_tg        | 277 ms                                                          | 264 ms: 1.05x faster                                                |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 388 ms: 1.05x faster                                                |
| html5lib                         | 46.9 ms                                                         | 44.7 ms: 1.05x faster                                               |
| chaos                            | 43.8 ms                                                         | 41.9 ms: 1.04x faster                                               |
| base64_small                     | 186 us                                                          | 178 us: 1.04x faster                                                |
| json_loads                       | 17.5 us                                                         | 16.8 us: 1.04x faster                                               |
| async_tree_eager_memoization     | 180 ms                                                          | 173 ms: 1.04x faster                                                |
| scimark_sor                      | 75.7 ms                                                         | 72.9 ms: 1.04x faster                                               |
| deepcopy_memo                    | 18.0 us                                                         | 17.3 us: 1.04x faster                                               |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 302 ms: 1.04x faster                                                |
| async_tree_none                  | 228 ms                                                          | 220 ms: 1.04x faster                                                |
| python_startup                   | 9.73 ms                                                         | 9.39 ms: 1.04x faster                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 228 ms: 1.04x faster                                                |
| deepcopy                         | 193 us                                                          | 186 us: 1.03x faster                                                |
| richards_super                   | 37.4 ms                                                         | 36.2 ms: 1.03x faster                                               |
| python_startup_no_site           | 6.38 ms                                                         | 6.19 ms: 1.03x faster                                               |
| unpack_sequence                  | 25.8 ns                                                         | 25.1 ns: 1.02x faster                                               |
| logging_simple                   | 4.79 us                                                         | 4.67 us: 1.02x faster                                               |
| async_tree_memoization           | 281 ms                                                          | 274 ms: 1.02x faster                                                |
| thread_mandelbrot_optimized      | 233 ms                                                          | 228 ms: 1.02x faster                                                |
| async_generators                 | 228 ms                                                          | 223 ms: 1.02x faster                                                |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.26 sec: 1.02x faster                                              |
| async_tree_eager_tg              | 182 ms                                                          | 179 ms: 1.02x faster                                                |
| fannkuch                         | 245 ms                                                          | 241 ms: 1.02x faster                                                |
| gc_traversal                     | 3.26 ms                                                         | 3.20 ms: 1.02x faster                                               |
| quadtree_nbody                   | 596 ms                                                          | 587 ms: 1.02x faster                                                |
| pickle_dict                      | 21.5 us                                                         | 21.2 us: 1.01x faster                                               |
| xdsl_constant_fold               | 34.7 ms                                                         | 34.2 ms: 1.01x faster                                               |
| spectral_norm                    | 65.6 ms                                                         | 64.6 ms: 1.01x faster                                               |
| json                             | 3.42 ms                                                         | 3.38 ms: 1.01x faster                                               |
| nbody                            | 67.9 ms                                                         | 67.0 ms: 1.01x faster                                               |
| pycparser                        | 851 ms                                                          | 841 ms: 1.01x faster                                                |
| base16_small                     | 305 us                                                          | 302 us: 1.01x faster                                                |
| logging_format                   | 5.35 us                                                         | 5.29 us: 1.01x faster                                               |
| hexiom                           | 4.11 ms                                                         | 4.08 ms: 1.01x faster                                               |
| crypto_pyaes                     | 54.5 ms                                                         | 54.0 ms: 1.01x faster                                               |
| xml_etree_parse                  | 94.3 ms                                                         | 93.5 ms: 1.01x faster                                               |
| tornado_http                     | 101 ms                                                          | 101 ms: 1.01x faster                                                |
| pidigits                         | 189 ms                                                          | 188 ms: 1.01x faster                                                |
| async_tree_eager                 | 81.3 ms                                                         | 80.9 ms: 1.00x faster                                               |
| xml_etree_generate               | 62.6 ms                                                         | 62.3 ms: 1.00x faster                                               |
| regex_compile                    | 93.9 ms                                                         | 94.2 ms: 1.00x slower                                               |
| unpickle_pure_python             | 152 us                                                          | 153 us: 1.00x slower                                                |
| ascii85_large                    | 667 ms                                                          | 671 ms: 1.00x slower                                                |
| fastapi_http                     | 216 ms                                                          | 217 ms: 1.01x slower                                                |
| docutils                         | 1.95 sec                                                        | 1.96 sec: 1.01x slower                                              |
| pickle_pure_python               | 240 us                                                          | 242 us: 1.01x slower                                                |
| decimal_pi                       | 208 ms                                                          | 210 ms: 1.01x slower                                                |
| go                               | 84.7 ms                                                         | 85.5 ms: 1.01x slower                                               |
| base85_small                     | 4.69 ms                                                         | 4.74 ms: 1.01x slower                                               |
| ascii85_small                    | 12.7 ms                                                         | 12.8 ms: 1.01x slower                                               |
| sqlglot_v2_parse                 | 911 us                                                          | 922 us: 1.01x slower                                                |
| comprehensions                   | 10.8 us                                                         | 10.9 us: 1.01x slower                                               |
| coroutines                       | 15.1 ms                                                         | 15.3 ms: 1.01x slower                                               |
| sympy_integrate                  | 15.4 ms                                                         | 15.6 ms: 1.02x slower                                               |
| networkx_shortest_path           | 444 ms                                                          | 451 ms: 1.02x slower                                                |
| typing_runtime_protocols         | 112 us                                                          | 114 us: 1.02x slower                                                |
| genshi_text                      | 16.8 ms                                                         | 17.1 ms: 1.02x slower                                               |
| unpickle_list                    | 3.43 us                                                         | 3.49 us: 1.02x slower                                               |
| mdp                              | 946 ms                                                          | 964 ms: 1.02x slower                                                |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 14.2 ms: 1.02x slower                                               |
| xml_etree_process                | 44.7 ms                                                         | 45.7 ms: 1.02x slower                                               |
| pickle                           | 8.20 us                                                         | 8.38 us: 1.02x slower                                               |
| sympy_sum                        | 106 ms                                                          | 109 ms: 1.02x slower                                                |
| scimark_lu                       | 73.8 ms                                                         | 75.6 ms: 1.02x slower                                               |
| thrift                           | 1.86 ms                                                         | 1.91 ms: 1.02x slower                                               |
| sympy_expand                     | 332 ms                                                          | 340 ms: 1.03x slower                                                |
| pprint_pformat                   | 989 ms                                                          | 1.01 sec: 1.03x slower                                              |
| base85_large                     | 248 ms                                                          | 254 ms: 1.03x slower                                                |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 40.1 ms: 1.03x slower                                               |
| scimark_monte_carlo              | 40.7 ms                                                         | 41.9 ms: 1.03x slower                                               |
| pickle_list                      | 3.24 us                                                         | 3.33 us: 1.03x slower                                               |
| sympy_str                        | 194 ms                                                          | 200 ms: 1.03x slower                                                |
| regex_effbot                     | 1.95 ms                                                         | 2.01 ms: 1.03x slower                                               |
| base32_large                     | 292 ms                                                          | 303 ms: 1.04x slower                                                |
| float                            | 47.3 ms                                                         | 49.1 ms: 1.04x slower                                               |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 81.2 ms: 1.04x slower                                               |
| meteor_contest                   | 84.1 ms                                                         | 87.3 ms: 1.04x slower                                               |
| genshi_xml                       | 39.5 ms                                                         | 41.0 ms: 1.04x slower                                               |
| mako                             | 7.40 ms                                                         | 7.70 ms: 1.04x slower                                               |
| nqueens                          | 56.8 ms                                                         | 59.2 ms: 1.04x slower                                               |
| regex_dna                        | 150 ms                                                          | 157 ms: 1.04x slower                                                |
| unpickle                         | 10.2 us                                                         | 10.6 us: 1.04x slower                                               |
| base32_small                     | 5.71 ms                                                         | 5.96 ms: 1.04x slower                                               |
| thread_pipeline_naive            | 32.0 ms                                                         | 33.7 ms: 1.05x slower                                               |
| pyflate                          | 299 ms                                                          | 315 ms: 1.05x slower                                                |
| asyncio_websockets               | 296 ms                                                          | 312 ms: 1.05x slower                                                |
| chameleon                        | 9.52 ms                                                         | 10.1 ms: 1.06x slower                                               |
| deltablue                        | 2.34 ms                                                         | 2.47 ms: 1.06x slower                                               |
| thread_montecarlo_naive          | 15.8 ms                                                         | 16.8 ms: 1.06x slower                                               |
| generators                       | 20.3 ms                                                         | 21.6 ms: 1.06x slower                                               |
| pprint_safe_repr                 | 474 ms                                                          | 507 ms: 1.07x slower                                                |
| django_template                  | 27.8 ms                                                         | 29.8 ms: 1.07x slower                                               |
| thread_accumulate_naive          | 35.8 ms                                                         | 39.2 ms: 1.09x slower                                               |
| thread_counter_naive             | 20.2 ms                                                         | 22.1 ms: 1.09x slower                                               |
| noop                             | 19.4 ns                                                         | 21.3 ns: 1.10x slower                                               |
| thread_memo_optimized            | 15.9 ms                                                         | 17.7 ms: 1.11x slower                                               |
| thread_accumulate_optimized      | 35.1 ms                                                         | 39.1 ms: 1.11x slower                                               |
| thread_pipeline_optimized        | 22.5 ms                                                         | 25.5 ms: 1.13x slower                                               |
| tomli_loads                      | 1.44 sec                                                        | 1.68 sec: 1.16x slower                                              |
| thread_counter_optimized         | 17.1 ms                                                         | 20.0 ms: 1.17x slower                                               |
| networkx_connected_components    | 438 ms                                                          | 542 ms: 1.24x slower                                                |
| Geometric mean                   | (ref)                                                           | 1.01x faster                                                        |

Benchmark hidden because not significant (12): pylint, urlsafe_base64_small, sqlglot_v2_transpile, mypy2, deepcopy_reduce, decimal_factorial, bpe_tokeniser, create_gc_cycles, scimark_sparse_mat_mult, coverage, regex_v8, raytrace
Ignored benchmarks (1) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.015x faster

# HPT report

- Reliability score: 78.48% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.02x