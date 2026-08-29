# Results vs. 3.14.0

- fork: python
- ref: v3.15.0a4
- machine: linux-x86_64
- commit hash: 43cd277
- commit date: 2026-01-13
- overall geometric mean: 1.001x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.05x slower
- Memory change: 1.46x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.3 ms                                                            | 12.3 ms: 1.20x slower                                                  |
| docutils       | 1.98 sec                                                           | 2.18 sec: 1.10x slower                                                 |
| fastapi_http   | 222 ms                                                             | 204 ms: 1.09x faster                                                   |
| html5lib       | 45.3 ms                                                            | 49.8 ms: 1.10x slower                                                  |
| tornado_http   | 101 ms                                                             | 98.9 ms: 1.02x faster                                                  |
| Geometric mean | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_eager_io_tg           | 565 ms                                                             | 490 ms: 1.15x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 281 ms: 1.15x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 503 ms: 1.08x faster                                                   |
| async_tree_eager_io              | 568 ms                                                             | 534 ms: 1.06x faster                                                   |
| asyncio_websockets               | 305 ms                                                             | 288 ms: 1.06x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 217 ms: 1.03x faster                                                   |
| async_tree_io                    | 549 ms                                                             | 539 ms: 1.02x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 422 ms: 1.01x faster                                                   |
| async_tree_eager_tg              | 182 ms                                                             | 190 ms: 1.04x slower                                                   |
| async_tree_none                  | 233 ms                                                             | 243 ms: 1.04x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 343 ms: 1.05x slower                                                   |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 451 ms: 1.05x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.36 sec: 1.05x slower                                                 |
| async_tree_eager_memoization     | 183 ms                                                             | 195 ms: 1.07x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 405 ms: 1.08x slower                                                   |
| coroutines                       | 15.1 ms                                                            | 16.6 ms: 1.10x slower                                                  |
| async_tree_memoization           | 285 ms                                                             | 314 ms: 1.10x slower                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 264 ms: 1.12x slower                                                   |
| async_generators                 | 231 ms                                                             | 258 ms: 1.12x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 100 ms: 1.21x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.02x slower                                                           |

