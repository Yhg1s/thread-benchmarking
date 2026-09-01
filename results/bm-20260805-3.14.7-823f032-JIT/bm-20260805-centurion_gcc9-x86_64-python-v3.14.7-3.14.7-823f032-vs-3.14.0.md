# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.019x slower
- HPT reliability: 99.61%
- HPT 99th percentile: 1.00x slower
- Memory change: 1.02x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.1 ms: 1.07x slower                                           |
| fastapi_http   | 216 ms                                                          | 212 ms: 1.02x faster                                            |
| html5lib       | 46.9 ms                                                         | 48.7 ms: 1.04x slower                                           |
| tornado_http   | 101 ms                                                          | 104 ms: 1.03x slower                                            |
| Geometric mean | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (1): docutils

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| asyncio_tcp                      | 325 ms                                                          | 297 ms: 1.09x faster                                            |
| asyncio_websockets               | 296 ms                                                          | 298 ms: 1.01x slower                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.29 sec: 1.01x slower                                          |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 320 ms: 1.02x slower                                            |
| async_tree_eager                 | 81.3 ms                                                         | 85.9 ms: 1.06x slower                                           |
| coroutines                       | 15.1 ms                                                         | 16.4 ms: 1.08x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 397 ms: 1.09x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 197 ms: 1.09x slower                                            |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 450 ms: 1.10x slower                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 457 ms: 1.11x slower                                            |
| async_generators                 | 228 ms                                                          | 257 ms: 1.13x slower                                            |
| async_tree_eager_tg              | 182 ms                                                          | 207 ms: 1.13x slower                                            |
| async_tree_none                  | 228 ms                                                          | 266 ms: 1.17x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 651 ms: 1.18x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 333 ms: 1.19x slower                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 282 ms: 1.19x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 268 ms: 1.20x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 667 ms: 1.21x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 343 ms: 1.24x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 694 ms: 1.29x slower                                            |
| async_tree_io                    | 531 ms                                                          | 686 ms: 1.29x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.12x slower                                                    |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 16.8 ns: 1.15x faster                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_pi        | 208 ms                                                          | 204 ms: 1.02x faster                                            |
| decimal_factorial | 173 ms                                                          | 175 ms: 1.01x slower                                            |
| Geometric mean    | (ref)                                                           | 1.00x faster                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| float          | 47.3 ms                                                         | 42.1 ms: 1.12x faster                                           |
| pidigits       | 189 ms                                                          | 187 ms: 1.01x faster                                            |
| quadtree_nbody | 596 ms                                                          | 592 ms: 1.01x faster                                            |
| nbody          | 67.9 ms                                                         | 70.1 ms: 1.03x slower                                           |
| Geometric mean | (ref)                                                           | 1.03x faster                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_compile  | 93.9 ms                                                         | 95.2 ms: 1.01x slower                                           |
| regex_dna      | 150 ms                                                          | 153 ms: 1.02x slower                                            |
| regex_effbot   | 1.95 ms                                                         | 2.09 ms: 1.07x slower                                           |
| Geometric mean | (ref)                                                           | 1.03x slower                                                    |

