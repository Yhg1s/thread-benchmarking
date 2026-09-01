# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.003x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.04x slower
- Memory change: 1.45x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 11.4 ms: 1.20x slower                                           |
| docutils       | 1.95 sec                                                        | 2.05 sec: 1.05x slower                                          |
| fastapi_http   | 216 ms                                                          | 191 ms: 1.13x faster                                            |
| html5lib       | 46.9 ms                                                         | 47.9 ms: 1.02x slower                                           |
| tornado_http   | 101 ms                                                          | 96.9 ms: 1.05x faster                                           |
| Geometric mean | (ref)                                                           | 1.02x slower                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_eager_io_tg           | 550 ms                                                          | 484 ms: 1.14x faster                                            |
| async_tree_io_tg                 | 539 ms                                                          | 482 ms: 1.12x faster                                            |
| async_tree_eager_io              | 552 ms                                                          | 507 ms: 1.09x faster                                            |
| asyncio_tcp                      | 325 ms                                                          | 305 ms: 1.06x faster                                            |
| async_tree_none_tg               | 223 ms                                                          | 215 ms: 1.04x faster                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 402 ms: 1.02x faster                                            |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 321 ms: 1.02x slower                                            |
| async_tree_eager_tg              | 182 ms                                                          | 191 ms: 1.05x slower                                            |
| async_tree_none                  | 228 ms                                                          | 240 ms: 1.05x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 382 ms: 1.05x slower                                            |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 431 ms: 1.06x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 195 ms: 1.08x slower                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.39 sec: 1.09x slower                                          |
| async_tree_memoization           | 281 ms                                                          | 306 ms: 1.09x slower                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 264 ms: 1.12x slower                                            |
| async_generators                 | 228 ms                                                          | 256 ms: 1.12x slower                                            |
| async_tree_eager                 | 81.3 ms                                                         | 100 ms: 1.23x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (4): async_tree_io, asyncio_websockets, coroutines, async_tree_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 21.6 ns: 1.12x slower                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 191 ms: 1.10x slower                                            |
| decimal_pi        | 208 ms                                                          | 249 ms: 1.20x slower                                            |
| Geometric mean    | (ref)                                                           | 1.15x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pidigits       | 189 ms                                                          | 186 ms: 1.01x faster                                            |
| quadtree_nbody | 596 ms                                                          | 658 ms: 1.10x slower                                            |
| float          | 47.3 ms                                                         | 53.7 ms: 1.14x slower                                           |
| nbody          | 67.9 ms                                                         | 81.8 ms: 1.21x slower                                           |
| Geometric mean | (ref)                                                           | 1.10x slower                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                         | 14.4 ms: 1.03x faster                                           |
| regex_dna      | 150 ms                                                          | 151 ms: 1.01x slower                                            |
| regex_effbot   | 1.95 ms                                                         | 2.00 ms: 1.03x slower                                           |
| regex_compile  | 93.9 ms                                                         | 104 ms: 1.11x slower                                            |
| Geometric mean | (ref)                                                           | 1.03x slower                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| xml_etree_iterparse  | 76.2 ms                                                         | 67.8 ms: 1.12x faster                                           |
| base64_large         | 3.63 ms                                                         | 3.37 ms: 1.08x faster                                           |
| base16_large         | 5.33 ms                                                         | 4.97 ms: 1.07x faster                                           |
| base64_small         | 186 us                                                          | 177 us: 1.05x faster                                            |
| base16_small         | 305 us                                                          | 295 us: 1.04x faster                                            |
| urlsafe_base64_small | 329 us                                                          | 335 us: 1.02x slower                                            |
| pickle_dict          | 21.5 us                                                         | 22.4 us: 1.04x slower                                           |
| pickle               | 8.20 us                                                         | 8.55 us: 1.04x slower                                           |
| unpickle_pure_python | 152 us                                                          | 159 us: 1.05x slower                                            |
| base85_small         | 4.69 ms                                                         | 4.92 ms: 1.05x slower                                           |
| pickle_pure_python   | 240 us                                                          | 253 us: 1.05x slower                                            |
| base85_large         | 248 ms                                                          | 265 ms: 1.07x slower                                            |
| xml_etree_parse      | 94.3 ms                                                         | 101 ms: 1.07x slower                                            |
| tomli_loads          | 1.44 sec                                                        | 1.55 sec: 1.07x slower                                          |
| xml_etree_generate   | 62.6 ms                                                         | 67.7 ms: 1.08x slower                                           |
| base32_large         | 292 ms                                                          | 321 ms: 1.10x slower                                            |
| xml_etree_process    | 44.7 ms                                                         | 49.3 ms: 1.10x slower                                           |
| ascii85_large        | 667 ms                                                          | 743 ms: 1.11x slower                                            |
| ascii85_small        | 12.7 ms                                                         | 14.2 ms: 1.12x slower                                           |
| base32_small         | 5.71 ms                                                         | 6.39 ms: 1.12x slower                                           |
| unpickle_list        | 3.43 us                                                         | 3.90 us: 1.14x slower                                           |
| json_dumps           | 6.95 ms                                                         | 7.98 ms: 1.15x slower                                           |
| unpickle             | 10.2 us                                                         | 12.2 us: 1.20x slower                                           |
| pickle_list          | 3.24 us                                                         | 4.01 us: 1.24x slower                                           |
| json_loads           | 17.5 us                                                         | 25.0 us: 1.43x slower                                           |
| Geometric mean       | (ref)                                                           | 1.07x slower                                                    |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 11.9 ms: 1.22x slower                                           |
| python_startup_no_site | 6.38 ms                                                         | 8.35 ms: 1.31x slower                                           |
| Geometric mean         | (ref)                                                           | 1.26x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| django_template | 27.8 ms                                                         | 30.6 ms: 1.10x slower                                           |
| genshi_xml      | 39.5 ms                                                         | 44.5 ms: 1.13x slower                                           |
| genshi_text     | 16.8 ms                                                         | 19.6 ms: 1.17x slower                                           |
| mako            | 7.40 ms                                                         | 11.0 ms: 1.48x slower                                           |
| Geometric mean  | (ref)                                                           | 1.21x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                          | 61.7 ms: 3.78x faster                                           |
| thread_mandelbrot_optimized | 233 ms                                                          | 63.4 ms: 3.67x faster                                           |
| thread_accumulate_optimized | 35.1 ms                                                         | 9.61 ms: 3.65x faster                                           |
| thread_pipeline_optimized   | 22.5 ms                                                         | 6.23 ms: 3.61x faster                                           |
| thread_counter_optimized    | 17.1 ms                                                         | 4.90 ms: 3.49x faster                                           |
| thread_memo_optimized       | 15.9 ms                                                         | 5.42 ms: 2.94x faster                                           |
| thread_montecarlo_optimized | 13.9 ms                                                         | 4.80 ms: 2.90x faster                                           |
| thread_accumulate_naive     | 35.8 ms                                                         | 12.5 ms: 2.87x faster                                           |
| thread_pipeline_naive       | 32.0 ms                                                         | 27.0 ms: 1.18x faster                                           |
| thread_counter_naive        | 20.2 ms                                                         | 21.1 ms: 1.04x slower                                           |
| thread_montecarlo_naive     | 15.8 ms                                                         | 29.3 ms: 1.86x slower                                           |
| thread_memo_naive           | 11.5 ms                                                         | 23.6 ms: 2.05x slower                                           |
| Geometric mean              | (ref)                                                           | 2.02x faster                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_gcc9-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| argparse_many_optionals          | 34.4 ms                                                         | 7.90 ms: 4.35x faster                                           |
| thread_mandelbrot_naive          | 233 ms                                                          | 61.7 ms: 3.78x faster                                           |
| thread_mandelbrot_optimized      | 233 ms                                                          | 63.4 ms: 3.67x faster                                           |
| thread_accumulate_optimized      | 35.1 ms                                                         | 9.61 ms: 3.65x faster                                           |
| thread_pipeline_optimized        | 22.5 ms                                                         | 6.23 ms: 3.61x faster                                           |
| thread_counter_optimized         | 17.1 ms                                                         | 4.90 ms: 3.49x faster                                           |
| thread_memo_optimized            | 15.9 ms                                                         | 5.42 ms: 2.94x faster                                           |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 4.80 ms: 2.90x faster                                           |
| thread_accumulate_naive          | 35.8 ms                                                         | 12.5 ms: 2.87x faster                                           |
| gc_traversal                     | 3.26 ms                                                         | 1.68 ms: 1.94x faster                                           |
| create_gc_cycles                 | 1.96 ms                                                         | 1.34 ms: 1.47x faster                                           |
| argparse_subparsers              | 686 us                                                          | 536 us: 1.28x faster                                            |
| thread_pipeline_naive            | 32.0 ms                                                         | 27.0 ms: 1.18x faster                                           |
| async_tree_eager_io_tg           | 550 ms                                                          | 484 ms: 1.14x faster                                            |
| fastapi_http                     | 216 ms                                                          | 191 ms: 1.13x faster                                            |
| xml_etree_iterparse              | 76.2 ms                                                         | 67.8 ms: 1.12x faster                                           |
| async_tree_io_tg                 | 539 ms                                                          | 482 ms: 1.12x faster                                            |
| async_tree_eager_io              | 552 ms                                                          | 507 ms: 1.09x faster                                            |
| base64_large                     | 3.63 ms                                                         | 3.37 ms: 1.08x faster                                           |
| base16_large                     | 5.33 ms                                                         | 4.97 ms: 1.07x faster                                           |
| asyncio_tcp                      | 325 ms                                                          | 305 ms: 1.06x faster                                            |
| base64_small                     | 186 us                                                          | 177 us: 1.05x faster                                            |
| tornado_http                     | 101 ms                                                          | 96.9 ms: 1.05x faster                                           |
| async_tree_none_tg               | 223 ms                                                          | 215 ms: 1.04x faster                                            |
| base16_small                     | 305 us                                                          | 295 us: 1.04x faster                                            |
| regex_v8                         | 14.8 ms                                                         | 14.4 ms: 1.03x faster                                           |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 402 ms: 1.02x faster                                            |
| pycparser                        | 851 ms                                                          | 837 ms: 1.02x faster                                            |
| pathlib                          | 13.0 ms                                                         | 12.8 ms: 1.02x faster                                           |
| pidigits                         | 189 ms                                                          | 186 ms: 1.01x faster                                            |
| regex_dna                        | 150 ms                                                          | 151 ms: 1.01x slower                                            |
| urlsafe_base64_small             | 329 us                                                          | 335 us: 1.02x slower                                            |
| html5lib                         | 46.9 ms                                                         | 47.9 ms: 1.02x slower                                           |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 321 ms: 1.02x slower                                            |
| regex_effbot                     | 1.95 ms                                                         | 2.00 ms: 1.03x slower                                           |
| networkx_k_core                  | 2.07 sec                                                        | 2.13 sec: 1.03x slower                                          |
| pickle_dict                      | 21.5 us                                                         | 22.4 us: 1.04x slower                                           |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 40.7 ms: 1.04x slower                                           |
| thread_counter_naive             | 20.2 ms                                                         | 21.1 ms: 1.04x slower                                           |
| pickle                           | 8.20 us                                                         | 8.55 us: 1.04x slower                                           |
| generators                       | 20.3 ms                                                         | 21.3 ms: 1.05x slower                                           |
| async_tree_eager_tg              | 182 ms                                                          | 191 ms: 1.05x slower                                            |
| pylint                           | 216 ms                                                          | 226 ms: 1.05x slower                                            |
| unpickle_pure_python             | 152 us                                                          | 159 us: 1.05x slower                                            |
| base85_small                     | 4.69 ms                                                         | 4.92 ms: 1.05x slower                                           |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.15 sec: 1.05x slower                                          |
| docutils                         | 1.95 sec                                                        | 2.05 sec: 1.05x slower                                          |
| async_tree_none                  | 228 ms                                                          | 240 ms: 1.05x slower                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 382 ms: 1.05x slower                                            |
| pickle_pure_python               | 240 us                                                          | 253 us: 1.05x slower                                            |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 431 ms: 1.06x slower                                            |
| mdp                              | 946 ms                                                          | 1.01 sec: 1.06x slower                                          |
| base85_large                     | 248 ms                                                          | 265 ms: 1.07x slower                                            |
| logging_silent                   | 65.3 ns                                                         | 69.8 ns: 1.07x slower                                           |
| thrift                           | 1.86 ms                                                         | 2.00 ms: 1.07x slower                                           |
| sympy_sum                        | 106 ms                                                          | 114 ms: 1.07x slower                                            |
| xml_etree_parse                  | 94.3 ms                                                         | 101 ms: 1.07x slower                                            |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 84.0 ms: 1.07x slower                                           |
| tomli_loads                      | 1.44 sec                                                        | 1.55 sec: 1.07x slower                                          |
| scimark_fft                      | 226 ms                                                          | 243 ms: 1.07x slower                                            |
| xml_etree_generate               | 62.6 ms                                                         | 67.7 ms: 1.08x slower                                           |
| async_tree_eager_memoization     | 180 ms                                                          | 195 ms: 1.08x slower                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.39 sec: 1.09x slower                                          |
| telco                            | 5.59 ms                                                         | 6.08 ms: 1.09x slower                                           |
| sympy_integrate                  | 15.4 ms                                                         | 16.7 ms: 1.09x slower                                           |
| async_tree_memoization           | 281 ms                                                          | 306 ms: 1.09x slower                                            |
| base32_large                     | 292 ms                                                          | 321 ms: 1.10x slower                                            |
| django_template                  | 27.8 ms                                                         | 30.6 ms: 1.10x slower                                           |
| sympy_str                        | 194 ms                                                          | 213 ms: 1.10x slower                                            |
| xml_etree_process                | 44.7 ms                                                         | 49.3 ms: 1.10x slower                                           |
| decimal_factorial                | 173 ms                                                          | 191 ms: 1.10x slower                                            |
| quadtree_nbody                   | 596 ms                                                          | 658 ms: 1.10x slower                                            |
| chaos                            | 43.8 ms                                                         | 48.4 ms: 1.11x slower                                           |
| sympy_expand                     | 332 ms                                                          | 367 ms: 1.11x slower                                            |
| regex_compile                    | 93.9 ms                                                         | 104 ms: 1.11x slower                                            |
| ascii85_large                    | 667 ms                                                          | 743 ms: 1.11x slower                                            |
| scimark_sor                      | 75.7 ms                                                         | 84.2 ms: 1.11x slower                                           |
| ascii85_small                    | 12.7 ms                                                         | 14.2 ms: 1.12x slower                                           |
| noop                             | 19.4 ns                                                         | 21.6 ns: 1.12x slower                                           |
| go                               | 84.7 ms                                                         | 94.7 ms: 1.12x slower                                           |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 264 ms: 1.12x slower                                            |
| nqueens                          | 56.8 ms                                                         | 63.6 ms: 1.12x slower                                           |
| base32_small                     | 5.71 ms                                                         | 6.39 ms: 1.12x slower                                           |
| async_generators                 | 228 ms                                                          | 256 ms: 1.12x slower                                            |
| pprint_safe_repr                 | 474 ms                                                          | 533 ms: 1.12x slower                                            |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.30 ms: 1.13x slower                                           |
| genshi_xml                       | 39.5 ms                                                         | 44.5 ms: 1.13x slower                                           |
| spectral_norm                    | 65.6 ms                                                         | 74.3 ms: 1.13x slower                                           |
| float                            | 47.3 ms                                                         | 53.7 ms: 1.14x slower                                           |
| hexiom                           | 4.11 ms                                                         | 4.67 ms: 1.14x slower                                           |
| xdsl_constant_fold               | 34.7 ms                                                         | 39.5 ms: 1.14x slower                                           |
| pprint_pformat                   | 989 ms                                                          | 1.12 sec: 1.14x slower                                          |
| unpickle_list                    | 3.43 us                                                         | 3.90 us: 1.14x slower                                           |
| pyflate                          | 299 ms                                                          | 341 ms: 1.14x slower                                            |
| richards                         | 32.6 ms                                                         | 37.2 ms: 1.14x slower                                           |
| scimark_lu                       | 73.8 ms                                                         | 84.5 ms: 1.14x slower                                           |
| networkx_connected_components    | 438 ms                                                          | 501 ms: 1.15x slower                                            |
| json_dumps                       | 6.95 ms                                                         | 7.98 ms: 1.15x slower                                           |
| richards_super                   | 37.4 ms                                                         | 43.0 ms: 1.15x slower                                           |
| sqlglot_v2_parse                 | 911 us                                                          | 1.05 ms: 1.15x slower                                           |
| networkx_shortest_path           | 444 ms                                                          | 516 ms: 1.16x slower                                            |
| deltablue                        | 2.34 ms                                                         | 2.71 ms: 1.16x slower                                           |
| meteor_contest                   | 84.1 ms                                                         | 97.9 ms: 1.16x slower                                           |
| deepcopy                         | 193 us                                                          | 224 us: 1.16x slower                                            |
| comprehensions                   | 10.8 us                                                         | 12.6 us: 1.17x slower                                           |
| genshi_text                      | 16.8 ms                                                         | 19.6 ms: 1.17x slower                                           |
| deepcopy_reduce                  | 2.00 us                                                         | 2.34 us: 1.17x slower                                           |
| logging_simple                   | 4.79 us                                                         | 5.61 us: 1.17x slower                                           |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.73 ms: 1.17x slower                                           |
| logging_format                   | 5.35 us                                                         | 6.30 us: 1.18x slower                                           |
| raytrace                         | 194 ms                                                          | 229 ms: 1.18x slower                                            |
| unpickle                         | 10.2 us                                                         | 12.2 us: 1.20x slower                                           |
| chameleon                        | 9.52 ms                                                         | 11.4 ms: 1.20x slower                                           |
| crypto_pyaes                     | 54.5 ms                                                         | 65.3 ms: 1.20x slower                                           |
| decimal_pi                       | 208 ms                                                          | 249 ms: 1.20x slower                                            |
| nbody                            | 67.9 ms                                                         | 81.8 ms: 1.21x slower                                           |
| unpack_sequence                  | 25.8 ns                                                         | 31.1 ns: 1.21x slower                                           |
| deepcopy_memo                    | 18.0 us                                                         | 21.8 us: 1.21x slower                                           |
| typing_runtime_protocols         | 112 us                                                          | 136 us: 1.21x slower                                            |
| python_startup                   | 9.73 ms                                                         | 11.9 ms: 1.22x slower                                           |
| async_tree_eager                 | 81.3 ms                                                         | 100 ms: 1.23x slower                                            |
| pickle_list                      | 3.24 us                                                         | 4.01 us: 1.24x slower                                           |
| fannkuch                         | 245 ms                                                          | 305 ms: 1.24x slower                                            |
| json                             | 3.42 ms                                                         | 4.28 ms: 1.25x slower                                           |
| mypy2                            | 753 ms                                                          | 941 ms: 1.25x slower                                            |
| scimark_monte_carlo              | 40.7 ms                                                         | 51.0 ms: 1.25x slower                                           |
| python_startup_no_site           | 6.38 ms                                                         | 8.35 ms: 1.31x slower                                           |
| coverage                         | 57.4 ms                                                         | 79.2 ms: 1.38x slower                                           |
| json_loads                       | 17.5 us                                                         | 25.0 us: 1.43x slower                                           |
| mako                             | 7.40 ms                                                         | 11.0 ms: 1.48x slower                                           |
| thread_montecarlo_naive          | 15.8 ms                                                         | 29.3 ms: 1.86x slower                                           |
| thread_memo_naive                | 11.5 ms                                                         | 23.6 ms: 2.05x slower                                           |
| Geometric mean                   | (ref)                                                           | 1.00x faster                                                    |

Benchmark hidden because not significant (4): async_tree_io, asyncio_websockets, coroutines, async_tree_memoization_tg
Ignored benchmarks (1) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d.json: sqlalchemy_imperative

- Geometric mean (including insignificant results): 1.003x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.05x
- 95% likely to have a slowdown of 1.05x
- 99% likely to have a slowdown of 1.04x

# Memory
- memory change: 1.45x