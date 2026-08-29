# Results vs. 3.13.0

- fork: python
- ref: v3.15.0b4
- machine: linux-x86_64
- commit hash: 0a6fa62
- commit date: 2026-07-18
- overall geometric mean: 1.243x faster
- HPT reliability: 94.18%
- HPT 99th percentile: 1.00x faster
- Memory change: 1.07x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 11.1 ms                                                            | 10.9 ms: 1.02x faster                                                  |
| docutils       | 1.89 sec                                                           | 1.91 sec: 1.01x slower                                                 |
| fastapi_http   | 215 ms                                                             | 227 ms: 1.06x slower                                                   |
| tornado_http   | 98.9 ms                                                            | 100 ms: 1.01x slower                                                   |
| Geometric mean | (ref)                                                              | 1.00x slower                                                           |

Benchmark hidden because not significant (1): html5lib

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| async_tree_memoization_tg        | 421 ms                                                             | 340 ms: 1.24x faster                                                   |
| async_tree_none                  | 312 ms                                                             | 264 ms: 1.18x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 188 ms: 1.18x faster                                                   |
| asyncio_tcp                      | 316 ms                                                             | 273 ms: 1.16x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 663 ms: 1.14x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 346 ms: 1.13x faster                                                   |
| coroutines                       | 18.2 ms                                                            | 16.4 ms: 1.11x faster                                                  |
| async_tree_io_tg                 | 781 ms                                                             | 705 ms: 1.11x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 672 ms: 1.10x faster                                                   |
| async_tree_none_tg               | 290 ms                                                             | 270 ms: 1.08x faster                                                   |
| async_generators                 | 251 ms                                                             | 234 ms: 1.07x faster                                                   |
| async_tree_eager                 | 88.3 ms                                                            | 83.5 ms: 1.06x faster                                                  |
| async_tree_eager_io_tg           | 731 ms                                                             | 699 ms: 1.05x faster                                                   |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 474 ms: 1.04x faster                                                   |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 491 ms: 1.03x faster                                                   |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 339 ms: 1.01x faster                                                   |
| asyncio_websockets               | 313 ms                                                             | 321 ms: 1.02x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 425 ms: 1.41x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 290 ms: 1.66x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 212 ms: 3.74x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.03x slower                                                           |

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 21.4 ns                                                            | 19.8 ns: 1.08x faster                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_pi        | 228 ms                                                             | 216 ms: 1.06x faster                                                   |
| decimal_factorial | 177 ms                                                             | 179 ms: 1.01x slower                                                   |
| Geometric mean    | (ref)                                                              | 1.02x faster                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| pidigits       | 216 ms                                                             | 217 ms: 1.01x slower                                                   |
| float          | 59.2 ms                                                            | 59.8 ms: 1.01x slower                                                  |
| Geometric mean | (ref)                                                              | 1.00x faster                                                           |

