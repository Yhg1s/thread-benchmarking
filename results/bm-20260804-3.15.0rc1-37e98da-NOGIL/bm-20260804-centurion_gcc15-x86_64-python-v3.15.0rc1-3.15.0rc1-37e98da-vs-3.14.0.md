# Results vs. 3.14.0

- fork: python
- ref: v3.15.0rc1
- machine: linux-x86_64
- commit hash: 37e98da
- commit date: 2026-08-04
- overall geometric mean: 1.216x faster
- HPT reliability: 100.00%
- HPT 99th percentile: 1.03x slower
- Memory change: 1.50x

Benchmarks with tag 'apps':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| chameleon      | 10.6 ms                                                          | 11.8 ms: 1.12x slower                                                  |
| docutils       | 2.02 sec                                                         | 2.23 sec: 1.10x slower                                                 |
| fastapi_http   | 215 ms                                                           | 182 ms: 1.18x faster                                                   |
| html5lib       | 45.5 ms                                                          | 46.6 ms: 1.02x slower                                                  |
| tornado_http   | 101 ms                                                           | 91.9 ms: 1.10x faster                                                  |
| Geometric mean | (ref)                                                            | 1.01x faster                                                           |

Benchmarks with tag 'asyncio':
==============================

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| asyncio_tcp                      | 332 ms                                                           | 286 ms: 1.16x faster                                                   |
| asyncio_websockets               | 305 ms                                                           | 288 ms: 1.06x faster                                                   |
| coroutines                       | 15.4 ms                                                          | 15.1 ms: 1.02x faster                                                  |
| async_tree_io_tg                 | 529 ms                                                           | 536 ms: 1.01x slower                                                   |
| async_tree_eager_io              | 548 ms                                                           | 559 ms: 1.02x slower                                                   |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.33 sec: 1.03x slower                                                 |
| async_tree_io                    | 527 ms                                                           | 558 ms: 1.06x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 369 ms: 1.11x slower                                                   |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 492 ms: 1.13x slower                                                   |
| async_tree_eager_memoization     | 175 ms                                                           | 200 ms: 1.15x slower                                                   |
| async_tree_eager                 | 78.8 ms                                                          | 90.7 ms: 1.15x slower                                                  |
| async_generators                 | 243 ms                                                           | 281 ms: 1.16x slower                                                   |
| async_tree_none_tg               | 221 ms                                                           | 256 ms: 1.16x slower                                                   |
| async_tree_memoization_tg        | 275 ms                                                           | 326 ms: 1.19x slower                                                   |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 516 ms: 1.20x slower                                                   |
| async_tree_none                  | 223 ms                                                           | 269 ms: 1.21x slower                                                   |
| async_tree_memoization           | 274 ms                                                           | 344 ms: 1.25x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 486 ms: 1.26x slower                                                   |
| async_tree_eager_tg              | 179 ms                                                           | 228 ms: 1.27x slower                                                   |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 315 ms: 1.34x slower                                                   |
| Geometric mean                   | (ref)                                                            | 1.11x slower                                                           |

Benchmark hidden because not significant (1): async_tree_eager_io_tg

Benchmarks with tag 'baseline':
===============================

| Benchmark | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| noop      | 18.7 ns                                                          | 20.3 ns: 1.08x slower                                                  |

Benchmarks with tag 'decimal':
==============================

| Benchmark         | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| decimal_factorial | 170 ms                                                           | 186 ms: 1.10x slower                                                   |
| decimal_pi        | 201 ms                                                           | 236 ms: 1.17x slower                                                   |
| Geometric mean    | (ref)                                                            | 1.13x slower                                                           |

Benchmarks with tag 'math':
===========================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| pidigits       | 181 ms                                                           | 179 ms: 1.01x faster                                                   |
| quadtree_nbody | 602 ms                                                           | 625 ms: 1.04x slower                                                   |
| nbody          | 67.2 ms                                                          | 81.4 ms: 1.21x slower                                                  |
| float          | 48.1 ms                                                          | 63.5 ms: 1.32x slower                                                  |
| Geometric mean | (ref)                                                            | 1.13x slower                                                           |

