# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.064x slower
- HPT reliability: 99.92%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.00x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 10.2 ms: 1.07x slower                                           |
| docutils       | 1.95 sec                                                        | 2.00 sec: 1.03x slower                                          |
| fastapi_http   | 216 ms                                                          | 219 ms: 1.01x slower                                            |
| html5lib       | 46.9 ms                                                         | 52.9 ms: 1.13x slower                                           |
| tornado_http   | 101 ms                                                          | 104 ms: 1.03x slower                                            |
| Geometric mean | (ref)                                                           | 1.05x slower                                                    |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                          | 59.5 ms: 3.07x faster                                           |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 178 ms: 1.33x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 287 ms: 1.26x faster                                            |
| asyncio_tcp                      | 325 ms                                                          | 302 ms: 1.07x faster                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.30 sec: 1.01x slower                                          |
| coroutines                       | 15.1 ms                                                         | 15.5 ms: 1.03x slower                                           |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 328 ms: 1.05x slower                                            |
| async_generators                 | 228 ms                                                          | 260 ms: 1.14x slower                                            |
| async_tree_eager                 | 81.3 ms                                                         | 94.4 ms: 1.16x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 477 ms: 1.17x slower                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 492 ms: 1.20x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 224 ms: 1.25x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 729 ms: 1.32x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 296 ms: 1.33x slower                                            |
| async_tree_none                  | 228 ms                                                          | 310 ms: 1.36x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 756 ms: 1.37x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 392 ms: 1.40x slower                                            |
| async_tree_io                    | 531 ms                                                          | 749 ms: 1.41x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 786 ms: 1.46x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 423 ms: 1.53x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.09x slower                                                    |

Benchmark hidden because not significant (1): asyncio_websockets

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 18.3 ns: 1.06x faster                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_pi        | 208 ms                                                          | 204 ms: 1.02x faster                                            |
| decimal_factorial | 173 ms                                                          | 178 ms: 1.03x slower                                            |
| Geometric mean    | (ref)                                                           | 1.01x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| nbody          | 67.9 ms                                                         | 62.5 ms: 1.09x faster                                           |
| quadtree_nbody | 596 ms                                                          | 570 ms: 1.05x faster                                            |
| pidigits       | 189 ms                                                          | 188 ms: 1.01x faster                                            |
| float          | 47.3 ms                                                         | 53.5 ms: 1.13x slower                                           |
| Geometric mean | (ref)                                                           | 1.00x faster                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                         | 14.5 ms: 1.02x faster                                           |
| regex_compile  | 93.9 ms                                                         | 98.8 ms: 1.05x slower                                           |
| regex_dna      | 150 ms                                                          | 159 ms: 1.06x slower                                            |
| regex_effbot   | 1.95 ms                                                         | 2.29 ms: 1.18x slower                                           |
| Geometric mean | (ref)                                                           | 1.06x slower                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| ascii85_large        | 667 ms                                                          | 548 ms: 1.22x faster                                            |
| ascii85_small        | 12.7 ms                                                         | 10.9 ms: 1.17x faster                                           |
| base85_small         | 4.69 ms                                                         | 4.19 ms: 1.12x faster                                           |
| pickle               | 8.20 us                                                         | 7.38 us: 1.11x faster                                           |
| json_loads           | 17.5 us                                                         | 15.9 us: 1.10x faster                                           |
| pickle_pure_python   | 240 us                                                          | 219 us: 1.09x faster                                            |
| base64_large         | 3.63 ms                                                         | 3.33 ms: 1.09x faster                                           |
| base85_large         | 248 ms                                                          | 227 ms: 1.09x faster                                            |
| pickle_list          | 3.24 us                                                         | 3.02 us: 1.07x faster                                           |
| unpickle_pure_python | 152 us                                                          | 143 us: 1.06x faster                                            |
| base32_large         | 292 ms                                                          | 281 ms: 1.04x faster                                            |
| unpickle_list        | 3.43 us                                                         | 3.31 us: 1.04x faster                                           |
| xml_etree_generate   | 62.6 ms                                                         | 60.8 ms: 1.03x faster                                           |
| base64_small         | 186 us                                                          | 181 us: 1.03x faster                                            |
| json_dumps           | 6.95 ms                                                         | 6.85 ms: 1.01x faster                                           |
| pickle_dict          | 21.5 us                                                         | 21.8 us: 1.01x slower                                           |
| unpickle             | 10.2 us                                                         | 10.3 us: 1.01x slower                                           |
| xml_etree_iterparse  | 76.2 ms                                                         | 77.8 ms: 1.02x slower                                           |
| xml_etree_process    | 44.7 ms                                                         | 45.8 ms: 1.02x slower                                           |
| xml_etree_parse      | 94.3 ms                                                         | 102 ms: 1.09x slower                                            |
| base16_small         | 305 us                                                          | 754 us: 2.47x slower                                            |
| base16_large         | 5.33 ms                                                         | 37.3 ms: 6.99x slower                                           |
| Geometric mean       | (ref)                                                           | 1.07x slower                                                    |