Benchmark hidden because not significant (2): nbody, quadtree_nbody

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_dna      | 159 ms                                                             | 153 ms: 1.04x faster                                                   |
| regex_effbot   | 2.33 ms                                                            | 2.27 ms: 1.03x faster                                                  |
| regex_compile  | 102 ms                                                             | 103 ms: 1.00x slower                                                   |
| regex_v8       | 15.0 ms                                                            | 16.1 ms: 1.07x slower                                                  |
| Geometric mean | (ref)                                                              | 1.00x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 325 ms                                                             | 1.90 ms: 171.10x faster                                                |
| ascii85_large        | 824 ms                                                             | 13.8 ms: 59.78x faster                                                 |
| base85_large         | 267 ms                                                             | 5.11 ms: 52.27x faster                                                 |
| base32_small         | 6.46 ms                                                            | 213 us: 30.39x faster                                                  |
| ascii85_small        | 15.7 ms                                                            | 530 us: 29.72x faster                                                  |
| base85_small         | 4.85 ms                                                            | 207 us: 23.46x faster                                                  |
| base16_large         | 42.7 ms                                                            | 7.41 ms: 5.76x faster                                                  |
| base64_large         | 5.69 ms                                                            | 1.59 ms: 3.59x faster                                                  |
| base16_small         | 836 us                                                             | 374 us: 2.24x faster                                                   |
| urlsafe_base64_small | 328 us                                                             | 246 us: 1.33x faster                                                   |
| tomli_loads          | 1.77 sec                                                           | 1.52 sec: 1.17x faster                                                 |
| unpickle_list        | 3.42 us                                                            | 2.95 us: 1.16x faster                                                  |
| json_dumps           | 7.26 ms                                                            | 6.57 ms: 1.10x faster                                                  |
| xml_etree_iterparse  | 86.8 ms                                                            | 83.7 ms: 1.04x faster                                                  |
| unpickle             | 10.8 us                                                            | 10.5 us: 1.03x faster                                                  |
| xml_etree_generate   | 70.6 ms                                                            | 69.9 ms: 1.01x faster                                                  |
| json_loads           | 18.2 us                                                            | 18.1 us: 1.01x faster                                                  |
| xml_etree_process    | 49.9 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| pickle_dict          | 19.0 us                                                            | 19.5 us: 1.03x slower                                                  |
| xml_etree_parse      | 121 ms                                                             | 124 ms: 1.03x slower                                                   |
| base64_small         | 222 us                                                             | 237 us: 1.07x slower                                                   |
| unpickle_pure_python | 161 us                                                             | 174 us: 1.08x slower                                                   |
| pickle_pure_python   | 245 us                                                             | 267 us: 1.09x slower                                                   |
| pickle               | 7.21 us                                                            | 8.26 us: 1.15x slower                                                  |
| pickle_list          | 2.66 us                                                            | 3.22 us: 1.21x slower                                                  |
| Geometric mean       | (ref)                                                              | 2.96x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup_no_site | 6.49 ms                                                            | 6.01 ms: 1.08x faster                                                  |
| python_startup         | 9.51 ms                                                            | 9.67 ms: 1.02x slower                                                  |
| Geometric mean         | (ref)                                                              | 1.03x faster                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 28.8 ms                                                            | 31.2 ms: 1.08x slower                                                  |
| mako            | 8.30 ms                                                            | 9.51 ms: 1.15x slower                                                  |
| Geometric mean  | (ref)                                                              | 1.11x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|-----------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_memo_naive           | 37.9 ms                                                            | 10.7 ms: 3.53x faster                                                  |
| thread_pipeline_naive       | 49.8 ms                                                            | 36.4 ms: 1.37x faster                                                  |
| thread_montecarlo_naive     | 18.1 ms                                                            | 14.7 ms: 1.23x faster                                                  |
| thread_montecarlo_optimized | 14.2 ms                                                            | 13.3 ms: 1.07x faster                                                  |
| thread_counter_naive        | 23.7 ms                                                            | 24.3 ms: 1.02x slower                                                  |
| thread_counter_optimized    | 19.7 ms                                                            | 21.6 ms: 1.09x slower                                                  |
| thread_memo_optimized       | 16.8 ms                                                            | 18.4 ms: 1.09x slower                                                  |
| thread_mandelbrot_naive     | 190 ms                                                             | 208 ms: 1.10x slower                                                   |
| thread_mandelbrot_optimized | 189 ms                                                             | 208 ms: 1.10x slower                                                   |
| thread_accumulate_naive     | 36.5 ms                                                            | 43.2 ms: 1.18x slower                                                  |
| thread_accumulate_optimized | 35.3 ms                                                            | 42.4 ms: 1.20x slower                                                  |
| thread_pipeline_optimized   | 22.8 ms                                                            | 27.5 ms: 1.21x slower                                                  |
| Geometric mean              | (ref)                                                              | 1.08x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5 | bm-20260718-centurion_clang22-x86_64-python-v3.15.0b4-3.15.0b4-0a6fa62 |
|----------------------------------|:------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 325 ms                                                             | 1.90 ms: 171.10x faster                                                |
| ascii85_large                    | 824 ms                                                             | 13.8 ms: 59.78x faster                                                 |
| base85_large                     | 267 ms                                                             | 5.11 ms: 52.27x faster                                                 |
| base32_small                     | 6.46 ms                                                            | 213 us: 30.39x faster                                                  |
| ascii85_small                    | 15.7 ms                                                            | 530 us: 29.72x faster                                                  |
| base85_small                     | 4.85 ms                                                            | 207 us: 23.46x faster                                                  |
| base16_large                     | 42.7 ms                                                            | 7.41 ms: 5.76x faster                                                  |
| base64_large                     | 5.69 ms                                                            | 1.59 ms: 3.59x faster                                                  |
| thread_memo_naive                | 37.9 ms                                                            | 10.7 ms: 3.53x faster                                                  |
| base16_small                     | 836 us                                                             | 374 us: 2.24x faster                                                   |
| pylint                           | 226 ms                                                             | 103 ms: 2.19x faster                                                   |
| mdp                              | 2.05 sec                                                           | 996 ms: 2.06x faster                                                   |
| argparse_many_optionals          | 12.9 ms                                                            | 8.43 ms: 1.54x faster                                                  |
| deepcopy_memo                    | 27.8 us                                                            | 19.3 us: 1.44x faster                                                  |
| deepcopy                         | 267 us                                                             | 190 us: 1.40x faster                                                   |
| thread_pipeline_naive            | 49.8 ms                                                            | 36.4 ms: 1.37x faster                                                  |
| go                               | 129 ms                                                             | 96.3 ms: 1.34x faster                                                  |
| urlsafe_base64_small             | 328 us                                                             | 246 us: 1.33x faster                                                   |
| async_tree_memoization_tg        | 421 ms                                                             | 340 ms: 1.24x faster                                                   |
| thread_montecarlo_naive          | 18.1 ms                                                            | 14.7 ms: 1.23x faster                                                  |
| async_tree_none                  | 312 ms                                                             | 264 ms: 1.18x faster                                                   |
| async_tree_eager_memoization     | 221 ms                                                             | 188 ms: 1.18x faster                                                   |
| tomli_loads                      | 1.77 sec                                                           | 1.52 sec: 1.17x faster                                                 |
| unpickle_list                    | 3.42 us                                                            | 2.95 us: 1.16x faster                                                  |
| deepcopy_reduce                  | 2.36 us                                                            | 2.03 us: 1.16x faster                                                  |
| asyncio_tcp                      | 316 ms                                                             | 273 ms: 1.16x faster                                                   |
| pyflate                          | 374 ms                                                             | 326 ms: 1.14x faster                                                   |
| async_tree_eager_io              | 753 ms                                                             | 663 ms: 1.14x faster                                                   |
| async_tree_memoization           | 392 ms                                                             | 346 ms: 1.13x faster                                                   |
| pathlib                          | 12.2 ms                                                            | 11.0 ms: 1.11x faster                                                  |
| coroutines                       | 18.2 ms                                                            | 16.4 ms: 1.11x faster                                                  |
| async_tree_io_tg                 | 781 ms                                                             | 705 ms: 1.11x faster                                                   |
| async_tree_io                    | 743 ms                                                             | 672 ms: 1.10x faster                                                   |
| json_dumps                       | 7.26 ms                                                            | 6.57 ms: 1.10x faster                                                  |
| noop                             | 21.4 ns                                                            | 19.8 ns: 1.08x faster                                                  |
| fannkuch                         | 287 ms                                                             | 265 ms: 1.08x faster                                                   |
| python_startup_no_site           | 6.49 ms                                                            | 6.01 ms: 1.08x faster                                                  |
| async_tree_none_tg               | 290 ms                                                             | 270 ms: 1.08x faster                                                   |
| async_generators                 | 251 ms                                                             | 234 ms: 1.07x faster                                                   |
| thread_montecarlo_optimized      | 14.2 ms                                                            | 13.3 ms: 1.07x faster                                                  |
| richards                         | 38.2 ms                                                            | 36.1 ms: 1.06x faster                                                  |
| async_tree_eager                 | 88.3 ms                                                            | 83.5 ms: 1.06x faster                                                  |
| scimark_sor                      | 96.2 ms                                                            | 91.0 ms: 1.06x faster                                                  |
| decimal_pi                       | 228 ms                                                             | 216 ms: 1.06x faster                                                   |
| create_gc_cycles                 | 1.77 ms                                                            | 1.68 ms: 1.05x faster                                                  |
| async_tree_eager_io_tg           | 731 ms                                                             | 699 ms: 1.05x faster                                                   |
| richards_super                   | 43.8 ms                                                            | 42.1 ms: 1.04x faster                                                  |
| async_tree_cpu_io_mixed          | 494 ms                                                             | 474 ms: 1.04x faster                                                   |
| gc_traversal                     | 3.20 ms                                                            | 3.07 ms: 1.04x faster                                                  |
| sqlglot_v2_transpile             | 1.22 ms                                                            | 1.17 ms: 1.04x faster                                                  |
| regex_dna                        | 159 ms                                                             | 153 ms: 1.04x faster                                                   |
| xml_etree_iterparse              | 86.8 ms                                                            | 83.7 ms: 1.04x faster                                                  |
| sqlglot_v2_parse                 | 979 us                                                             | 945 us: 1.04x faster                                                   |
| bpe_tokeniser                    | 3.37 sec                                                           | 3.26 sec: 1.04x faster                                                 |
| async_tree_cpu_io_mixed_tg       | 507 ms                                                             | 491 ms: 1.03x faster                                                   |
| regex_effbot                     | 2.33 ms                                                            | 2.27 ms: 1.03x faster                                                  |
| unpickle                         | 10.8 us                                                            | 10.5 us: 1.03x faster                                                  |
| spectral_norm                    | 68.6 ms                                                            | 66.8 ms: 1.03x faster                                                  |
| chameleon                        | 11.1 ms                                                            | 10.9 ms: 1.02x faster                                                  |
| asyncio_tcp_ssl                  | 1.28 sec                                                           | 1.26 sec: 1.02x faster                                                 |
| telco                            | 5.37 ms                                                            | 5.30 ms: 1.01x faster                                                  |
| json                             | 3.50 ms                                                            | 3.46 ms: 1.01x faster                                                  |
| networkx_shortest_path           | 454 ms                                                             | 449 ms: 1.01x faster                                                   |
| xml_etree_generate               | 70.6 ms                                                            | 69.9 ms: 1.01x faster                                                  |
| async_tree_eager_cpu_io_mixed    | 342 ms                                                             | 339 ms: 1.01x faster                                                   |
| chaos                            | 43.6 ms                                                            | 43.2 ms: 1.01x faster                                                  |
| networkx_connected_components    | 443 ms                                                             | 439 ms: 1.01x faster                                                   |
| json_loads                       | 18.2 us                                                            | 18.1 us: 1.01x faster                                                  |
| sqlglot_v2_optimize              | 42.1 ms                                                            | 42.2 ms: 1.00x slower                                                  |
| regex_compile                    | 102 ms                                                             | 103 ms: 1.00x slower                                                   |
| sqlglot_v2_normalize             | 83.6 ms                                                            | 84.1 ms: 1.00x slower                                                  |
| pidigits                         | 216 ms                                                             | 217 ms: 1.01x slower                                                   |
| sympy_integrate                  | 15.4 ms                                                            | 15.5 ms: 1.01x slower                                                  |
| logging_simple                   | 5.06 us                                                            | 5.10 us: 1.01x slower                                                  |
| xml_etree_process                | 49.9 ms                                                            | 50.4 ms: 1.01x slower                                                  |
| docutils                         | 1.89 sec                                                           | 1.91 sec: 1.01x slower                                                 |
| float                            | 59.2 ms                                                            | 59.8 ms: 1.01x slower                                                  |
| tornado_http                     | 98.9 ms                                                            | 100 ms: 1.01x slower                                                   |
| decimal_factorial                | 177 ms                                                             | 179 ms: 1.01x slower                                                   |
| python_startup                   | 9.51 ms                                                            | 9.67 ms: 1.02x slower                                                  |
| mypy2                            | 741 ms                                                             | 756 ms: 1.02x slower                                                   |
| asyncio_websockets               | 313 ms                                                             | 321 ms: 1.02x slower                                                   |
| thread_counter_naive             | 23.7 ms                                                            | 24.3 ms: 1.02x slower                                                  |
| meteor_contest                   | 85.7 ms                                                            | 87.8 ms: 1.02x slower                                                  |
| pickle_dict                      | 19.0 us                                                            | 19.5 us: 1.03x slower                                                  |
| xml_etree_parse                  | 121 ms                                                             | 124 ms: 1.03x slower                                                   |
| scimark_sparse_mat_mult          | 2.86 ms                                                            | 2.96 ms: 1.04x slower                                                  |
| typing_runtime_protocols         | 112 us                                                             | 117 us: 1.04x slower                                                   |
| logging_format                   | 5.62 us                                                            | 5.86 us: 1.04x slower                                                  |
| nqueens                          | 58.3 ms                                                            | 61.1 ms: 1.05x slower                                                  |
| pprint_pformat                   | 1.13 sec                                                           | 1.18 sec: 1.05x slower                                                 |
| fastapi_http                     | 215 ms                                                             | 227 ms: 1.06x slower                                                   |
| hexiom                           | 4.75 ms                                                            | 5.02 ms: 1.06x slower                                                  |
| crypto_pyaes                     | 55.6 ms                                                            | 58.9 ms: 1.06x slower                                                  |
| argparse_subparsers              | 449 us                                                             | 476 us: 1.06x slower                                                   |
| base64_small                     | 222 us                                                             | 237 us: 1.07x slower                                                   |
| regex_v8                         | 15.0 ms                                                            | 16.1 ms: 1.07x slower                                                  |
| pprint_safe_repr                 | 546 ms                                                             | 586 ms: 1.07x slower                                                   |
| sympy_str                        | 193 ms                                                             | 208 ms: 1.08x slower                                                   |
| sympy_sum                        | 104 ms                                                             | 112 ms: 1.08x slower                                                   |
| xdsl_constant_fold               | 36.4 ms                                                            | 39.2 ms: 1.08x slower                                                  |
| sqlalchemy_imperative            | 13.9 ms                                                            | 15.0 ms: 1.08x slower                                                  |
| sympy_expand                     | 331 ms                                                             | 358 ms: 1.08x slower                                                   |
| unpickle_pure_python             | 161 us                                                             | 174 us: 1.08x slower                                                   |
| pycparser                        | 901 ms                                                             | 976 ms: 1.08x slower                                                   |
| django_template                  | 28.8 ms                                                            | 31.2 ms: 1.08x slower                                                  |
| pickle_pure_python               | 245 us                                                             | 267 us: 1.09x slower                                                   |
| thread_counter_optimized         | 19.7 ms                                                            | 21.6 ms: 1.09x slower                                                  |
| deltablue                        | 2.59 ms                                                            | 2.83 ms: 1.09x slower                                                  |
| thread_memo_optimized            | 16.8 ms                                                            | 18.4 ms: 1.09x slower                                                  |
| comprehensions                   | 11.4 us                                                            | 12.5 us: 1.10x slower                                                  |
| thread_mandelbrot_naive          | 190 ms                                                             | 208 ms: 1.10x slower                                                   |
| thread_mandelbrot_optimized      | 189 ms                                                             | 208 ms: 1.10x slower                                                   |
| coverage                         | 55.0 ms                                                            | 60.7 ms: 1.10x slower                                                  |
| scimark_lu                       | 70.2 ms                                                            | 78.0 ms: 1.11x slower                                                  |
| generators                       | 22.2 ms                                                            | 25.2 ms: 1.13x slower                                                  |
| pickle                           | 7.21 us                                                            | 8.26 us: 1.15x slower                                                  |
| mako                             | 8.30 ms                                                            | 9.51 ms: 1.15x slower                                                  |
| logging_silent                   | 60.1 ns                                                            | 70.1 ns: 1.17x slower                                                  |
| thread_accumulate_naive          | 36.5 ms                                                            | 43.2 ms: 1.18x slower                                                  |
| thread_accumulate_optimized      | 35.3 ms                                                            | 42.4 ms: 1.20x slower                                                  |
| thread_pipeline_optimized        | 22.8 ms                                                            | 27.5 ms: 1.21x slower                                                  |
| pickle_list                      | 2.66 us                                                            | 3.22 us: 1.21x slower                                                  |
| unpack_sequence                  | 26.4 ns                                                            | 36.0 ns: 1.36x slower                                                  |
| async_tree_eager_cpu_io_mixed_tg | 301 ms                                                             | 425 ms: 1.41x slower                                                   |
| async_tree_eager_memoization_tg  | 175 ms                                                             | 290 ms: 1.66x slower                                                   |
| async_tree_eager_tg              | 56.8 ms                                                            | 212 ms: 3.74x slower                                                   |
| Geometric mean                   | (ref)                                                              | 1.24x faster                                                           |

Benchmark hidden because not significant (8): html5lib, nbody, quadtree_nbody, thrift, scimark_fft, raytrace, networkx_k_core, scimark_monte_carlo
Ignored benchmarks (2) of results/bm-20241007-3.13.0-60403a5/bm-20241007-centurion_clang22-x86_64-python-v3.13.0-3.13.0-60403a5.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.243x faster

# HPT report

- Reliability score: 94.18% likely to be faster
- 90% likely to have a speedup of 1.00x
- 95% likely to have a speedup of 1.00x
- 99% likely to have a speedup of 1.00x

# Memory
- memory change: 1.07x