Benchmarks with tag 'regex':
============================

| Benchmark      | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| regex_v8       | 15.0 ms                                                          | 15.5 ms: 1.03x slower                                                  |
| regex_dna      | 141 ms                                                           | 149 ms: 1.06x slower                                                   |
| regex_compile  | 91.6 ms                                                          | 101 ms: 1.11x slower                                                   |
| regex_effbot   | 1.80 ms                                                          | 2.05 ms: 1.14x slower                                                  |
| Geometric mean | (ref)                                                            | 1.08x slower                                                           |

Benchmarks with tag 'serialize':
================================

| Benchmark            | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large         | 276 ms                                                           | 2.10 ms: 131.68x faster                                                |
| base85_large         | 233 ms                                                           | 3.31 ms: 70.25x faster                                                 |
| ascii85_large        | 651 ms                                                           | 10.1 ms: 64.24x faster                                                 |
| base32_small         | 5.43 ms                                                          | 208 us: 26.10x faster                                                  |
| ascii85_small        | 12.5 ms                                                          | 485 us: 25.75x faster                                                  |
| base85_small         | 4.44 ms                                                          | 177 us: 25.15x faster                                                  |
| base64_large         | 6.31 ms                                                          | 1.55 ms: 4.09x faster                                                  |
| urlsafe_base64_small | 383 us                                                           | 254 us: 1.51x faster                                                   |
| xml_etree_iterparse  | 76.5 ms                                                          | 70.4 ms: 1.09x faster                                                  |
| json_dumps           | 7.37 ms                                                          | 7.09 ms: 1.04x faster                                                  |
| base64_small         | 230 us                                                           | 221 us: 1.04x faster                                                   |
| tomli_loads          | 1.41 sec                                                         | 1.38 sec: 1.02x faster                                                 |
| pickle               | 9.23 us                                                          | 9.49 us: 1.03x slower                                                  |
| pickle_pure_python   | 234 us                                                           | 242 us: 1.03x slower                                                   |
| xml_etree_parse      | 102 ms                                                           | 107 ms: 1.05x slower                                                   |
| unpickle_pure_python | 153 us                                                           | 163 us: 1.07x slower                                                   |
| xml_etree_generate   | 71.1 ms                                                          | 77.7 ms: 1.09x slower                                                  |
| pickle_dict          | 21.3 us                                                          | 23.4 us: 1.10x slower                                                  |
| xml_etree_process    | 50.0 ms                                                          | 57.0 ms: 1.14x slower                                                  |
| unpickle             | 10.3 us                                                          | 12.0 us: 1.16x slower                                                  |
| json_loads           | 17.3 us                                                          | 20.7 us: 1.19x slower                                                  |
| pickle_list          | 3.26 us                                                          | 3.94 us: 1.21x slower                                                  |
| unpickle_list        | 3.64 us                                                          | 4.54 us: 1.25x slower                                                  |
| base16_large         | 5.41 ms                                                          | 7.65 ms: 1.41x slower                                                  |
| base16_small         | 298 us                                                           | 441 us: 1.48x slower                                                   |
| Geometric mean       | (ref)                                                            | 2.52x faster                                                           |

Benchmarks with tag 'startup':
==============================

| Benchmark              | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| python_startup         | 9.62 ms                                                          | 11.2 ms: 1.17x slower                                                  |
| python_startup_no_site | 6.29 ms                                                          | 7.56 ms: 1.20x slower                                                  |
| Geometric mean         | (ref)                                                            | 1.19x slower                                                           |

Benchmarks with tag 'template':
===============================

| Benchmark       | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| django_template | 28.4 ms                                                          | 31.5 ms: 1.11x slower                                                  |
| mako            | 7.66 ms                                                          | 13.6 ms: 1.77x slower                                                  |
| Geometric mean  | (ref)                                                            | 1.40x slower                                                           |

Benchmarks with tag 'threads':
==============================

