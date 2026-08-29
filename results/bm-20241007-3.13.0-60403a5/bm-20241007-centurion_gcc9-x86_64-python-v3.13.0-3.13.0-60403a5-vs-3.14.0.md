# Results vs. 3.14.0

- fork: python
- ref: v3.13.0
- machine: linux-x86_64
- commit hash: 60403a5
- commit date: 2024-10-07
- overall geometric mean: 1.059x slower
- HPT reliability: 100.00%
- HPT 99th percentile: 1.01x slower
- Memory change: 0.94x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| chameleon      | 9.52 ms                                                         | 9.95 ms: 1.05x slower                                           |
| docutils       | 1.95 sec                                                        | 1.89 sec: 1.03x faster                                          |
| fastapi_http   | 216 ms                                                          | 218 ms: 1.01x slower                                            |
| html5lib       | 46.9 ms                                                         | 51.7 ms: 1.10x slower                                           |
| Geometric mean | (ref)                                                           | 1.02x slower                                                    |

Benchmark hidden because not significant (1): tornado_http

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                          | 58.6 ms: 3.11x faster                                           |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 175 ms: 1.35x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 285 ms: 1.27x faster                                            |
| asyncio_tcp                      | 325 ms                                                          | 318 ms: 1.02x faster                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.29 sec: 1.00x slower                                          |
| coroutines                       | 15.1 ms                                                         | 15.4 ms: 1.02x slower                                           |
| asyncio_websockets               | 296 ms                                                          | 303 ms: 1.02x slower                                            |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 323 ms: 1.03x slower                                            |
| async_generators                 | 228 ms                                                          | 240 ms: 1.05x slower                                            |
| async_tree_eager                 | 81.3 ms                                                         | 89.6 ms: 1.10x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 474 ms: 1.16x slower                                            |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 490 ms: 1.19x slower                                            |
| async_tree_eager_memoization     | 180 ms                                                          | 219 ms: 1.22x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 291 ms: 1.30x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 728 ms: 1.32x slower                                            |
| async_tree_none                  | 228 ms                                                          | 308 ms: 1.35x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 749 ms: 1.36x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 388 ms: 1.38x slower                                            |
| async_tree_io                    | 531 ms                                                          | 741 ms: 1.40x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 778 ms: 1.44x slower                                            |
| async_tree_memoization_tg        | 277 ms                                                          | 419 ms: 1.51x slower                                            |
| Geometric mean                   | (ref)                                                           | 1.08x slower                                                    |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| noop      | 19.4 ns                                                         | 20.5 ns: 1.06x slower                                           |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| decimal_factorial | 173 ms                                                          | 177 ms: 1.02x slower                                            |
| decimal_pi        | 208 ms                                                          | 222 ms: 1.07x slower                                            |
| Geometric mean    | (ref)                                                           | 1.05x slower                                                    |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| nbody          | 67.9 ms                                                         | 65.9 ms: 1.03x faster                                           |
| pidigits       | 189 ms                                                          | 189 ms: 1.00x faster                                            |
| quadtree_nbody | 596 ms                                                          | 626 ms: 1.05x slower                                            |
| float          | 47.3 ms                                                         | 57.0 ms: 1.21x slower                                           |
| Geometric mean | (ref)                                                           | 1.05x slower                                                    |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| regex_v8       | 14.8 ms                                                         | 15.2 ms: 1.03x slower                                           |
| regex_compile  | 93.9 ms                                                         | 98.5 ms: 1.05x slower                                           |
| regex_dna      | 150 ms                                                          | 162 ms: 1.08x slower                                            |
| regex_effbot   | 1.95 ms                                                         | 2.30 ms: 1.18x slower                                           |
| Geometric mean | (ref)                                                           | 1.08x slower                                                    |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| pickle               | 8.20 us                                                         | 7.44 us: 1.10x faster                                           |
| base64_large         | 3.63 ms                                                         | 3.33 ms: 1.09x faster                                           |
| json_loads           | 17.5 us                                                         | 16.2 us: 1.08x faster                                           |
| pickle_pure_python   | 240 us                                                          | 223 us: 1.07x faster                                            |
| base64_small         | 186 us                                                          | 177 us: 1.05x faster                                            |
| pickle_list          | 3.24 us                                                         | 3.14 us: 1.03x faster                                           |
| unpickle_list        | 3.43 us                                                         | 3.33 us: 1.03x faster                                           |
| base85_small         | 4.69 ms                                                         | 4.59 ms: 1.02x faster                                           |
| urlsafe_base64_small | 329 us                                                          | 325 us: 1.01x faster                                            |
| unpickle_pure_python | 152 us                                                          | 151 us: 1.01x faster                                            |
| base32_large         | 292 ms                                                          | 296 ms: 1.01x slower                                            |
| base32_small         | 5.71 ms                                                         | 5.79 ms: 1.02x slower                                           |
| base85_large         | 248 ms                                                          | 252 ms: 1.02x slower                                            |
| pickle_dict          | 21.5 us                                                         | 22.0 us: 1.02x slower                                           |
| xml_etree_generate   | 62.6 ms                                                         | 64.2 ms: 1.02x slower                                           |
| unpickle             | 10.2 us                                                         | 10.5 us: 1.03x slower                                           |
| xml_etree_process    | 44.7 ms                                                         | 46.6 ms: 1.04x slower                                           |
| xml_etree_iterparse  | 76.2 ms                                                         | 79.9 ms: 1.05x slower                                           |
| ascii85_small        | 12.7 ms                                                         | 13.6 ms: 1.07x slower                                           |
| ascii85_large        | 667 ms                                                          | 717 ms: 1.07x slower                                            |
| xml_etree_parse      | 94.3 ms                                                         | 104 ms: 1.11x slower                                            |
| tomli_loads          | 1.44 sec                                                        | 1.62 sec: 1.12x slower                                          |
| base16_small         | 305 us                                                          | 740 us: 2.42x slower                                            |
| base16_large         | 5.33 ms                                                         | 37.0 ms: 6.94x slower                                           |
| Geometric mean       | (ref)                                                           | 1.12x slower                                                    |