Benchmark hidden because not significant (1): async_tree_memoization_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 19.2 ns                                                            | 22.8 ns: 1.19x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 174 ms                                                             | 188 ms: 1.08x slower                                                   |
| decimal_pi        | 209 ms                                                             | 240 ms: 1.15x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.11x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 216 ms: 1.00x faster                                                   |
| float          | 51.2 ms                                                            | 57.4 ms: 1.12x slower                                                  |
| quadtree_nbody | 654 ms                                                             | 753 ms: 1.15x slower                                                   |
| nbody          | 74.2 ms                                                            | 89.8 ms: 1.21x slower                                                  |
| Geometric mean | (ref)                                                              | 1.12x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                            | 14.7 ms: 1.02x faster                                                  |
| regex_dna      | 147 ms                                                             | 145 ms: 1.01x faster                                                   |
| regex_effbot   | 1.98 ms                                                            | 2.00 ms: 1.01x slower                                                  |
| regex_compile  | 97.0 ms                                                            | 115 ms: 1.19x slower                                                   |
| Geometric mean | (ref)                                                              | 1.04x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| xml_etree_iterparse  | 85.5 ms                                                            | 74.4 ms: 1.15x faster                                                  |
| base16_large         | 6.35 ms                                                            | 5.97 ms: 1.06x faster                                                  |
| pickle_list          | 3.03 us                                                            | 2.86 us: 1.06x faster                                                  |
| json_dumps           | 7.52 ms                                                            | 7.13 ms: 1.06x faster                                                  |
| pickle_dict          | 20.0 us                                                            | 19.0 us: 1.05x faster                                                  |
| xml_etree_parse      | 118 ms                                                             | 112 ms: 1.05x faster                                                   |
| base64_large         | 5.70 ms                                                            | 5.47 ms: 1.04x faster                                                  |
| pickle               | 8.04 us                                                            | 7.74 us: 1.04x faster                                                  |
| base64_small         | 227 us                                                             | 219 us: 1.04x faster                                                   |
| base16_small         | 265 us                                                             | 263 us: 1.01x faster                                                   |
| json_loads           | 18.6 us                                                            | 18.5 us: 1.00x faster                                                  |
| urlsafe_base64_small | 340 us                                                             | 347 us: 1.02x slower                                                   |
| xml_etree_generate   | 68.1 ms                                                            | 71.6 ms: 1.05x slower                                                  |
| unpickle             | 10.5 us                                                            | 11.1 us: 1.06x slower                                                  |
| xml_etree_process    | 50.0 ms                                                            | 53.3 ms: 1.07x slower                                                  |
| pickle_pure_python   | 251 us                                                             | 282 us: 1.12x slower                                                   |
| unpickle_list        | 3.03 us                                                            | 3.41 us: 1.12x slower                                                  |
| base32_large         | 289 ms                                                             | 330 ms: 1.14x slower                                                   |
| base32_small         | 5.71 ms                                                            | 6.52 ms: 1.14x slower                                                  |
| unpickle_pure_python | 163 us                                                             | 188 us: 1.16x slower                                                   |
| base85_large         | 249 ms                                                             | 295 ms: 1.18x slower                                                   |
| base85_small         | 4.66 ms                                                            | 5.52 ms: 1.18x slower                                                  |
| tomli_loads          | 1.49 sec                                                           | 1.83 sec: 1.23x slower                                                 |
| ascii85_small        | 13.0 ms                                                            | 16.6 ms: 1.27x slower                                                  |
| ascii85_large        | 681 ms                                                             | 883 ms: 1.30x slower                                                   |
| Geometric mean       | (ref)                                                              | 1.06x slower                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.93 ms                                                            | 11.6 ms: 1.17x slower                                                  |
| python_startup_no_site | 6.52 ms                                                            | 8.15 ms: 1.25x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.21x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 30.5 ms                                                            | 35.6 ms: 1.17x slower                                                  |
| genshi_xml      | 43.2 ms                                                            | 50.8 ms: 1.17x slower                                                  |
| genshi_text     | 18.0 ms                                                            | 22.2 ms: 1.23x slower                                                  |
| mako            | 8.69 ms                                                            | 12.1 ms: 1.39x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.24x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 207 ms                                                             | 53.7 ms: 3.85x faster                                                  |
| thread_mandelbrot_optimized | 205 ms                                                             | 53.4 ms: 3.85x faster                                                  |
| thread_pipeline_optimized   | 25.8 ms                                                            | 7.45 ms: 3.46x faster                                                  |
| thread_accumulate_optimized | 39.5 ms                                                            | 11.7 ms: 3.36x faster                                                  |
| thread_counter_optimized    | 18.3 ms                                                            | 6.01 ms: 3.05x faster                                                  |
| thread_accumulate_naive     | 40.4 ms                                                            | 13.6 ms: 2.96x faster                                                  |
| thread_memo_optimized       | 17.5 ms                                                            | 6.04 ms: 2.90x faster                                                  |
| thread_montecarlo_optimized | 12.9 ms                                                            | 4.89 ms: 2.64x faster                                                  |
| thread_pipeline_naive       | 34.9 ms                                                            | 24.8 ms: 1.41x faster                                                  |
| thread_counter_naive        | 21.2 ms                                                            | 21.0 ms: 1.01x faster                                                  |
| thread_memo_naive           | 12.4 ms                                                            | 21.0 ms: 1.69x slower                                                  |
| thread_montecarlo_naive     | 14.3 ms                                                            | 25.7 ms: 1.80x slower                                                  |
| Geometric mean              | (ref)                                                              | 2.05x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_clang22-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260113-centurion_clang22-x86_64-python-v3.15.0a4-3.15.0a4-43cd277 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| argparse_many_optionals          | 34.5 ms                                                            | 8.85 ms: 3.90x faster                                                  |
| thread_mandelbrot_naive          | 207 ms                                                             | 53.7 ms: 3.85x faster                                                  |
| thread_mandelbrot_optimized      | 205 ms                                                             | 53.4 ms: 3.85x faster                                                  |
| thread_pipeline_optimized        | 25.8 ms                                                            | 7.45 ms: 3.46x faster                                                  |
| thread_accumulate_optimized      | 39.5 ms                                                            | 11.7 ms: 3.36x faster                                                  |
| thread_counter_optimized         | 18.3 ms                                                            | 6.01 ms: 3.05x faster                                                  |
| thread_accumulate_naive          | 40.4 ms                                                            | 13.6 ms: 2.96x faster                                                  |
| thread_memo_optimized            | 17.5 ms                                                            | 6.04 ms: 2.90x faster                                                  |
| thread_montecarlo_optimized      | 12.9 ms                                                            | 4.89 ms: 2.64x faster                                                  |
| gc_traversal                     | 3.36 ms                                                            | 1.61 ms: 2.09x faster                                                  |
| create_gc_cycles                 | 2.02 ms                                                            | 1.29 ms: 1.56x faster                                                  |
| thread_pipeline_naive            | 34.9 ms                                                            | 24.8 ms: 1.41x faster                                                  |
| argparse_subparsers              | 687 us                                                             | 541 us: 1.27x faster                                                   |
| pathlib                          | 12.7 ms                                                            | 11.0 ms: 1.15x faster                                                  |
| async_tree_eager_io_tg           | 565 ms                                                             | 490 ms: 1.15x faster                                                   |
| asyncio_tcp                      | 324 ms                                                             | 281 ms: 1.15x faster                                                   |
| xml_etree_iterparse              | 85.5 ms                                                            | 74.4 ms: 1.15x faster                                                  |
| fastapi_http                     | 222 ms                                                             | 204 ms: 1.09x faster                                                   |
| async_tree_io_tg                 | 545 ms                                                             | 503 ms: 1.08x faster                                                   |
| base16_large                     | 6.35 ms                                                            | 5.97 ms: 1.06x faster                                                  |
| async_tree_eager_io              | 568 ms                                                             | 534 ms: 1.06x faster                                                   |
| asyncio_websockets               | 305 ms                                                             | 288 ms: 1.06x faster                                                   |
| pickle_list                      | 3.03 us                                                            | 2.86 us: 1.06x faster                                                  |
| json_dumps                       | 7.52 ms                                                            | 7.13 ms: 1.06x faster                                                  |
| pickle_dict                      | 20.0 us                                                            | 19.0 us: 1.05x faster                                                  |
| xml_etree_parse                  | 118 ms                                                             | 112 ms: 1.05x faster                                                   |
| base64_large                     | 5.70 ms                                                            | 5.47 ms: 1.04x faster                                                  |
| pickle                           | 8.04 us                                                            | 7.74 us: 1.04x faster                                                  |
| base64_small                     | 227 us                                                             | 219 us: 1.04x faster                                                   |
| async_tree_none_tg               | 224 ms                                                             | 217 ms: 1.03x faster                                                   |
| json                             | 3.46 ms                                                            | 3.38 ms: 1.03x faster                                                  |
| regex_v8                         | 15.0 ms                                                            | 14.7 ms: 1.02x faster                                                  |
| tornado_http                     | 101 ms                                                             | 98.9 ms: 1.02x faster                                                  |
| async_tree_io                    | 549 ms                                                             | 539 ms: 1.02x faster                                                   |
| regex_dna                        | 147 ms                                                             | 145 ms: 1.01x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 427 ms                                                             | 422 ms: 1.01x faster                                                   |
| thread_counter_naive             | 21.2 ms                                                            | 21.0 ms: 1.01x faster                                                  |
| base16_small                     | 265 us                                                             | 263 us: 1.01x faster                                                   |
| json_loads                       | 18.6 us                                                            | 18.5 us: 1.00x faster                                                  |
| pidigits                         | 216 ms                                                             | 216 ms: 1.00x faster                                                   |
| regex_effbot                     | 1.98 ms                                                            | 2.00 ms: 1.01x slower                                                  |
| urlsafe_base64_small             | 340 us                                                             | 347 us: 1.02x slower                                                   |
| telco                            | 5.39 ms                                                            | 5.60 ms: 1.04x slower                                                  |
| async_tree_eager_tg              | 182 ms                                                             | 190 ms: 1.04x slower                                                   |
| async_tree_none                  | 233 ms                                                             | 243 ms: 1.04x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 327 ms                                                             | 343 ms: 1.05x slower                                                   |
| pylint                           | 222 ms                                                             | 233 ms: 1.05x slower                                                   |
| xml_etree_generate               | 68.1 ms                                                            | 71.6 ms: 1.05x slower                                                  |
| async_tree_cpu_io_mixed          | 429 ms                                                             | 451 ms: 1.05x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                           | 1.36 sec: 1.05x slower                                                 |
| networkx_k_core                  | 2.05 sec                                                           | 2.16 sec: 1.05x slower                                                 |
| unpickle                         | 10.5 us                                                            | 11.1 us: 1.06x slower                                                  |
| xml_etree_process                | 50.0 ms                                                            | 53.3 ms: 1.07x slower                                                  |
| sqlglot_v2_optimize              | 41.8 ms                                                            | 44.6 ms: 1.07x slower                                                  |
| async_tree_eager_memoization     | 183 ms                                                             | 195 ms: 1.07x slower                                                   |
| scimark_fft                      | 211 ms                                                             | 226 ms: 1.07x slower                                                   |
| bpe_tokeniser                    | 3.11 sec                                                           | 3.35 sec: 1.08x slower                                                 |
| decimal_factorial                | 174 ms                                                             | 188 ms: 1.08x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 374 ms                                                             | 405 ms: 1.08x slower                                                   |
| sympy_sum                        | 109 ms                                                             | 119 ms: 1.09x slower                                                   |
| logging_format                   | 6.00 us                                                            | 6.58 us: 1.10x slower                                                  |
| coroutines                       | 15.1 ms                                                            | 16.6 ms: 1.10x slower                                                  |
| html5lib                         | 45.3 ms                                                            | 49.8 ms: 1.10x slower                                                  |
| async_tree_memoization           | 285 ms                                                             | 314 ms: 1.10x slower                                                   |
| docutils                         | 1.98 sec                                                           | 2.18 sec: 1.10x slower                                                 |
| mypy2                            | 780 ms                                                             | 866 ms: 1.11x slower                                                   |
| async_tree_eager_memoization_tg  | 236 ms                                                             | 264 ms: 1.12x slower                                                   |
| generators                       | 24.2 ms                                                            | 27.0 ms: 1.12x slower                                                  |
| async_generators                 | 231 ms                                                             | 258 ms: 1.12x slower                                                   |
| mdp                              | 971 ms                                                             | 1.09 sec: 1.12x slower                                                 |
| thrift                           | 2.00 ms                                                            | 2.24 ms: 1.12x slower                                                  |
| spectral_norm                    | 64.1 ms                                                            | 71.9 ms: 1.12x slower                                                  |
| float                            | 51.2 ms                                                            | 57.4 ms: 1.12x slower                                                  |
| pickle_pure_python               | 251 us                                                             | 282 us: 1.12x slower                                                   |
| pycparser                        | 878 ms                                                             | 985 ms: 1.12x slower                                                   |
| sqlglot_v2_normalize             | 84.9 ms                                                            | 95.3 ms: 1.12x slower                                                  |
| unpickle_list                    | 3.03 us                                                            | 3.41 us: 1.12x slower                                                  |
| sympy_str                        | 200 ms                                                             | 225 ms: 1.13x slower                                                   |
| sympy_integrate                  | 15.1 ms                                                            | 17.1 ms: 1.13x slower                                                  |
| sqlalchemy_imperative            | 14.8 ms                                                            | 16.7 ms: 1.13x slower                                                  |
| sympy_expand                     | 344 ms                                                             | 388 ms: 1.13x slower                                                   |
| meteor_contest                   | 85.4 ms                                                            | 96.7 ms: 1.13x slower                                                  |
| scimark_lu                       | 74.7 ms                                                            | 84.7 ms: 1.13x slower                                                  |
| base32_large                     | 289 ms                                                             | 330 ms: 1.14x slower                                                   |
| deepcopy                         | 198 us                                                             | 225 us: 1.14x slower                                                   |
| base32_small                     | 5.71 ms                                                            | 6.52 ms: 1.14x slower                                                  |
| xdsl_constant_fold               | 36.0 ms                                                            | 41.2 ms: 1.15x slower                                                  |
| decimal_pi                       | 209 ms                                                             | 240 ms: 1.15x slower                                                   |
| logging_simple                   | 5.02 us                                                            | 5.77 us: 1.15x slower                                                  |
| quadtree_nbody                   | 654 ms                                                             | 753 ms: 1.15x slower                                                   |
| nqueens                          | 59.8 ms                                                            | 69.1 ms: 1.16x slower                                                  |
| comprehensions                   | 11.4 us                                                            | 13.2 us: 1.16x slower                                                  |
| crypto_pyaes                     | 56.7 ms                                                            | 65.6 ms: 1.16x slower                                                  |
| chaos                            | 42.9 ms                                                            | 49.7 ms: 1.16x slower                                                  |
| unpickle_pure_python             | 163 us                                                             | 188 us: 1.16x slower                                                   |
| deltablue                        | 2.76 ms                                                            | 3.19 ms: 1.16x slower                                                  |
| sqlglot_v2_transpile             | 1.21 ms                                                            | 1.40 ms: 1.16x slower                                                  |
| scimark_sparse_mat_mult          | 2.89 ms                                                            | 3.36 ms: 1.16x slower                                                  |
| django_template                  | 30.5 ms                                                            | 35.6 ms: 1.17x slower                                                  |
| deepcopy_memo                    | 19.1 us                                                            | 22.4 us: 1.17x slower                                                  |
| networkx_shortest_path           | 447 ms                                                             | 523 ms: 1.17x slower                                                   |
| python_startup                   | 9.93 ms                                                            | 11.6 ms: 1.17x slower                                                  |
| genshi_xml                       | 43.2 ms                                                            | 50.8 ms: 1.17x slower                                                  |
| scimark_sor                      | 78.2 ms                                                            | 91.9 ms: 1.18x slower                                                  |
| pyflate                          | 309 ms                                                             | 364 ms: 1.18x slower                                                   |
| base85_large                     | 249 ms                                                             | 295 ms: 1.18x slower                                                   |
| base85_small                     | 4.66 ms                                                            | 5.52 ms: 1.18x slower                                                  |
| regex_compile                    | 97.0 ms                                                            | 115 ms: 1.19x slower                                                   |
| noop                             | 19.2 ns                                                            | 22.8 ns: 1.19x slower                                                  |
| typing_runtime_protocols         | 115 us                                                             | 137 us: 1.19x slower                                                   |
| raytrace                         | 201 ms                                                             | 240 ms: 1.19x slower                                                   |
| deepcopy_reduce                  | 2.02 us                                                            | 2.42 us: 1.20x slower                                                  |
| pprint_safe_repr                 | 534 ms                                                             | 641 ms: 1.20x slower                                                   |
| chameleon                        | 10.3 ms                                                            | 12.3 ms: 1.20x slower                                                  |
| networkx_connected_components    | 425 ms                                                             | 511 ms: 1.20x slower                                                   |
| async_tree_eager                 | 83.0 ms                                                            | 100 ms: 1.21x slower                                                   |
| pprint_pformat                   | 1.10 sec                                                           | 1.33 sec: 1.21x slower                                                 |
| nbody                            | 74.2 ms                                                            | 89.8 ms: 1.21x slower                                                  |
| richards_super                   | 40.3 ms                                                            | 49.0 ms: 1.21x slower                                                  |
| go                               | 91.1 ms                                                            | 111 ms: 1.22x slower                                                   |
| hexiom                           | 4.50 ms                                                            | 5.50 ms: 1.22x slower                                                  |
| tomli_loads                      | 1.49 sec                                                           | 1.83 sec: 1.23x slower                                                 |
| sqlglot_v2_parse                 | 954 us                                                             | 1.17 ms: 1.23x slower                                                  |
| genshi_text                      | 18.0 ms                                                            | 22.2 ms: 1.23x slower                                                  |
| richards                         | 34.7 ms                                                            | 43.0 ms: 1.24x slower                                                  |
| python_startup_no_site           | 6.52 ms                                                            | 8.15 ms: 1.25x slower                                                  |
| scimark_monte_carlo              | 42.3 ms                                                            | 53.2 ms: 1.26x slower                                                  |
| logging_silent                   | 59.2 ns                                                            | 74.9 ns: 1.26x slower                                                  |
| ascii85_small                    | 13.0 ms                                                            | 16.6 ms: 1.27x slower                                                  |
| fannkuch                         | 246 ms                                                             | 319 ms: 1.29x slower                                                   |
| ascii85_large                    | 681 ms                                                             | 883 ms: 1.30x slower                                                   |
| coverage                         | 54.5 ms                                                            | 73.4 ms: 1.35x slower                                                  |
| mako                             | 8.69 ms                                                            | 12.1 ms: 1.39x slower                                                  |
| thread_memo_naive                | 12.4 ms                                                            | 21.0 ms: 1.69x slower                                                  |
| thread_montecarlo_naive          | 14.3 ms                                                            | 25.7 ms: 1.80x slower                                                  |
| Geometric mean                   | (ref)                                                              | 1.00x faster                                                           |

Benchmark hidden because not significant (2): unpack_sequence, async_tree_memoization_tg

- Geometric mean (including insignificant results): 1.001x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.07x
- 95% likely to have a slowdown of 1.06x
- 99% likely to have a slowdown of 1.05x

# Memory
- memory change: 1.46x