| Benchmark                   | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|-----------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| thread_mandelbrot_naive     | 217 ms                                                           | 55.3 ms: 3.92x faster                                                  |
| thread_mandelbrot_optimized | 215 ms                                                           | 55.8 ms: 3.86x faster                                                  |
| thread_pipeline_optimized   | 26.3 ms                                                          | 7.38 ms: 3.56x faster                                                  |
| thread_accumulate_optimized | 40.8 ms                                                          | 11.8 ms: 3.45x faster                                                  |
| thread_accumulate_naive     | 41.6 ms                                                          | 12.6 ms: 3.30x faster                                                  |
| thread_counter_optimized    | 18.7 ms                                                          | 5.67 ms: 3.29x faster                                                  |
| thread_memo_optimized       | 17.9 ms                                                          | 6.17 ms: 2.91x faster                                                  |
| thread_montecarlo_optimized | 12.6 ms                                                          | 4.63 ms: 2.72x faster                                                  |
| thread_pipeline_naive       | 35.4 ms                                                          | 20.2 ms: 1.75x faster                                                  |
| thread_counter_naive        | 21.4 ms                                                          | 13.1 ms: 1.64x faster                                                  |
| thread_memo_naive           | 11.8 ms                                                          | 22.2 ms: 1.88x slower                                                  |
| thread_montecarlo_naive     | 14.6 ms                                                          | 35.8 ms: 2.45x slower                                                  |
| Geometric mean              | (ref)                                                            | 2.15x faster                                                           |

All benchmarks:
===============