Benchmark hidden because not significant (1): json_dumps

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| python_startup         | 9.73 ms                                                         | 9.51 ms: 1.02x faster                                           |
| python_startup_no_site | 6.38 ms                                                         | 6.46 ms: 1.01x slower                                           |
| Geometric mean         | (ref)                                                           | 1.01x faster                                                    |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| mako            | 7.40 ms                                                         | 7.16 ms: 1.03x faster                                           |
| django_template | 27.8 ms                                                         | 27.6 ms: 1.01x faster                                           |
| genshi_xml      | 39.5 ms                                                         | 41.3 ms: 1.05x slower                                           |
| genshi_text     | 16.8 ms                                                         | 17.8 ms: 1.06x slower                                           |
| Geometric mean  | (ref)                                                           | 1.02x slower                                                    |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|-----------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| thread_mandelbrot_optimized | 233 ms                                                          | 208 ms: 1.12x faster                                            |
| thread_mandelbrot_naive     | 233 ms                                                          | 210 ms: 1.11x faster                                            |
| thread_accumulate_optimized | 35.1 ms                                                         | 32.3 ms: 1.08x faster                                           |
| thread_pipeline_optimized   | 22.5 ms                                                         | 20.9 ms: 1.08x faster                                           |
| thread_accumulate_naive     | 35.8 ms                                                         | 33.4 ms: 1.07x faster                                           |
| thread_memo_optimized       | 15.9 ms                                                         | 15.3 ms: 1.04x faster                                           |
| thread_counter_optimized    | 17.1 ms                                                         | 16.5 ms: 1.03x faster                                           |
| thread_counter_naive        | 20.2 ms                                                         | 20.6 ms: 1.02x slower                                           |
| thread_montecarlo_optimized | 13.9 ms                                                         | 14.5 ms: 1.04x slower                                           |
| thread_montecarlo_naive     | 15.8 ms                                                         | 19.0 ms: 1.21x slower                                           |
| thread_pipeline_naive       | 32.0 ms                                                         | 47.3 ms: 1.48x slower                                           |
| thread_memo_naive           | 11.5 ms                                                         | 36.1 ms: 3.13x slower                                           |
| Geometric mean              | (ref)                                                           | 1.11x slower                                                    |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc9-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20241007-centurion_gcc9-x86_64-python-v3.13.0-3.13.0-60403a5 |
|----------------------------------|:---------------------------------------------------------------:|:---------------------------------------------------------------:|
| async_tree_eager_tg              | 182 ms                                                          | 58.6 ms: 3.11x faster                                           |
| argparse_many_optionals          | 34.4 ms                                                         | 12.8 ms: 2.68x faster                                           |
| argparse_subparsers              | 686 us                                                          | 452 us: 1.52x faster                                            |
| async_tree_eager_memoization_tg  | 236 ms                                                          | 175 ms: 1.35x faster                                            |
| async_tree_eager_cpu_io_mixed_tg | 363 ms                                                          | 285 ms: 1.27x faster                                            |
| create_gc_cycles                 | 1.96 ms                                                         | 1.75 ms: 1.12x faster                                           |
| thread_mandelbrot_optimized      | 233 ms                                                          | 208 ms: 1.12x faster                                            |
| thread_mandelbrot_naive          | 233 ms                                                          | 210 ms: 1.11x faster                                            |
| pickle                           | 8.20 us                                                         | 7.44 us: 1.10x faster                                           |
| base64_large                     | 3.63 ms                                                         | 3.33 ms: 1.09x faster                                           |
| thread_accumulate_optimized      | 35.1 ms                                                         | 32.3 ms: 1.08x faster                                           |
| json_loads                       | 17.5 us                                                         | 16.2 us: 1.08x faster                                           |
| thread_pipeline_optimized        | 22.5 ms                                                         | 20.9 ms: 1.08x faster                                           |
| pickle_pure_python               | 240 us                                                          | 223 us: 1.07x faster                                            |
| logging_silent                   | 65.3 ns                                                         | 61.0 ns: 1.07x faster                                           |
| thread_accumulate_naive          | 35.8 ms                                                         | 33.4 ms: 1.07x faster                                           |
| crypto_pyaes                     | 54.5 ms                                                         | 50.9 ms: 1.07x faster                                           |
| gc_traversal                     | 3.26 ms                                                         | 3.07 ms: 1.06x faster                                           |
| nqueens                          | 56.8 ms                                                         | 53.6 ms: 1.06x faster                                           |
| base64_small                     | 186 us                                                          | 177 us: 1.05x faster                                            |
| thread_memo_optimized            | 15.9 ms                                                         | 15.3 ms: 1.04x faster                                           |
| mypy2                            | 753 ms                                                          | 724 ms: 1.04x faster                                            |
| thread_counter_optimized         | 17.1 ms                                                         | 16.5 ms: 1.03x faster                                           |
| mako                             | 7.40 ms                                                         | 7.16 ms: 1.03x faster                                           |
| pickle_list                      | 3.24 us                                                         | 3.14 us: 1.03x faster                                           |
| docutils                         | 1.95 sec                                                        | 1.89 sec: 1.03x faster                                          |
| nbody                            | 67.9 ms                                                         | 65.9 ms: 1.03x faster                                           |
| coverage                         | 57.4 ms                                                         | 55.8 ms: 1.03x faster                                           |
| networkx_connected_components    | 438 ms                                                          | 425 ms: 1.03x faster                                            |
| unpickle_list                    | 3.43 us                                                         | 3.33 us: 1.03x faster                                           |
| python_startup                   | 9.73 ms                                                         | 9.51 ms: 1.02x faster                                           |
| asyncio_tcp                      | 325 ms                                                          | 318 ms: 1.02x faster                                            |
| base85_small                     | 4.69 ms                                                         | 4.59 ms: 1.02x faster                                           |
| sqlalchemy_imperative            | 14.2 ms                                                         | 13.9 ms: 1.02x faster                                           |
| logging_format                   | 5.35 us                                                         | 5.25 us: 1.02x faster                                           |
| networkx_shortest_path           | 444 ms                                                          | 437 ms: 1.02x faster                                            |
| logging_simple                   | 4.79 us                                                         | 4.71 us: 1.02x faster                                           |
| pathlib                          | 13.0 ms                                                         | 12.8 ms: 1.02x faster                                           |
| scimark_sparse_mat_mult          | 3.18 ms                                                         | 3.14 ms: 1.01x faster                                           |
| urlsafe_base64_small             | 329 us                                                          | 325 us: 1.01x faster                                            |
| django_template                  | 27.8 ms                                                         | 27.6 ms: 1.01x faster                                           |
| unpickle_pure_python             | 152 us                                                          | 151 us: 1.01x faster                                            |
| pidigits                         | 189 ms                                                          | 189 ms: 1.00x faster                                            |
| asyncio_tcp_ssl                  | 1.28 sec                                                        | 1.29 sec: 1.00x slower                                          |
| meteor_contest                   | 84.1 ms                                                         | 84.4 ms: 1.00x slower                                           |
| spectral_norm                    | 65.6 ms                                                         | 65.9 ms: 1.00x slower                                           |
| raytrace                         | 194 ms                                                          | 195 ms: 1.01x slower                                            |
| scimark_lu                       | 73.8 ms                                                         | 74.5 ms: 1.01x slower                                           |
| fastapi_http                     | 216 ms                                                          | 218 ms: 1.01x slower                                            |
| pycparser                        | 851 ms                                                          | 860 ms: 1.01x slower                                            |
| typing_runtime_protocols         | 112 us                                                          | 113 us: 1.01x slower                                            |
| base32_large                     | 292 ms                                                          | 296 ms: 1.01x slower                                            |
| comprehensions                   | 10.8 us                                                         | 10.9 us: 1.01x slower                                           |
| python_startup_no_site           | 6.38 ms                                                         | 6.46 ms: 1.01x slower                                           |
| sympy_expand                     | 332 ms                                                          | 336 ms: 1.01x slower                                            |
| sympy_str                        | 194 ms                                                          | 197 ms: 1.02x slower                                            |
| base32_small                     | 5.71 ms                                                         | 5.79 ms: 1.02x slower                                           |
| coroutines                       | 15.1 ms                                                         | 15.4 ms: 1.02x slower                                           |
| base85_large                     | 248 ms                                                          | 252 ms: 1.02x slower                                            |
| thread_counter_naive             | 20.2 ms                                                         | 20.6 ms: 1.02x slower                                           |
| pickle_dict                      | 21.5 us                                                         | 22.0 us: 1.02x slower                                           |
| decimal_factorial                | 173 ms                                                          | 177 ms: 1.02x slower                                            |
| json                             | 3.42 ms                                                         | 3.51 ms: 1.02x slower                                           |
| xml_etree_generate               | 62.6 ms                                                         | 64.2 ms: 1.02x slower                                           |
| asyncio_websockets               | 296 ms                                                          | 303 ms: 1.02x slower                                            |
| regex_v8                         | 14.8 ms                                                         | 15.2 ms: 1.03x slower                                           |
| sqlglot_v2_optimize              | 39.0 ms                                                         | 40.1 ms: 1.03x slower                                           |
| sympy_integrate                  | 15.4 ms                                                         | 15.8 ms: 1.03x slower                                           |
| sqlglot_v2_normalize             | 78.2 ms                                                         | 80.5 ms: 1.03x slower                                           |
| async_tree_eager_cpu_io_mixed    | 314 ms                                                          | 323 ms: 1.03x slower                                            |
| deltablue                        | 2.34 ms                                                         | 2.41 ms: 1.03x slower                                           |
| chaos                            | 43.8 ms                                                         | 45.1 ms: 1.03x slower                                           |
| unpickle                         | 10.2 us                                                         | 10.5 us: 1.03x slower                                           |
| xml_etree_process                | 44.7 ms                                                         | 46.6 ms: 1.04x slower                                           |
| scimark_sor                      | 75.7 ms                                                         | 78.9 ms: 1.04x slower                                           |
| networkx_k_core                  | 2.07 sec                                                        | 2.16 sec: 1.04x slower                                          |
| telco                            | 5.59 ms                                                         | 5.83 ms: 1.04x slower                                           |
| thread_montecarlo_optimized      | 13.9 ms                                                         | 14.5 ms: 1.04x slower                                           |
| generators                       | 20.3 ms                                                         | 21.2 ms: 1.04x slower                                           |
| chameleon                        | 9.52 ms                                                         | 9.95 ms: 1.05x slower                                           |
| genshi_xml                       | 39.5 ms                                                         | 41.3 ms: 1.05x slower                                           |
| hexiom                           | 4.11 ms                                                         | 4.30 ms: 1.05x slower                                           |
| sqlglot_v2_transpile             | 1.15 ms                                                         | 1.20 ms: 1.05x slower                                           |
| regex_compile                    | 93.9 ms                                                         | 98.5 ms: 1.05x slower                                           |
| xml_etree_iterparse              | 76.2 ms                                                         | 79.9 ms: 1.05x slower                                           |
| quadtree_nbody                   | 596 ms                                                          | 626 ms: 1.05x slower                                            |
| pylint                           | 216 ms                                                          | 227 ms: 1.05x slower                                            |
| sqlglot_v2_parse                 | 911 us                                                          | 958 us: 1.05x slower                                            |
| unpack_sequence                  | 25.8 ns                                                         | 27.1 ns: 1.05x slower                                           |
| async_generators                 | 228 ms                                                          | 240 ms: 1.05x slower                                            |
| xdsl_constant_fold               | 34.7 ms                                                         | 36.7 ms: 1.06x slower                                           |
| noop                             | 19.4 ns                                                         | 20.5 ns: 1.06x slower                                           |
| genshi_text                      | 16.8 ms                                                         | 17.8 ms: 1.06x slower                                           |
| decimal_pi                       | 208 ms                                                          | 222 ms: 1.07x slower                                            |
| ascii85_small                    | 12.7 ms                                                         | 13.6 ms: 1.07x slower                                           |
| ascii85_large                    | 667 ms                                                          | 717 ms: 1.07x slower                                            |
| regex_dna                        | 150 ms                                                          | 162 ms: 1.08x slower                                            |
| thrift                           | 1.86 ms                                                         | 2.02 ms: 1.08x slower                                           |
| bpe_tokeniser                    | 3.00 sec                                                        | 3.30 sec: 1.10x slower                                          |
| async_tree_eager                 | 81.3 ms                                                         | 89.6 ms: 1.10x slower                                           |
| html5lib                         | 46.9 ms                                                         | 51.7 ms: 1.10x slower                                           |
| pprint_pformat                   | 989 ms                                                          | 1.09 sec: 1.10x slower                                          |
| xml_etree_parse                  | 94.3 ms                                                         | 104 ms: 1.11x slower                                            |
| pprint_safe_repr                 | 474 ms                                                          | 530 ms: 1.12x slower                                            |
| tomli_loads                      | 1.44 sec                                                        | 1.62 sec: 1.12x slower                                          |
| pyflate                          | 299 ms                                                          | 342 ms: 1.14x slower                                            |
| scimark_monte_carlo              | 40.7 ms                                                         | 46.5 ms: 1.14x slower                                           |
| richards_super                   | 37.4 ms                                                         | 42.8 ms: 1.15x slower                                           |
| richards                         | 32.6 ms                                                         | 37.8 ms: 1.16x slower                                           |
| async_tree_cpu_io_mixed          | 407 ms                                                          | 474 ms: 1.16x slower                                            |
| regex_effbot                     | 1.95 ms                                                         | 2.30 ms: 1.18x slower                                           |
| async_tree_cpu_io_mixed_tg       | 410 ms                                                          | 490 ms: 1.19x slower                                            |
| deepcopy_reduce                  | 2.00 us                                                         | 2.40 us: 1.20x slower                                           |
| thread_montecarlo_naive          | 15.8 ms                                                         | 19.0 ms: 1.21x slower                                           |
| float                            | 47.3 ms                                                         | 57.0 ms: 1.21x slower                                           |
| async_tree_eager_memoization     | 180 ms                                                          | 219 ms: 1.22x slower                                            |
| async_tree_none_tg               | 223 ms                                                          | 291 ms: 1.30x slower                                            |
| async_tree_eager_io_tg           | 550 ms                                                          | 728 ms: 1.32x slower                                            |
| async_tree_none                  | 228 ms                                                          | 308 ms: 1.35x slower                                            |
| async_tree_eager_io              | 552 ms                                                          | 749 ms: 1.36x slower                                            |
| async_tree_memoization           | 281 ms                                                          | 388 ms: 1.38x slower                                            |
| go                               | 84.7 ms                                                         | 117 ms: 1.38x slower                                            |
| async_tree_io                    | 531 ms                                                          | 741 ms: 1.40x slower                                            |
| deepcopy                         | 193 us                                                          | 269 us: 1.40x slower                                            |
| async_tree_io_tg                 | 539 ms                                                          | 778 ms: 1.44x slower                                            |
| deepcopy_memo                    | 18.0 us                                                         | 26.5 us: 1.47x slower                                           |
| thread_pipeline_naive            | 32.0 ms                                                         | 47.3 ms: 1.48x slower                                           |
| async_tree_memoization_tg        | 277 ms                                                          | 419 ms: 1.51x slower                                            |
| mdp                              | 946 ms                                                          | 2.15 sec: 2.27x slower                                          |
| base16_small                     | 305 us                                                          | 740 us: 2.42x slower                                            |
| thread_memo_naive                | 11.5 ms                                                         | 36.1 ms: 3.13x slower                                           |
| base16_large                     | 5.33 ms                                                         | 37.0 ms: 6.94x slower                                           |
| Geometric mean                   | (ref)                                                           | 1.06x slower                                                    |

Benchmark hidden because not significant (5): tornado_http, json_dumps, scimark_fft, sympy_sum, fannkuch

- Geometric mean (including insignificant results): 1.059x slower

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.01x
- 95% likely to have a slowdown of 1.01x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 0.94x