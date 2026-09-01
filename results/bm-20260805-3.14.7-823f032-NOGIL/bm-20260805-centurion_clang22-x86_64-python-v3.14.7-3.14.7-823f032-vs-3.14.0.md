# Results vs. 3.14.0

- fork: python
- ref: v3.14.7
- machine: linux-x86_64
- commit hash: 823f032
- commit date: 2026-08-05
- overall geometric mean: 1.046x faster
- HPT reliability: 99.99%
- HPT 99th percentile: 1.01x slower
- Memory change: 1.44x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 11.5 ms: 1.12x slower                                              |
| docutils       | 1.98 sec                                                           | 2.01 sec: 1.01x slower                                             |
| fastapi_http   | 222 ms                                                             | 195 ms: 1.14x faster                                               |
| html5lib       | 45.3 ms                                                            | 46.0 ms: 1.02x slower                                              |
| tornado_http   | 101 ms                                                             | 96.7 ms: 1.04x faster                                              |
| Geometric mean | (ref)                                                              | 1.01x faster                                                       |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 565 ms                                                             | 479 ms: 1.18x faster                                               |
| async_tree_eager_io              | 568 ms                                                             | 509 ms: 1.12x faster                                               |
| async_tree_io_tg                 | 545 ms                                                             | 497 ms: 1.10x faster                                               |
| async_tree_none_tg               | 224 ms                                                             | 209 ms: 1.07x faster                                               |
| asyncio_tcp                      | 324 ms                                                             | 303 ms: 1.07x faster                                               |
| asyncio_websockets               | 305 ms                                                             | 289 ms: 1.05x faster                                               |
| async_tree_io                    | 549 ms                                                             | 530 ms: 1.04x faster                                               |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 413 ms: 1.03x faster                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 271 ms: 1.03x faster                                               |
| async_tree_none                  | 233 ms                                                             | 236 ms: 1.01x slower                                               |
| coroutines                       | 15.1 ms                                                            | 15.4 ms: 1.02x slower                                              |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 338 ms: 1.03x slower                                               |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 445 ms: 1.04x slower                                               |
| async_tree_eager_memoization     | 183 ms                                                             | 192 ms: 1.05x slower                                               |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 397 ms: 1.06x slower                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 251 ms: 1.06x slower                                               |
| async_tree_memoization           | 285 ms                                                             | 304 ms: 1.07x slower                                               |
| async_generators                 | 231 ms                                                             | 248 ms: 1.07x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.39 sec: 1.08x slower                                             |
| async_tree_eager                 | 83.0 ms                                                            | 97.3 ms: 1.17x slower                                              |
| Geometric mean                   | (ref)                                                              | 1.00x faster                                                       |