Benchmark hidden because not significant (1): regex_v8

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pickle_list          | 3.24 us                                                         | 2.79 us: 1.16x faster                                           |
| unpickle_pure_python | 152 us                                                          | 134 us: 1.14x faster                                            |
| base64_large         | 3.63 ms                                                         | 3.31 ms: 1.10x faster                                           |
| ascii85_large        | 667 ms                                                          | 613 ms: 1.09x faster                                            |
| xml_etree_generate   | 62.6 ms                                                         | 58.5 ms: 1.07x faster                                           |
| xml_etree_process    | 44.7 ms                                                         | 42.9 ms: 1.04x faster                                           |
| ascii85_small        | 12.7 ms                                                         | 12.2 ms: 1.04x faster                                           |
| base64_small         | 186 us                                                          | 179 us: 1.04x faster                                            |
| base85_small         | 4.69 ms                                                         | 4.51 ms: 1.04x faster                                           |
| base85_large         | 248 ms                                                          | 242 ms: 1.02x faster                                            |
| base16_large         | 5.33 ms                                                         | 5.25 ms: 1.02x faster                                           |
| tomli_loads          | 1.44 sec                                                        | 1.42 sec: 1.01x faster                                          |
| urlsafe_base64_small | 329 us                                                          | 325 us: 1.01x faster                                            |
| pickle_dict          | 21.5 us                                                         | 21.5 us: 1.00x faster                                           |
| base16_small         | 305 us                                                          | 310 us: 1.01x slower                                            |
| xml_etree_iterparse  | 76.2 ms                                                         | 77.6 ms: 1.02x slower                                           |
| base32_large         | 292 ms                                                          | 298 ms: 1.02x slower                                            |
| pickle               | 8.20 us                                                         | 8.38 us: 1.02x slower                                           |
| unpickle_list        | 3.43 us                                                         | 3.51 us: 1.02x slower                                           |
| pickle_pure_python   | 240 us                                                          | 247 us: 1.03x slower                                            |
| base32_small         | 5.71 ms                                                         | 5.90 ms: 1.03x slower                                           |
| json_dumps           | 6.95 ms                                                         | 7.28 ms: 1.05x slower                                           |
| unpickle             | 10.2 us                                                         | 10.7 us: 1.05x slower                                           |
| json_loads           | 17.5 us                                                         | 19.6 us: 1.12x slower                                           |
| xml_etree_parse      | 94.3 ms                                                         | 112 ms: 1.19x slower                                            |
| Geometric mean       | (ref)                                                           | 1.01x faster                                                    |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup_no_site | 6.38 ms                                                         | 6.49 ms: 1.02x slower                                           |
| python_startup         | 9.73 ms                                                         | 9.96 ms: 1.02x slower                                           |
| Geometric mean         | (ref)                                                           | 1.02x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| mako            | 7.40 ms                                                         | 6.48 ms: 1.14x faster                                           |
| django_template | 27.8 ms                                                         | 28.5 ms: 1.02x slower                                           |
| genshi_text     | 16.8 ms                                                         | 17.3 ms: 1.03x slower                                           |
| genshi_xml      | 39.5 ms                                                         | 41.7 ms: 1.06x slower                                           |
| Geometric mean  | (ref)                                                           | 1.01x faster                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                          | 211 ms: 1.11x faster                                            |
| thread_mandelbrot_optimized | 233 ms                                                          | 212 ms: 1.10x faster                                            |
| thread_accumulate_naive     | 35.8 ms                                                         | 33.3 ms: 1.07x faster                                           |
| thread_accumulate_optimized | 35.1 ms                                                         | 32.7 ms: 1.07x faster                                           |
| thread_memo_naive           | 11.5 ms                                                         | 10.8 ms: 1.07x faster                                           |
| thread_pipeline_optimized   | 22.5 ms                                                         | 21.0 ms: 1.07x faster                                           |
| thread_memo_optimized       | 15.9 ms                                                         | 15.0 ms: 1.06x faster                                           |
| thread_pipeline_naive       | 32.0 ms                                                         | 30.7 ms: 1.04x faster                                           |
| thread_counter_optimized    | 17.1 ms                                                         | 16.7 ms: 1.02x faster                                           |
| thread_counter_naive        | 20.2 ms                                                         | 20.3 ms: 1.01x slower                                           |
| thread_montecarlo_optimized | 13.9 ms                                                         | 14.4 ms: 1.03x slower                                           |
| thread_montecarlo_naive     | 15.8 ms                                                         | 19.7 ms: 1.25x slower                                           |
| Geometric mean              | (ref)                                                           | 1.03x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| argparse_many_optionals          | 34.4 ms                                                         | 7.62 ms: 4.52x faster                                           |
| argparse_subparsers              | 686 us                                                          | 518 us: 1.32x faster                                            |
| scimark_fft                      | 226 ms                                                          | 186 ms: 1.21x faster                                            |
| richards                         | 32.6 ms                                                         | 27.6 ms: 1.18x faster                                           |
| pickle_list                      | 3.24 us                                                         | 2.79 us: 1.16x faster                                           |
| richards_super                   | 37.4 ms                                                         | 32.2 ms: 1.16x faster                                           |
| noop                             | 19.4 ns                                                         | 16.8 ns: 1.15x faster                                           |
| spectral_norm                    | 65.6 ms                                                         | 57.4 ms: 1.14x faster                                           |
| mako                             | 7.40 ms                                                         | 6.48 ms: 1.14x faster                                           |
| deltablue                        | 2.34 ms                                                         | 2.05 ms: 1.14x faster                                           |
| unpickle_pure_python             | 152 us                                                          | 134 us: 1.14x faster                                            |
| float                            | 47.3 ms                                                         | 42.1 ms: 1.12x faster                                           |
| thread_mandelbrot_naive          | 233 ms                                                          | 211 ms: 1.11x faster                                            |
| thread_mandelbrot_optimized      | 233 ms                                                          | 212 ms: 1.10x faster                                            |
| base64_large                     | 3.63 ms                                                         | 3.31 ms: 1.10x faster                                           |
| asyncio_tcp                      | 325 ms                                                          | 297 ms: 1.09x faster                                            |
| ascii85_large                    | 667 ms                                                          | 613 ms: 1.09x faster                                            |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 2.93 ms: 1.09x faster                                           |
| thread_accumulate_naive          | 35.8 ms                                                         | 33.3 ms: 1.07x faster                                           |
| thread_accumulate_optimized      | 35.1 ms                                                         | 32.7 ms: 1.07x faster                                           |
| thread_memo_naive                | 11.5 ms                                                         | 10.8 ms: 1.07x faster                                           |
| xml_etree_generate               | 62.6 ms                                                         | 58.5 ms: 1.07x faster                                           |
| thread_pipeline_optimized        | 22.5 ms                                                         | 21.0 ms: 1.07x faster                                           |
| thread_memo_optimized            | 15.9 ms                                                         | 15.0 ms: 1.06x faster                                           |
| networkx_connected_components    | 438 ms                                                          | 416 ms: 1.05x faster                                            |
| xml_etree_process                | 44.7 ms                                                         | 42.9 ms: 1.04x faster                                           |
| ascii85_small                    | 12.7 ms                                                         | 12.2 ms: 1.04x faster                                           |
| thread_pipeline_naive            | 32.0 ms                                                         | 30.7 ms: 1.04x faster                                           |
| base64_small                     | 186 us                                                          | 179 us: 1.04x faster                                            |
| create_gc_cycles                 | 1.96 ms                                                         | 1.89 ms: 1.04x faster                                           |
| base85_small                     | 4.69 ms                                                         | 4.51 ms: 1.04x faster                                           |
| telco                            | 5.59 ms                                                         | 5.38 ms: 1.04x faster                                           |
| networkx_shortest_path           | 444 ms                                                          | 432 ms: 1.03x faster                                            |
| thread_counter_optimized         | 17.1 ms                                                         | 16.7 ms: 1.02x faster                                           |
| base85_large                     | 248 ms                                                          | 242 ms: 1.02x faster                                            |
| fastapi_http                     | 216 ms                                                          | 212 ms: 1.02x faster                                            |
| decimal_pi                       | 208 ms                                                          | 204 ms: 1.02x faster                                            |
| base16_large                     | 5.33 ms                                                         | 5.25 ms: 1.02x faster                                           |
| fannkuch                         | 245 ms                                                          | 242 ms: 1.02x faster                                            |
| tomli_loads                      | 1.44 sec                                                        | 1.42 sec: 1.01x faster                                          |
| urlsafe_base64_small             | 329 us                                                          | 325 us: 1.01x faster                                            |
| pidigits                         | 189 ms                                                          | 187 ms: 1.01x faster                                            |
| bpe_tokeniser                    | 3.00 sec                                                        | 2.98 sec: 1.01x faster                                          |
| quadtree_nbody                   | 596 ms                                                          | 592 ms: 1.01x faster                                            |
| scimark_sor                      | 75.7 ms                                                         | 75.3 ms: 1.01x faster                                           |
| pickle_dict                      | 21.5 us                                                         | 21.5 us: 1.00x faster                                           |
| thread_counter_naive             | 20.2 ms                                                         | 20.3 ms: 1.01x slower                                           |
| asyncio_websockets               | 296 ms                                                          | 298 ms: 1.01x slower                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.29 sec: 1.01x slower                                          |
| pathlib                          | 13.0 ms                                                         | 13.1 ms: 1.01x slower                                           |
| mdp                              | 946 ms                                                          | 954 ms: 1.01x slower                                            |
| decimal_factorial                | 173 ms                                                          | 175 ms: 1.01x slower                                            |
| coverage                         | 57.4 ms                                                         | 58.0 ms: 1.01x slower                                           |
| pyflate                          | 299 ms                                                          | 303 ms: 1.01x slower                                            |
| regex_compile                    | 93.9 ms                                                         | 95.2 ms: 1.01x slower                                           |
| base16_small                     | 305 us                                                          | 310 us: 1.01x slower                                            |
| meteor_contest                   | 84.1 ms                                                         | 85.5 ms: 1.02x slower                                           |
| logging_silent                   | 65.3 ns                                                         | 66.4 ns: 1.02x slower                                           |
| deepcopy_reduce                  | 2.00 us                                                         | 2.03 us: 1.02x slower                                           |
| python_startup_no_site           | 6.38 ms                                                         | 6.49 ms: 1.02x slower                                           |
| regex_dna                        | 150 ms                                                          | 153 ms: 1.02x slower                                            |
| logging_format                   | 5.35 us                                                         | 5.45 us: 1.02x slower                                           |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 320 ms: 1.02x slower                                            |
| xml_etree_iterparse              | 76.2 ms                                                         | 77.6 ms: 1.02x slower                                           |
| base32_large                     | 292 ms                                                          | 298 ms: 1.02x slower                                            |
| deepcopy                         | 193 us                                                          | 197 us: 1.02x slower                                            |
| deepcopy_memo                    | 18.0 us                                                         | 18.4 us: 1.02x slower                                           |
| pickle                           | 8.20 us                                                         | 8.38 us: 1.02x slower                                           |
| unpickle_list                    | 3.43 us                                                         | 3.51 us: 1.02x slower                                           |
| python_startup                   | 9.73 ms                                                         | 9.96 ms: 1.02x slower                                           |
| logging_simple                   | 4.79 us                                                         | 4.89 us: 1.02x slower                                           |
| networkx_k_core                  | 2.07 sec                                                        | 2.12 sec: 1.02x slower                                          |
| django_template                  | 27.8 ms                                                         | 28.5 ms: 1.02x slower                                           |
| nqueens                          | 56.8 ms                                                         | 58.2 ms: 1.02x slower                                           |
| sympy_sum                        | 106 ms                                                          | 109 ms: 1.03x slower                                            |
| pickle_pure_python               | 240 us                                                          | 247 us: 1.03x slower                                            |
| tornado_http                     | 101 ms                                                          | 104 ms: 1.03x slower                                            |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 14.4 ms: 1.03x slower                                           |
| nbody                            | 67.9 ms                                                         | 70.1 ms: 1.03x slower                                           |
| base32_small                     | 5.71 ms                                                         | 5.90 ms: 1.03x slower                                           |
| genshi_text                      | 16.8 ms                                                         | 17.3 ms: 1.03x slower                                           |
| chaos                            | 43.8 ms                                                         | 45.2 ms: 1.03x slower                                           |
| html5lib                         | 46.9 ms                                                         | 48.7 ms: 1.04x slower                                           |
| sympy_integrate                  | 15.4 ms                                                         | 16.0 ms: 1.04x slower                                           |
| scimark_lu                       | 73.8 ms                                                         | 76.9 ms: 1.04x slower                                           |
| generators                       | 20.3 ms                                                         | 21.2 ms: 1.04x slower                                           |
| raytrace                         | 194 ms                                                          | 203 ms: 1.05x slower                                            |
| json_dumps                       | 6.95 ms                                                         | 7.28 ms: 1.05x slower                                           |
| sympy_str                        | 194 ms                                                          | 203 ms: 1.05x slower                                            |
| scimark_monte_carlo              | 40.7 ms                                                         | 42.7 ms: 1.05x slower                                           |
| sqlalchemy_imperative            | 14.2 ms                                                         | 14.9 ms: 1.05x slower                                           |
| unpickle                         | 10.2 us                                                         | 10.7 us: 1.05x slower                                           |
| sqlglot_v2_parse                 | 911 us                                                          | 958 us: 1.05x slower                                            |
| xdsl_constant_fold               | 34.7 ms                                                         | 36.6 ms: 1.05x slower                                           |
| gc_traversal                     | 3.26 ms                                                         | 3.43 ms: 1.05x slower                                           |
| genshi_xml                       | 39.5 ms                                                         | 41.7 ms: 1.06x slower                                           |
| async_tree_eager                 | 81.3 ms                                                         | 85.9 ms: 1.06x slower                                           |
| sympy_expand                     | 332 ms                                                          | 350 ms: 1.06x slower                                            |
| crypto_pyaes                     | 54.5 ms                                                         | 57.6 ms: 1.06x slower                                           |
| thrift                           | 1.86 ms                                                         | 1.99 ms: 1.07x slower                                           |
| chameleon                        | 9.52 ms                                                         | 10.1 ms: 1.07x slower                                           |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.23 ms: 1.07x slower                                           |
| typing_runtime_protocols         | 112 us                                                          | 119 us: 1.07x slower                                            |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 41.7 ms: 1.07x slower                                           |
| pycparser                        | 851 ms                                                          | 911 ms: 1.07x slower                                            |
| regex_effbot                     | 1.95 ms                                                         | 2.09 ms: 1.07x slower                                           |
| pylint                           | 216 ms                                                          | 231 ms: 1.07x slower                                            |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 84.5 ms: 1.08x slower                                           |
| coroutines                       | 15.1 ms                                                         | 16.4 ms: 1.08x slower                                           |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 397 ms: 1.09x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 197 ms: 1.09x slower                                            |
| hexiom                           | 4.11 ms                                                         | 4.53 ms: 1.10x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 450 ms: 1.10x slower                                            |
| comprehensions                   | 10.8 us                                                         | 12.0 us: 1.11x slower                                           |
| json                             | 3.42 ms                                                         | 3.80 ms: 1.11x slower                                           |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 457 ms: 1.11x slower                                            |
| json_loads                       | 17.5 us                                                         | 19.6 us: 1.12x slower                                           |
| async_generators                 | 228 ms                                                          | 257 ms: 1.13x slower                                            |
| async_tree_eager_tg              | 182 ms                                                          | 207 ms: 1.13x slower                                            |
| async_tree_none                  | 228 ms                                                          | 266 ms: 1.17x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 651 ms: 1.18x slower                                            |
| go                               | 84.7 ms                                                         | 100 ms: 1.18x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 333 ms: 1.19x slower                                            |
| xml_etree_parse                  | 94.3 ms                                                         | 112 ms: 1.19x slower                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 282 ms: 1.19x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 268 ms: 1.20x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 667 ms: 1.21x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 343 ms: 1.24x slower                                            |
| thread_montecarlo_naive          | 15.8 ms                                                         | 19.7 ms: 1.25x slower                                           |
| async_tree_io_tg                 | 539 ms                                                          | 694 ms: 1.29x slower                                            |
| pprint_pformat                   | 989 ms                                                          | 1.28 sec: 1.29x slower                                          |
| async_tree_io                    | 531 ms                                                          | 686 ms: 1.29x slower                                            |
| pprint_safe_repr                 | 474 ms                                                          | 632 ms: 1.33x slower                                            |
| mypy2                            | 753 ms                                                          | 1.06 sec: 1.41x slower                                          |
| unpack_sequence                  | 25.8 ns                                                         | 103 ns: 4.01x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (2): docutils, regex_v8

- Geometric mean (including insignificant results): 1.019x slower

# HPT report

- Reliability score: 99.61% likely to be slow
- 90% likely to have a slowdown of 1.00x
- 95% likely to have a slowdown of 1.00x
- 99% likely to have a slowdown of 1.00x

# Memory
- memory change: 1.02x