Benchmark hidden because not significant (3): base32_small, tomli_loads, urlsafe_base64_small

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 10.3 ms: 1.06x slower                                           |
| python_startup_no_site | 6.38 ms                                                         | 7.28 ms: 1.14x slower                                           |
| Geometric mean         | (ref)                                                           | 1.10x slower                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| mako            | 7.40 ms                                                         | 5.98 ms: 1.24x faster                                           |
| django_template | 27.8 ms                                                         | 30.2 ms: 1.08x slower                                           |
| genshi_text     | 16.8 ms                                                         | 21.7 ms: 1.29x slower                                           |
| genshi_xml      | 39.5 ms                                                         | 51.2 ms: 1.30x slower                                           |
| Geometric mean  | (ref)                                                           | 1.10x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_mandelbrot_naive     | 233 ms                                                          | 184 ms: 1.27x faster                                            |
| thread_mandelbrot_optimized | 233 ms                                                          | 184 ms: 1.27x faster                                            |
| thread_accumulate_optimized | 35.1 ms                                                         | 29.8 ms: 1.18x faster                                           |
| thread_accumulate_naive     | 35.8 ms                                                         | 30.9 ms: 1.16x faster                                           |
| thread_pipeline_optimized   | 22.5 ms                                                         | 19.4 ms: 1.16x faster                                           |
| thread_memo_optimized       | 15.9 ms                                                         | 13.8 ms: 1.15x faster                                           |
| thread_counter_optimized    | 17.1 ms                                                         | 15.3 ms: 1.12x faster                                           |
| thread_montecarlo_optimized | 13.9 ms                                                         | 12.5 ms: 1.11x faster                                           |
| thread_counter_naive        | 20.2 ms                                                         | 19.8 ms: 1.02x faster                                           |
| thread_montecarlo_naive     | 15.8 ms                                                         | 20.1 ms: 1.27x slower                                           |
| thread_pipeline_naive       | 32.0 ms                                                         | 49.2 ms: 1.54x slower                                           |
| thread_memo_naive           | 11.5 ms                                                         | 37.7 ms: 3.28x slower                                           |
| Geometric mean              | (ref)                                                           | 1.05x slower                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                          | 59.5 ms: 3.07x faster                                           |
| argparse_many_optionals          | 34.4 ms                                                         | 13.1 ms: 2.62x faster                                           |
| argparse_subparsers              | 686 us                                                          | 478 us: 1.43x faster                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 178 ms: 1.33x faster                                            |
| thread_mandelbrot_naive          | 233 ms                                                          | 184 ms: 1.27x faster                                            |
| thread_mandelbrot_optimized      | 233 ms                                                          | 184 ms: 1.27x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 287 ms: 1.26x faster                                            |
| scimark_fft                      | 226 ms                                                          | 181 ms: 1.25x faster                                            |
| mako                             | 7.40 ms                                                         | 5.98 ms: 1.24x faster                                           |
| ascii85_large                    | 667 ms                                                          | 548 ms: 1.22x faster                                            |
| fannkuch                         | 245 ms                                                          | 207 ms: 1.18x faster                                            |
| thread_accumulate_optimized      | 35.1 ms                                                         | 29.8 ms: 1.18x faster                                           |
| ascii85_small                    | 12.7 ms                                                         | 10.9 ms: 1.17x faster                                           |
| thread_accumulate_naive          | 35.8 ms                                                         | 30.9 ms: 1.16x faster                                           |
| thread_pipeline_optimized        | 22.5 ms                                                         | 19.4 ms: 1.16x faster                                           |
| thread_memo_optimized            | 15.9 ms                                                         | 13.8 ms: 1.15x faster                                           |
| crypto_pyaes                     | 54.5 ms                                                         | 47.7 ms: 1.14x faster                                           |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 2.81 ms: 1.13x faster                                           |
| base85_small                     | 4.69 ms                                                         | 4.19 ms: 1.12x faster                                           |
| spectral_norm                    | 65.6 ms                                                         | 58.7 ms: 1.12x faster                                           |
| thread_counter_optimized         | 17.1 ms                                                         | 15.3 ms: 1.12x faster                                           |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 12.5 ms: 1.11x faster                                           |
| pickle                           | 8.20 us                                                         | 7.38 us: 1.11x faster                                           |
| create_gc_cycles                 | 1.96 ms                                                         | 1.78 ms: 1.10x faster                                           |
| json_loads                       | 17.5 us                                                         | 15.9 us: 1.10x faster                                           |
| pickle_pure_python               | 240 us                                                          | 219 us: 1.09x faster                                            |
| base64_large                     | 3.63 ms                                                         | 3.33 ms: 1.09x faster                                           |
| base85_large                     | 248 ms                                                          | 227 ms: 1.09x faster                                            |
| nbody                            | 67.9 ms                                                         | 62.5 ms: 1.09x faster                                           |
| asyncio_tcp                      | 325 ms                                                          | 302 ms: 1.07x faster                                            |
| pickle_list                      | 3.24 us                                                         | 3.02 us: 1.07x faster                                           |
| networkx_connected_components    | 438 ms                                                          | 412 ms: 1.06x faster                                            |
| unpickle_pure_python             | 152 us                                                          | 143 us: 1.06x faster                                            |
| json                             | 3.42 ms                                                         | 3.24 ms: 1.06x faster                                           |
| noop                             | 19.4 ns                                                         | 18.3 ns: 1.06x faster                                           |
| gc_traversal                     | 3.26 ms                                                         | 3.09 ms: 1.05x faster                                           |
| networkx_shortest_path           | 444 ms                                                          | 423 ms: 1.05x faster                                            |
| quadtree_nbody                   | 596 ms                                                          | 570 ms: 1.05x faster                                            |
| base32_large                     | 292 ms                                                          | 281 ms: 1.04x faster                                            |
| logging_silent                   | 65.3 ns                                                         | 62.8 ns: 1.04x faster                                           |
| unpickle_list                    | 3.43 us                                                         | 3.31 us: 1.04x faster                                           |
| xml_etree_generate               | 62.6 ms                                                         | 60.8 ms: 1.03x faster                                           |
| base64_small                     | 186 us                                                          | 181 us: 1.03x faster                                            |
| regex_v8                         | 14.8 ms                                                         | 14.5 ms: 1.02x faster                                           |
| decimal_pi                       | 208 ms                                                          | 204 ms: 1.02x faster                                            |
| thread_counter_naive             | 20.2 ms                                                         | 19.8 ms: 1.02x faster                                           |
| json_dumps                       | 6.95 ms                                                         | 6.85 ms: 1.01x faster                                           |
| telco                            | 5.59 ms                                                         | 5.53 ms: 1.01x faster                                           |
| pidigits                         | 189 ms                                                          | 188 ms: 1.01x faster                                            |
| richards                         | 32.6 ms                                                         | 32.4 ms: 1.01x faster                                           |
| meteor_contest                   | 84.1 ms                                                         | 83.7 ms: 1.00x faster                                           |
| logging_format                   | 5.35 us                                                         | 5.37 us: 1.00x slower                                           |
| logging_simple                   | 4.79 us                                                         | 4.82 us: 1.01x slower                                           |
| scimark_monte_carlo              | 40.7 ms                                                         | 41.0 ms: 1.01x slower                                           |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.30 sec: 1.01x slower                                          |
| pickle_dict                      | 21.5 us                                                         | 21.8 us: 1.01x slower                                           |
| sqlalchemy_imperative            | 14.2 ms                                                         | 14.4 ms: 1.01x slower                                           |
| unpickle                         | 10.2 us                                                         | 10.3 us: 1.01x slower                                           |
| fastapi_http                     | 216 ms                                                          | 219 ms: 1.01x slower                                            |
| networkx_k_core                  | 2.07 sec                                                        | 2.11 sec: 1.02x slower                                          |
| pathlib                          | 13.0 ms                                                         | 13.3 ms: 1.02x slower                                           |
| xml_etree_iterparse              | 76.2 ms                                                         | 77.8 ms: 1.02x slower                                           |
| xml_etree_process                | 44.7 ms                                                         | 45.8 ms: 1.02x slower                                           |
| tornado_http                     | 101 ms                                                          | 104 ms: 1.03x slower                                            |
| coroutines                       | 15.1 ms                                                         | 15.5 ms: 1.03x slower                                           |
| docutils                         | 1.95 sec                                                        | 2.00 sec: 1.03x slower                                          |
| decimal_factorial                | 173 ms                                                          | 178 ms: 1.03x slower                                            |
| richards_super                   | 37.4 ms                                                         | 38.6 ms: 1.03x slower                                           |
| coverage                         | 57.4 ms                                                         | 59.9 ms: 1.04x slower                                           |
| pycparser                        | 851 ms                                                          | 888 ms: 1.04x slower                                            |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 328 ms: 1.05x slower                                            |
| regex_compile                    | 93.9 ms                                                         | 98.8 ms: 1.05x slower                                           |
| regex_dna                        | 150 ms                                                          | 159 ms: 1.06x slower                                            |
| python_startup                   | 9.73 ms                                                         | 10.3 ms: 1.06x slower                                           |
| sqlglot_v2_parse                 | 911 us                                                          | 965 us: 1.06x slower                                            |
| chaos                            | 43.8 ms                                                         | 46.6 ms: 1.06x slower                                           |
| comprehensions                   | 10.8 us                                                         | 11.5 us: 1.07x slower                                           |
| raytrace                         | 194 ms                                                          | 207 ms: 1.07x slower                                            |
| mypy2                            | 753 ms                                                          | 806 ms: 1.07x slower                                            |
| chameleon                        | 9.52 ms                                                         | 10.2 ms: 1.07x slower                                           |
| pyflate                          | 299 ms                                                          | 321 ms: 1.07x slower                                            |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.23 ms: 1.07x slower                                           |
| sympy_sum                        | 106 ms                                                          | 114 ms: 1.08x slower                                            |
| sympy_str                        | 194 ms                                                          | 210 ms: 1.08x slower                                            |
| typing_runtime_protocols         | 112 us                                                          | 121 us: 1.08x slower                                            |
| django_template                  | 27.8 ms                                                         | 30.2 ms: 1.08x slower                                           |
| xml_etree_parse                  | 94.3 ms                                                         | 102 ms: 1.09x slower                                            |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 42.6 ms: 1.09x slower                                           |
| sympy_expand                     | 332 ms                                                          | 363 ms: 1.10x slower                                            |
| generators                       | 20.3 ms                                                         | 22.3 ms: 1.10x slower                                           |
| nqueens                          | 56.8 ms                                                         | 62.6 ms: 1.10x slower                                           |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.33 sec: 1.11x slower                                          |
| xdsl_constant_fold               | 34.7 ms                                                         | 38.8 ms: 1.12x slower                                           |
| html5lib                         | 46.9 ms                                                         | 52.9 ms: 1.13x slower                                           |
| sympy_integrate                  | 15.4 ms                                                         | 17.4 ms: 1.13x slower                                           |
| float                            | 47.3 ms                                                         | 53.5 ms: 1.13x slower                                           |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 89.1 ms: 1.14x slower                                           |
| python_startup_no_site           | 6.38 ms                                                         | 7.28 ms: 1.14x slower                                           |
| async_generators                 | 228 ms                                                          | 260 ms: 1.14x slower                                            |
| hexiom                           | 4.11 ms                                                         | 4.72 ms: 1.15x slower                                           |
| async_tree_eager                 | 81.3 ms                                                         | 94.4 ms: 1.16x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 477 ms: 1.17x slower                                            |
| regex_effbot                     | 1.95 ms                                                         | 2.29 ms: 1.18x slower                                           |
| deepcopy_reduce                  | 2.00 us                                                         | 2.36 us: 1.18x slower                                           |
| pylint                           | 216 ms                                                          | 255 ms: 1.18x slower                                            |
| pprint_pformat                   | 989 ms                                                          | 1.18 sec: 1.19x slower                                          |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 492 ms: 1.20x slower                                            |
| deltablue                        | 2.34 ms                                                         | 2.80 ms: 1.20x slower                                           |
| pprint_safe_repr                 | 474 ms                                                          | 574 ms: 1.21x slower                                            |
| thrift                           | 1.86 ms                                                         | 2.26 ms: 1.21x slower                                           |
| async_tree_eager_memoization     | 180 ms                                                          | 224 ms: 1.25x slower                                            |
| thread_montecarlo_naive          | 15.8 ms                                                         | 20.1 ms: 1.27x slower                                           |
| genshi_text                      | 16.8 ms                                                         | 21.7 ms: 1.29x slower                                           |
| genshi_xml                       | 39.5 ms                                                         | 51.2 ms: 1.30x slower                                           |
| deepcopy_memo                    | 18.0 us                                                         | 23.6 us: 1.31x slower                                           |
| async_tree_eager_io_tg           | 550 ms                                                          | 729 ms: 1.32x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 296 ms: 1.33x slower                                            |
| scimark_sor                      | 75.7 ms                                                         | 101 ms: 1.33x slower                                            |
| scimark_lu                       | 73.8 ms                                                         | 98.5 ms: 1.33x slower                                           |
| async_tree_none                  | 228 ms                                                          | 310 ms: 1.36x slower                                            |
| deepcopy                         | 193 us                                                          | 263 us: 1.37x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 756 ms: 1.37x slower                                            |
| go                               | 84.7 ms                                                         | 118 ms: 1.39x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 392 ms: 1.40x slower                                            |
| async_tree_io                    | 531 ms                                                          | 749 ms: 1.41x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 786 ms: 1.46x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 423 ms: 1.53x slower                                            |
| thread_pipeline_naive            | 32.0 ms                                                         | 49.2 ms: 1.54x slower                                           |
| mdp                              | 946 ms                                                          | 2.14 sec: 2.27x slower                                          |
| base16_small                     | 305 us                                                          | 754 us: 2.47x slower                                            |
| unpack_sequence                  | 25.8 ns                                                         | 80.9 ns: 3.14x slower                                           |
| thread_memo_naive                | 11.5 ms                                                         | 37.7 ms: 3.28x slower                                           |
| base16_large                     | 5.33 ms                                                         | 37.3 ms: 6.99x slower                                           |
| Geometric mean                   | (ref)                                                           | 1.07x slower                                                    |

Benchmark hidden because not significant (4): base32_small, tomli_loads, asyncio_websockets, urlsafe_base64_small

- Geometric mean (including insignificant results): 1.064x slower

# HPT report

- Reliability score: 99.92% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.00x