Benchmark hidden because not significant (1): async_tree_eager_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 21.5 ns: 1.12x slower                                              |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 188 ms: 1.08x slower                                               |
| decimal_pi        | 209 ms                                                             | 247 ms: 1.18x slower                                               |
| Geometric mean    | (ref)                                                              | 1.13x slower                                                       |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 215 ms: 1.01x faster                                               |
| quadtree_nbody | 654 ms                                                             | 684 ms: 1.05x slower                                               |
| float          | 51.2 ms                                                            | 55.0 ms: 1.08x slower                                              |
| nbody          | 74.2 ms                                                            | 83.3 ms: 1.12x slower                                              |
| Geometric mean | (ref)                                                              | 1.06x slower                                                       |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                            | 14.1 ms: 1.07x faster                                              |
| regex_dna      | 147 ms                                                             | 149 ms: 1.01x slower                                               |
| regex_effbot   | 1.98 ms                                                            | 2.04 ms: 1.03x slower                                              |
| regex_compile  | 97.0 ms                                                            | 107 ms: 1.10x slower                                               |
| Geometric mean | (ref)                                                              | 1.02x slower                                                       |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| xml_etree_iterparse  | 85.5 ms                                                            | 68.6 ms: 1.25x faster                                              |
| base16_small         | 265 us                                                             | 245 us: 1.08x faster                                               |
| xml_etree_parse      | 118 ms                                                             | 112 ms: 1.05x faster                                               |
| base64_small         | 227 us                                                             | 216 us: 1.05x faster                                               |
| base16_large         | 6.35 ms                                                            | 6.09 ms: 1.04x faster                                              |
| pickle               | 8.04 us                                                            | 7.76 us: 1.04x faster                                              |
| urlsafe_base64_small | 340 us                                                             | 331 us: 1.03x faster                                               |
| pickle_dict          | 20.0 us                                                            | 19.6 us: 1.02x faster                                              |
| json_dumps           | 7.52 ms                                                            | 7.47 ms: 1.01x faster                                              |
| base64_large         | 5.70 ms                                                            | 5.69 ms: 1.00x faster                                              |
| unpickle_pure_python | 163 us                                                             | 165 us: 1.01x slower                                               |
| unpickle             | 10.5 us                                                            | 10.7 us: 1.02x slower                                              |
| xml_etree_process    | 50.0 ms                                                            | 51.0 ms: 1.02x slower                                              |
| xml_etree_generate   | 68.1 ms                                                            | 69.7 ms: 1.02x slower                                              |
| tomli_loads          | 1.49 sec                                                           | 1.53 sec: 1.03x slower                                             |
| pickle_pure_python   | 251 us                                                             | 259 us: 1.03x slower                                               |
| base85_large         | 249 ms                                                             | 259 ms: 1.04x slower                                               |
| base85_small         | 4.66 ms                                                            | 4.93 ms: 1.06x slower                                              |
| base32_large         | 289 ms                                                             | 306 ms: 1.06x slower                                               |
| base32_small         | 5.71 ms                                                            | 6.05 ms: 1.06x slower                                              |
| pickle_list          | 3.03 us                                                            | 3.27 us: 1.08x slower                                              |
| unpickle_list        | 3.03 us                                                            | 3.30 us: 1.09x slower                                              |
| ascii85_small        | 13.0 ms                                                            | 14.4 ms: 1.10x slower                                              |
| ascii85_large        | 681 ms                                                             | 753 ms: 1.11x slower                                               |
| json_loads           | 18.6 us                                                            | 20.7 us: 1.11x slower                                              |
| Geometric mean       | (ref)                                                              | 1.01x slower                                                       |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 11.7 ms: 1.18x slower                                              |
| python_startup_no_site | 6.52 ms                                                            | 8.20 ms: 1.26x slower                                              |
| Geometric mean         | (ref)                                                              | 1.22x slower                                                       |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| genshi_xml      | 43.2 ms                                                            | 45.7 ms: 1.06x slower                                              |
| django_template | 30.5 ms                                                            | 33.3 ms: 1.09x slower                                              |
| genshi_text     | 18.0 ms                                                            | 20.2 ms: 1.12x slower                                              |
| mako            | 8.69 ms                                                            | 11.2 ms: 1.29x slower                                              |
| Geometric mean  | (ref)                                                              | 1.14x slower                                                       |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|-----------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| thread_pipeline_optimized   | 25.8 ms                                                            | 6.45 ms: 4.00x faster                                              |
| thread_accumulate_optimized | 39.5 ms                                                            | 10.2 ms: 3.87x faster                                              |
| thread_mandelbrot_naive     | 207 ms                                                             | 54.1 ms: 3.82x faster                                              |
| thread_mandelbrot_optimized | 205 ms                                                             | 54.5 ms: 3.77x faster                                              |
| thread_counter_optimized    | 18.3 ms                                                            | 5.05 ms: 3.63x faster                                              |
| thread_memo_optimized       | 17.5 ms                                                            | 5.53 ms: 3.17x faster                                              |
| thread_accumulate_naive     | 40.4 ms                                                            | 12.9 ms: 3.14x faster                                              |
| thread_montecarlo_optimized | 12.9 ms                                                            | 4.36 ms: 2.96x faster                                              |
| thread_pipeline_naive       | 34.9 ms                                                            | 26.3 ms: 1.33x faster                                              |
| thread_counter_naive        | 21.2 ms                                                            | 20.3 ms: 1.04x faster                                              |
| thread_montecarlo_naive     | 14.3 ms                                                            | 25.5 ms: 1.79x slower                                              |
| thread_memo_naive           | 12.4 ms                                                            | 22.9 ms: 1.85x slower                                              |
| Geometric mean              | (ref)                                                              | 2.15x faster                                                       |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260805-centurion_clang22-x86_64-python-v3.14.7-3.14.7-823f032 |
|----------------------------------|:------------------------------------------------------------------:|:------------------------------------------------------------------:|
| argparse_many_optionals          | 34.5 ms                                                            | 8.45 ms: 4.08x faster                                              |
| thread_pipeline_optimized        | 25.8 ms                                                            | 6.45 ms: 4.00x faster                                              |
| thread_accumulate_optimized      | 39.5 ms                                                            | 10.2 ms: 3.87x faster                                              |
| thread_mandelbrot_naive          | 207 ms                                                             | 54.1 ms: 3.82x faster                                              |
| thread_mandelbrot_optimized      | 205 ms                                                             | 54.5 ms: 3.77x faster                                              |
| thread_counter_optimized         | 18.3 ms                                                            | 5.05 ms: 3.63x faster                                              |
| thread_memo_optimized            | 17.5 ms                                                            | 5.53 ms: 3.17x faster                                              |
| thread_accumulate_naive          | 40.4 ms                                                            | 12.9 ms: 3.14x faster                                              |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 4.36 ms: 2.96x faster                                              |
| gc_traversal                     | 3.36 ms                                                            | 1.55 ms: 2.16x faster                                              |
| create_gc_cycles                 | 2.02 ms                                                            | 1.23 ms: 1.64x faster                                              |
| thread_pipeline_naive            | 34.9 ms                                                            | 26.3 ms: 1.33x faster                                              |
| argparse_subparsers              | 687 us                                                             | 528 us: 1.30x faster                                               |
| xml_etree_iterparse              | 85.5 ms                                                            | 68.6 ms: 1.25x faster                                              |
| async_tree_eager_io_tg           | 565 ms                                                             | 479 ms: 1.18x faster                                               |
| fastapi_http                     | 222 ms                                                             | 195 ms: 1.14x faster                                               |
| async_tree_eager_io              | 568 ms                                                             | 509 ms: 1.12x faster                                               |
| async_tree_io_tg                 | 545 ms                                                             | 497 ms: 1.10x faster                                               |
| base16_small                     | 265 us                                                             | 245 us: 1.08x faster                                               |
| async_tree_none_tg               | 224 ms                                                             | 209 ms: 1.07x faster                                               |
| asyncio_tcp                      | 324 ms                                                             | 303 ms: 1.07x faster                                               |
| regex_v8                         | 15.0 ms                                                            | 14.1 ms: 1.07x faster                                              |
| asyncio_websockets               | 305 ms                                                             | 289 ms: 1.05x faster                                               |
| xml_etree_parse                  | 118 ms                                                             | 112 ms: 1.05x faster                                               |
| base64_small                     | 227 us                                                             | 216 us: 1.05x faster                                               |
| tornado_http                     | 101 ms                                                             | 96.7 ms: 1.04x faster                                              |
| base16_large                     | 6.35 ms                                                            | 6.09 ms: 1.04x faster                                              |
| thread_counter_naive             | 21.2 ms                                                            | 20.3 ms: 1.04x faster                                              |
| async_tree_io                    | 549 ms                                                             | 530 ms: 1.04x faster                                               |
| pickle                           | 8.04 us                                                            | 7.76 us: 1.04x faster                                              |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 413 ms: 1.03x faster                                               |
| async_tree_memoization_tg        | 279 ms                                                             | 271 ms: 1.03x faster                                               |
| urlsafe_base64_small             | 340 us                                                             | 331 us: 1.03x faster                                               |
| generators                       | 24.2 ms                                                            | 23.6 ms: 1.02x faster                                              |
| pickle_dict                      | 20.0 us                                                            | 19.6 us: 1.02x faster                                              |
| pidigits                         | 216 ms                                                             | 215 ms: 1.01x faster                                               |
| json_dumps                       | 7.52 ms                                                            | 7.47 ms: 1.01x faster                                              |
| base64_large                     | 5.70 ms                                                            | 5.69 ms: 1.00x faster                                              |
| regex_dna                        | 147 ms                                                             | 149 ms: 1.01x slower                                               |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 42.2 ms: 1.01x slower                                              |
| async_tree_none                  | 233 ms                                                             | 236 ms: 1.01x slower                                               |
| unpickle_pure_python             | 163 us                                                             | 165 us: 1.01x slower                                               |
| docutils                         | 1.98 sec                                                           | 2.01 sec: 1.01x slower                                             |
| html5lib                         | 45.3 ms                                                            | 46.0 ms: 1.02x slower                                              |
| coroutines                       | 15.1 ms                                                            | 15.4 ms: 1.02x slower                                              |
| unpickle                         | 10.5 us                                                            | 10.7 us: 1.02x slower                                              |
| xml_etree_process                | 50.0 ms                                                            | 51.0 ms: 1.02x slower                                              |
| xml_etree_generate               | 68.1 ms                                                            | 69.7 ms: 1.02x slower                                              |
| logging_format                   | 6.00 us                                                            | 6.15 us: 1.02x slower                                              |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.19 sec: 1.03x slower                                             |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 87.0 ms: 1.03x slower                                              |
| tomli_loads                      | 1.49 sec                                                           | 1.53 sec: 1.03x slower                                             |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 338 ms: 1.03x slower                                               |
| regex_effbot                     | 1.98 ms                                                            | 2.04 ms: 1.03x slower                                              |
| pickle_pure_python               | 251 us                                                             | 259 us: 1.03x slower                                               |
| mypy2                            | 780 ms                                                             | 808 ms: 1.04x slower                                               |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 445 ms: 1.04x slower                                               |
| base85_large                     | 249 ms                                                             | 259 ms: 1.04x slower                                               |
| json                             | 3.46 ms                                                            | 3.62 ms: 1.04x slower                                              |
| quadtree_nbody                   | 654 ms                                                             | 684 ms: 1.05x slower                                               |
| async_tree_eager_memoization     | 183 ms                                                             | 192 ms: 1.05x slower                                               |
| thrift                           | 2.00 ms                                                            | 2.10 ms: 1.05x slower                                              |
| networkx_k_core                  | 2.05 sec                                                           | 2.15 sec: 1.05x slower                                             |
| scimark_fft                      | 211 ms                                                             | 222 ms: 1.05x slower                                               |
| mdp                              | 971 ms                                                             | 1.03 sec: 1.06x slower                                             |
| base85_small                     | 4.66 ms                                                            | 4.93 ms: 1.06x slower                                              |
| networkx_connected_components    | 425 ms                                                             | 449 ms: 1.06x slower                                               |
| genshi_xml                       | 43.2 ms                                                            | 45.7 ms: 1.06x slower                                              |
| base32_large                     | 289 ms                                                             | 306 ms: 1.06x slower                                               |
| networkx_shortest_path           | 447 ms                                                             | 473 ms: 1.06x slower                                               |
| sympy_sum                        | 109 ms                                                             | 115 ms: 1.06x slower                                               |
| nqueens                          | 59.8 ms                                                            | 63.4 ms: 1.06x slower                                              |
| base32_small                     | 5.71 ms                                                            | 6.05 ms: 1.06x slower                                              |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 397 ms: 1.06x slower                                               |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 251 ms: 1.06x slower                                               |
| chaos                            | 42.9 ms                                                            | 45.8 ms: 1.07x slower                                              |
| async_tree_memoization           | 285 ms                                                             | 304 ms: 1.07x slower                                               |
| scimark_sor                      | 78.2 ms                                                            | 83.5 ms: 1.07x slower                                              |
| spectral_norm                    | 64.1 ms                                                            | 68.7 ms: 1.07x slower                                              |
| go                               | 91.1 ms                                                            | 97.7 ms: 1.07x slower                                              |
| telco                            | 5.39 ms                                                            | 5.79 ms: 1.07x slower                                              |
| sympy_str                        | 200 ms                                                             | 215 ms: 1.07x slower                                               |
| async_generators                 | 231 ms                                                             | 248 ms: 1.07x slower                                               |
| float                            | 51.2 ms                                                            | 55.0 ms: 1.08x slower                                              |
| sqlalchemy_imperative            | 14.8 ms                                                            | 15.9 ms: 1.08x slower                                              |
| decimal_factorial                | 174 ms                                                             | 188 ms: 1.08x slower                                               |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.39 sec: 1.08x slower                                             |
| deltablue                        | 2.76 ms                                                            | 2.97 ms: 1.08x slower                                              |
| pickle_list                      | 3.03 us                                                            | 3.27 us: 1.08x slower                                              |
| sympy_expand                     | 344 ms                                                             | 372 ms: 1.08x slower                                               |
| sympy_integrate                  | 15.1 ms                                                            | 16.4 ms: 1.08x slower                                              |
| logging_simple                   | 5.02 us                                                            | 5.44 us: 1.08x slower                                              |
| unpickle_list                    | 3.03 us                                                            | 3.30 us: 1.09x slower                                              |
| pyflate                          | 309 ms                                                             | 337 ms: 1.09x slower                                               |
| pprint_safe_repr                 | 534 ms                                                             | 583 ms: 1.09x slower                                               |
| django_template                  | 30.5 ms                                                            | 33.3 ms: 1.09x slower                                              |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.33 ms: 1.10x slower                                              |
| regex_compile                    | 97.0 ms                                                            | 107 ms: 1.10x slower                                               |
| ascii85_small                    | 13.0 ms                                                            | 14.4 ms: 1.10x slower                                              |
| xdsl_constant_fold               | 36.0 ms                                                            | 39.7 ms: 1.10x slower                                              |
| hexiom                           | 4.50 ms                                                            | 4.96 ms: 1.10x slower                                              |
| raytrace                         | 201 ms                                                             | 222 ms: 1.10x slower                                               |
| ascii85_large                    | 681 ms                                                             | 753 ms: 1.11x slower                                               |
| logging_silent                   | 59.2 ns                                                            | 65.7 ns: 1.11x slower                                              |
| json_loads                       | 18.6 us                                                            | 20.7 us: 1.11x slower                                              |
| comprehensions                   | 11.4 us                                                            | 12.7 us: 1.11x slower                                              |
| crypto_pyaes                     | 56.7 ms                                                            | 63.1 ms: 1.11x slower                                              |
| pprint_pformat                   | 1.10 sec                                                           | 1.22 sec: 1.12x slower                                             |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 3.22 ms: 1.12x slower                                              |
| chameleon                        | 10.3 ms                                                            | 11.5 ms: 1.12x slower                                              |
| noop                             | 19.2 ns                                                            | 21.5 ns: 1.12x slower                                              |
| nbody                            | 74.2 ms                                                            | 83.3 ms: 1.12x slower                                              |
| genshi_text                      | 18.0 ms                                                            | 20.2 ms: 1.12x slower                                              |
| richards_super                   | 40.3 ms                                                            | 45.4 ms: 1.12x slower                                              |
| scimark_monte_carlo              | 42.3 ms                                                            | 47.8 ms: 1.13x slower                                              |
| meteor_contest                   | 85.4 ms                                                            | 96.6 ms: 1.13x slower                                              |
| richards                         | 34.7 ms                                                            | 39.3 ms: 1.13x slower                                              |
| typing_runtime_protocols         | 115 us                                                             | 130 us: 1.13x slower                                               |
| deepcopy                         | 198 us                                                             | 225 us: 1.14x slower                                               |
| scimark_lu                       | 74.7 ms                                                            | 85.9 ms: 1.15x slower                                              |
| deepcopy_reduce                  | 2.02 us                                                            | 2.33 us: 1.15x slower                                              |
| sqlglot_v2_parse                 | 954 us                                                             | 1.11 ms: 1.16x slower                                              |
| fannkuch                         | 246 ms                                                             | 287 ms: 1.16x slower                                               |
| async_tree_eager                 | 83.0 ms                                                            | 97.3 ms: 1.17x slower                                              |
| python_startup                   | 9.93 ms                                                            | 11.7 ms: 1.18x slower                                              |
| decimal_pi                       | 209 ms                                                             | 247 ms: 1.18x slower                                               |
| deepcopy_memo                    | 19.1 us                                                            | 23.3 us: 1.22x slower                                              |
| python_startup_no_site           | 6.52 ms                                                            | 8.20 ms: 1.26x slower                                              |
| coverage                         | 54.5 ms                                                            | 69.8 ms: 1.28x slower                                              |
| mako                             | 8.69 ms                                                            | 11.2 ms: 1.29x slower                                              |
| thread_montecarlo_naive          | 14.3 ms                                                            | 25.5 ms: 1.79x slower                                              |
| thread_memo_naive                | 12.4 ms                                                            | 22.9 ms: 1.85x slower                                              |
| Geometric mean                   | (ref)                                                              | 1.05x faster                                                       |

Benchmark hidden because not significant (5): unpack_sequence, pycparser, pathlib, async_tree_eager_tg, pylint

- Geometric mean (including insignificant results): 1.046x faster

# HPT report

- Reliability score: 99.99% likely to be slow
- 90% likely to have a slowdown of 1.02x
- 95% likely to have a slowdown of 1.02x
- 99% likely to have a slowdown of 1.01x

# Memory
- memory change: 1.44x