| Benchmark                        | bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d | bm-20260804-centurion_gcc15-x86_64-python-v3.15.0rc1-3.15.0rc1-37e98da |
|----------------------------------|:----------------------------------------------------------------:|:----------------------------------------------------------------------:|
| base32_large                     | 276 ms                                                           | 2.10 ms: 131.68x faster                                                |
| base85_large                     | 233 ms                                                           | 3.31 ms: 70.25x faster                                                 |
| ascii85_large                    | 651 ms                                                           | 10.1 ms: 64.24x faster                                                 |
| base32_small                     | 5.43 ms                                                          | 208 us: 26.10x faster                                                  |
| ascii85_small                    | 12.5 ms                                                          | 485 us: 25.75x faster                                                  |
| base85_small                     | 4.44 ms                                                          | 177 us: 25.15x faster                                                  |
| argparse_many_optionals          | 33.3 ms                                                          | 8.11 ms: 4.10x faster                                                  |
| base64_large                     | 6.31 ms                                                          | 1.55 ms: 4.09x faster                                                  |
| thread_mandelbrot_naive          | 217 ms                                                           | 55.3 ms: 3.92x faster                                                  |
| thread_mandelbrot_optimized      | 215 ms                                                           | 55.8 ms: 3.86x faster                                                  |
| thread_pipeline_optimized        | 26.3 ms                                                          | 7.38 ms: 3.56x faster                                                  |
| thread_accumulate_optimized      | 40.8 ms                                                          | 11.8 ms: 3.45x faster                                                  |
| thread_accumulate_naive          | 41.6 ms                                                          | 12.6 ms: 3.30x faster                                                  |
| thread_counter_optimized         | 18.7 ms                                                          | 5.67 ms: 3.29x faster                                                  |
| thread_memo_optimized            | 17.9 ms                                                          | 6.17 ms: 2.91x faster                                                  |
| thread_montecarlo_optimized      | 12.6 ms                                                          | 4.63 ms: 2.72x faster                                                  |
| gc_traversal                     | 3.33 ms                                                          | 1.34 ms: 2.49x faster                                                  |
| pylint                           | 215 ms                                                           | 91.3 ms: 2.36x faster                                                  |
| thread_pipeline_naive            | 35.4 ms                                                          | 20.2 ms: 1.75x faster                                                  |
| create_gc_cycles                 | 1.93 ms                                                          | 1.17 ms: 1.65x faster                                                  |
| thread_counter_naive             | 21.4 ms                                                          | 13.1 ms: 1.64x faster                                                  |
| urlsafe_base64_small             | 383 us                                                           | 254 us: 1.51x faster                                                   |
| argparse_subparsers              | 665 us                                                           | 491 us: 1.36x faster                                                   |
| fastapi_http                     | 215 ms                                                           | 182 ms: 1.18x faster                                                   |
| pathlib                          | 12.5 ms                                                          | 10.6 ms: 1.18x faster                                                  |
| asyncio_tcp                      | 332 ms                                                           | 286 ms: 1.16x faster                                                   |
| tornado_http                     | 101 ms                                                           | 91.9 ms: 1.10x faster                                                  |
| xml_etree_iterparse              | 76.5 ms                                                          | 70.4 ms: 1.09x faster                                                  |
| asyncio_websockets               | 305 ms                                                           | 288 ms: 1.06x faster                                                   |
| json_dumps                       | 7.37 ms                                                          | 7.09 ms: 1.04x faster                                                  |
| base64_small                     | 230 us                                                           | 221 us: 1.04x faster                                                   |
| tomli_loads                      | 1.41 sec                                                         | 1.38 sec: 1.02x faster                                                 |
| coroutines                       | 15.4 ms                                                          | 15.1 ms: 1.02x faster                                                  |
| pidigits                         | 181 ms                                                           | 179 ms: 1.01x faster                                                   |
| pycparser                        | 837 ms                                                           | 828 ms: 1.01x faster                                                   |
| deepcopy                         | 195 us                                                           | 196 us: 1.01x slower                                                   |
| bpe_tokeniser                    | 3.10 sec                                                         | 3.14 sec: 1.01x slower                                                 |
| async_tree_io_tg                 | 529 ms                                                           | 536 ms: 1.01x slower                                                   |
| async_tree_eager_io              | 548 ms                                                           | 559 ms: 1.02x slower                                                   |
| html5lib                         | 45.5 ms                                                          | 46.6 ms: 1.02x slower                                                  |
| pickle                           | 9.23 us                                                          | 9.49 us: 1.03x slower                                                  |
| regex_v8                         | 15.0 ms                                                          | 15.5 ms: 1.03x slower                                                  |
| asyncio_tcp_ssl                  | 1.29 sec                                                         | 1.33 sec: 1.03x slower                                                 |
| pickle_pure_python               | 234 us                                                           | 242 us: 1.03x slower                                                   |
| thrift                           | 1.84 ms                                                          | 1.91 ms: 1.04x slower                                                  |
| quadtree_nbody                   | 602 ms                                                           | 625 ms: 1.04x slower                                                   |
| logging_silent                   | 59.7 ns                                                          | 62.5 ns: 1.05x slower                                                  |
| xml_etree_parse                  | 102 ms                                                           | 107 ms: 1.05x slower                                                   |
| logging_simple                   | 4.72 us                                                          | 4.96 us: 1.05x slower                                                  |
| sqlglot_v2_transpile             | 1.15 ms                                                          | 1.21 ms: 1.05x slower                                                  |
| mdp                              | 935 ms                                                           | 984 ms: 1.05x slower                                                   |
| sqlglot_v2_optimize              | 38.7 ms                                                          | 40.8 ms: 1.05x slower                                                  |
| regex_dna                        | 141 ms                                                           | 149 ms: 1.06x slower                                                   |
| chaos                            | 41.9 ms                                                          | 44.2 ms: 1.06x slower                                                  |
| async_tree_io                    | 527 ms                                                           | 558 ms: 1.06x slower                                                   |
| unpickle_pure_python             | 153 us                                                           | 163 us: 1.07x slower                                                   |
| sympy_sum                        | 104 ms                                                           | 111 ms: 1.07x slower                                                   |
| logging_format                   | 5.24 us                                                          | 5.60 us: 1.07x slower                                                  |
| sqlglot_v2_normalize             | 77.8 ms                                                          | 83.2 ms: 1.07x slower                                                  |
| sqlglot_v2_parse                 | 909 us                                                           | 974 us: 1.07x slower                                                   |
| sympy_str                        | 192 ms                                                           | 206 ms: 1.07x slower                                                   |
| comprehensions                   | 11.2 us                                                          | 12.0 us: 1.08x slower                                                  |
| telco                            | 5.26 ms                                                          | 5.67 ms: 1.08x slower                                                  |
| sympy_integrate                  | 14.7 ms                                                          | 15.9 ms: 1.08x slower                                                  |
| pyflate                          | 300 ms                                                           | 324 ms: 1.08x slower                                                   |
| sympy_expand                     | 330 ms                                                           | 356 ms: 1.08x slower                                                   |
| scimark_sor                      | 72.8 ms                                                          | 78.7 ms: 1.08x slower                                                  |
| nqueens                          | 56.3 ms                                                          | 61.1 ms: 1.08x slower                                                  |
| generators                       | 20.7 ms                                                          | 22.5 ms: 1.08x slower                                                  |
| noop                             | 18.7 ns                                                          | 20.3 ns: 1.08x slower                                                  |
| json                             | 3.42 ms                                                          | 3.72 ms: 1.09x slower                                                  |
| go                               | 82.6 ms                                                          | 89.7 ms: 1.09x slower                                                  |
| scimark_fft                      | 197 ms                                                           | 214 ms: 1.09x slower                                                   |
| hexiom                           | 4.00 ms                                                          | 4.37 ms: 1.09x slower                                                  |
| xml_etree_generate               | 71.1 ms                                                          | 77.7 ms: 1.09x slower                                                  |
| deepcopy_reduce                  | 2.05 us                                                          | 2.24 us: 1.10x slower                                                  |
| decimal_factorial                | 170 ms                                                           | 186 ms: 1.10x slower                                                   |
| pickle_dict                      | 21.3 us                                                          | 23.4 us: 1.10x slower                                                  |
| sqlalchemy_imperative            | 14.3 ms                                                          | 15.7 ms: 1.10x slower                                                  |
| docutils                         | 2.02 sec                                                         | 2.23 sec: 1.10x slower                                                 |
| regex_compile                    | 91.6 ms                                                          | 101 ms: 1.11x slower                                                   |
| async_tree_eager_cpu_io_mixed    | 333 ms                                                           | 369 ms: 1.11x slower                                                   |
| django_template                  | 28.4 ms                                                          | 31.5 ms: 1.11x slower                                                  |
| pprint_safe_repr                 | 484 ms                                                           | 539 ms: 1.11x slower                                                   |
| chameleon                        | 10.6 ms                                                          | 11.8 ms: 1.12x slower                                                  |
| networkx_k_core                  | 2.07 sec                                                         | 2.31 sec: 1.12x slower                                                 |
| raytrace                         | 194 ms                                                           | 218 ms: 1.12x slower                                                   |
| mypy2                            | 756 ms                                                           | 853 ms: 1.13x slower                                                   |
| async_tree_cpu_io_mixed_tg       | 436 ms                                                           | 492 ms: 1.13x slower                                                   |
| xdsl_constant_fold               | 35.1 ms                                                          | 39.9 ms: 1.13x slower                                                  |
| deepcopy_memo                    | 18.2 us                                                          | 20.7 us: 1.13x slower                                                  |
| richards                         | 32.5 ms                                                          | 37.0 ms: 1.14x slower                                                  |
| regex_effbot                     | 1.80 ms                                                          | 2.05 ms: 1.14x slower                                                  |
| meteor_contest                   | 83.9 ms                                                          | 95.7 ms: 1.14x slower                                                  |
| xml_etree_process                | 50.0 ms                                                          | 57.0 ms: 1.14x slower                                                  |
| async_tree_eager_memoization     | 175 ms                                                           | 200 ms: 1.15x slower                                                   |
| async_tree_eager                 | 78.8 ms                                                          | 90.7 ms: 1.15x slower                                                  |
| pprint_pformat                   | 982 ms                                                           | 1.13 sec: 1.15x slower                                                 |
| richards_super                   | 37.2 ms                                                          | 43.0 ms: 1.15x slower                                                  |
| async_generators                 | 243 ms                                                           | 281 ms: 1.16x slower                                                   |
| unpickle                         | 10.3 us                                                          | 12.0 us: 1.16x slower                                                  |
| async_tree_none_tg               | 221 ms                                                           | 256 ms: 1.16x slower                                                   |
| scimark_lu                       | 66.7 ms                                                          | 78.0 ms: 1.17x slower                                                  |
| python_startup                   | 9.62 ms                                                          | 11.2 ms: 1.17x slower                                                  |
| spectral_norm                    | 59.6 ms                                                          | 69.8 ms: 1.17x slower                                                  |
| decimal_pi                       | 201 ms                                                           | 236 ms: 1.17x slower                                                   |
| deltablue                        | 2.24 ms                                                          | 2.66 ms: 1.19x slower                                                  |
| async_tree_memoization_tg        | 275 ms                                                           | 326 ms: 1.19x slower                                                   |
| json_loads                       | 17.3 us                                                          | 20.7 us: 1.19x slower                                                  |
| async_tree_cpu_io_mixed          | 430 ms                                                           | 516 ms: 1.20x slower                                                   |
| python_startup_no_site           | 6.29 ms                                                          | 7.56 ms: 1.20x slower                                                  |
| async_tree_none                  | 223 ms                                                           | 269 ms: 1.21x slower                                                   |
| pickle_list                      | 3.26 us                                                          | 3.94 us: 1.21x slower                                                  |
| nbody                            | 67.2 ms                                                          | 81.4 ms: 1.21x slower                                                  |
| typing_runtime_protocols         | 106 us                                                           | 131 us: 1.24x slower                                                   |
| scimark_sparse_mat_mult          | 2.58 ms                                                          | 3.20 ms: 1.24x slower                                                  |
| scimark_monte_carlo              | 37.5 ms                                                          | 46.7 ms: 1.25x slower                                                  |
| unpickle_list                    | 3.64 us                                                          | 4.54 us: 1.25x slower                                                  |
| async_tree_memoization           | 274 ms                                                           | 344 ms: 1.25x slower                                                   |
| networkx_connected_components    | 435 ms                                                           | 547 ms: 1.26x slower                                                   |
| networkx_shortest_path           | 445 ms                                                           | 560 ms: 1.26x slower                                                   |
| async_tree_eager_cpu_io_mixed_tg | 385 ms                                                           | 486 ms: 1.26x slower                                                   |
| async_tree_eager_tg              | 179 ms                                                           | 228 ms: 1.27x slower                                                   |
| crypto_pyaes                     | 51.5 ms                                                          | 65.5 ms: 1.27x slower                                                  |
| fannkuch                         | 234 ms                                                           | 299 ms: 1.28x slower                                                   |
| unpack_sequence                  | 24.1 ns                                                          | 31.2 ns: 1.30x slower                                                  |
| float                            | 48.1 ms                                                          | 63.5 ms: 1.32x slower                                                  |
| async_tree_eager_memoization_tg  | 235 ms                                                           | 315 ms: 1.34x slower                                                   |
| coverage                         | 55.4 ms                                                          | 74.5 ms: 1.34x slower                                                  |
| base16_large                     | 5.41 ms                                                          | 7.65 ms: 1.41x slower                                                  |
| base16_small                     | 298 us                                                           | 441 us: 1.48x slower                                                   |
| mako                             | 7.66 ms                                                          | 13.6 ms: 1.77x slower                                                  |
| thread_memo_naive                | 11.8 ms                                                          | 22.2 ms: 1.88x slower                                                  |
| thread_montecarlo_naive          | 14.6 ms                                                          | 35.8 ms: 2.45x slower                                                  |
| Geometric mean                   | (ref)                                                            | 1.22x faster                                                           |

Benchmark hidden because not significant (1): async_tree_eager_io_tg
Ignored benchmarks (2) of results/bm-20251007-3.14.0-ebf955d/bm-20251007-centurion_gcc15-x86_64-python-v3.14.0-3.14.0-ebf955d.json: genshi_text, genshi_xml

- Geometric mean (including insignificant results): 1.216x faster

# HPT report

- Reliability score: 100.00% likely to be slow
- 90% likely to have a slowdown of 1.05x
- 95% likely to have a slowdown of 1.05x
- 99% likely to have a slowdown of 1.03x

# Memory
- memory change: 1.50x